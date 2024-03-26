---
title: Configuración y protocolo del conector SMS
description: Obtenga más información sobre el conector de SMS y cómo configurarlo
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: ea936128-1c51-483d-914c-6d06708456d6
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '8640'
ht-degree: 85%

---

# Configuración y protocolo del conector SMS {#sms-connector-protocol}

>[!NOTE]
>
>El **Configuración y protocolo del conector SMS** para Adobe Campaign Classic se puede encontrar en esta [página](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html).
>
>En este documento, todas las referencias a los detalles acerca del protocolo, los nombres de campo y los valores se refieren a la [especificación SMPP 3.4](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

## Información general {#overview}

Los SMS pueden limitarse a enviar mensajes de texto cortos sin formato, pero su sencillez lo convierte en un valioso canal de comunicación.

Existen dos maneras principales de enviar un SMS:

* Enviarlo manualmente desde un teléfono, la forma habitual de comunicarse directamente entre personas.

* Enviarlo desde Internet, la forma en que Adobe Campaign envía mensajes. Para eso, se necesita un proveedor de servicios de SMS que conecte Internet a la red móvil.
Adobe Campaign utiliza el protocolo SMPP para enviar SMS a un proveedor de servicios.

Este documento le guiará a través de la conexión configurada entre Adobe Campaign y un proveedor SMPP.

Los proveedores de SMPP a veces pueden desviarse de la especificación oficial, pero el conector de SMS en Adobe Campaign ofrece muchas opciones para adaptar su comportamiento para que sea compatible con la mayoría de los proveedores.

>[!IMPORTANT]
>
>La configuración de una conexión con un nuevo proveedor puede requerir algunas habilidades técnicas, conocimientos de TCP, representación binaria, hexadecimal y codificaciones de texto. También requerirá una cooperación activa con el proveedor.

### Tipos de SMS {#sms-types}

Al enviar SMS masivos a través de un proveedor de SMS, se encontrará con tres tipos diferentes de SMS:

* **SMS MT (móvil finalizado)**: un SMS emitido por Adobe Campaign hacia los teléfonos móviles a través del proveedor de SMPP.

* **SMS MO (móvil original)**: un SMS que un móvil envía a Adobe Campaign a través del proveedor de SMPP.

* **SMS SR (informe de estado) o DR o DLR (recibo de envío)**: un recibo de devolución enviado por el móvil a Adobe Campaign a través del proveedor de SMPP que indica que el SMS se ha recibido correctamente. Adobe Campaign también puede recibir SR indicando que el mensaje no se pudo entregar, a menudo con una descripción del error.

Debe distinguir entre reconocimientos (RESP PDU, parte del protocolo SMPP) y SR: SR es un tipo de SMS que se envía a través de la red de extremo a extremo, mientras que un reconocimiento es solo una confirmación de que una transferencia se ha realizado con éxito.

Tanto los reconocimientos como SR pueden desencadenar errores. Si se distingue entre los dos, se ayudará a solucionar los problemas.

### Información transmitida por un SMS {#information-sms}

Un SMS lleva más información que texto. Aquí hay una lista de lo que puede encontrar en un SMS:

* El texto está limitado a 140 bytes, lo que significa entre 70 y 160 caracteres en función de la codificación. Consulte [Codificación de texto SMS](../../administration/using/sms-protocol.md#sms-text-encoding) a continuación para obtener detalles y limitaciones.

* Una dirección de destinatario, a veces denominada `ADC` o `MSISDN`. Ese es el número del móvil que recibirá el SMS.

* Una dirección de remitente, que puede llamarse `oADC` o, a veces, `sender id`. Puede ser un número de teléfono de uso diario, un código corto cuando se envía a través de un proveedor o un nombre. El nombre es una característica opcional, en ese caso no puede responder al SMS.

* Un indicador que señala si el mensaje es un mensaje flash. Un mensaje flash es una ventana emergente que no se almacena en la memoria.

* Un indicador que señala si se espera o no un SR.

* Una fecha de validez, después de la cual no se permite reintentar ningún equipo de red.

* Un campo `data_coding` que indica la codificación del texto.

## Protocolo SMPP {#smpp-protocol}

Adobe Campaign Standard es compatible con la versión 3.4 del protocolo SMPP. Se trata de un protocolo muy extendido que permite enviar SMS a un proveedor (SMSC) y recibir SMS, así como recibos. Para obtener más información, consulte la [documentación de SMPP](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

El equipo de red en el lado del proveedor de servicios SMS suele conocerse como SMSC.

### Conexiones SMPP {#smpp-connections}

Adobe Campaign se conecta al equipo de red del proveedor de servicios SMS a través de TCP. El protocolo SMPP establece conexiones TCP permanentes desde Adobe Campaign al proveedor. Adobe Campaign siempre inicia las conexiones TCP, incluso para recibir mensajes.
SMPP abre 1 o 2 conexiones TCP, dependiendo de su modo. Adobe Campaign siempre inicia todas las conexiones.

El protocolo SMPP puede funcionar en dos modos:

* **Transmisor+receptor (o TX+RX)**: se utilizan dos conexiones TCP independientes para transmitir y recibir mensajes.
* **Transceptor (abort TRX)**: se utiliza una sola conexión TCP para transmitir y recibir mensajes.

>[!NOTE]
>
>TRX se prefiere para Adobe Campaign Standard, ya que reduce el número de conexiones y simplifica la recuperación de la conexión en caso de error.

### PDU SMPP {#smpp-pdu}

Las unidades de transmisión SMPP (&quot;paquetes&quot;) se denominan PDU. Una **PDU** contiene un comando, un estado, un número de secuencia y datos.

Cada PDU debe ser reconocida por una `SMPP RESP PDU` (respuesta sincrónica). Las solicitudes pueden canalizarse: el remitente puede enviar muchos comandos sin esperar `RESP`, el número de solicitudes que se pueden canalizar en cualquier momento se denomina ventana. `RESP PDU` puede llegar en cualquier orden, sin relación con el orden de su PDU iniciador correspondiente.

En el modo separado **Transmisor+receptor**, la conexión utilizada depende del tipo de mensaje transmitido. La conexión del transmisor se utiliza para MT y la conexión del receptor para MO y SR. Las solicitudes y respuestas para cada tipo de mensaje se envían a través de la misma conexión TCP.

Por ejemplo, al enviar un mensaje MT, se utiliza la conexión del transmisor y el `RESP` que reconoce el mensaje MT también se envía a través del canal del transmisor. Cuando recibe un MO (o un SR), la conexión del receptor se utiliza para recibir el MO y para enviar el `RESP` que reconoce el MO.

![](assets/do-not-localize/sms_protocol_1.png)

En Adobe Campaign Standard, la reconciliación de MT y SR es nativa del MTA, por lo que no hay ningún proceso de SMS dedicado.

Un `SUBMIT_SM_RESP PDU` exitoso activa el estado de mensaje &quot;enviado&quot; en el registro de envío, mientras que un `DELIVER_SM (SR) PDU` exitoso activa el estado de mensaje &quot;recibido&quot;.

### Aspectos de seguridad {#security-aspects}

El protocolo en sí no está cifrado. La mayoría de los proveedores implementan una variante de IP en la lista de permitidos, por lo que las direcciones IP del servidor Adobe Campaign deben declararse al proveedor.

Adobe Campaign permite pasar un inicio de sesión y una contraseña durante la fase de enlace. También admite SMPP a través de TLS. Cabe señalar que los certificados son necesarios para garantizar la seguridad adecuada. Aunque el conector SMPP permite omitir las comprobaciones de certificados, solo debe utilizarse para pruebas, ya que TLS sin certificados proporciona un nivel de seguridad significativamente inferior.

El conector utiliza los certificados predeterminados proporcionados por la biblioteca `openssl` del sistema. Generalmente lo proporciona el directorio `/etc/ssl/certs` en Debian. Este directorio lo proporciona el paquete “ca-certificates” de manera predeterminada, pero se puede personalizar.

### Información en cada tipo de PDU {#information-pdu}

Cada tipo de PDU tiene campos distintos que llevan diferentes partes de información. Estas PDU se detallan en la [especificación SMPP 3.4](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

Cada sección a continuación describe la PDU y su respuesta sincrónica (`*_RESP PDU`). Todas las PDU deben ser reconocidas por una `RESP` correspondiente, es una parte obligatoria de la especificación.

Las PDU pueden tener campos opcionales. Aquí solo se describen los campos más comunes. Consulte la [especificación SMPP 3.4](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) para obtener más información.

#### BIND_TRANSMITTER / BIND_RECEIVER / BIND_TRANSCEIVER {#bind-transmitter}

Esta PDU se utiliza para iniciar una conexión al SMSC. Los modos **Transmisor**, **Receptor** y **Transceptor** solo cambian el tipo de SMS que se permite transferir a través de esta conexión, específicamente:

| Modo | Clases de SMS admitidos |
|:-:|:-:|
| Transmisor | MT |
| Receptor | MO + SR |
| Transceptor | MT + MO + SR |

Campos notables en una `BIND_* PDU`:

* **system_id**: Credenciales utilizadas para la autenticación. Se configura en la cuenta externa.

* **contraseña**: Contraseña utilizada para la autenticación. Se configura en la cuenta externa.

* **system_type**: Necesario para establecerse en un valor específico para algunos proveedores. Se configura en la cuenta externa, disponible en todas las versiones. A menudo distingue entre diferentes tipos de contratos, canales, países, etc.

* **addr_ton** y **addr_npi**: Requerido por algunos proveedores. Establecido por la configuración `Bind TON` y `Bind NPI` en la cuenta externa.

* **address_range**: Requerido por algunos proveedores. La mayoría de las veces, esta es una lista de códigos abreviados permitidos en esta conexión. Se configura en la cuenta externa.

`BIND_*_RESP` no tiene un campo específico, confirma si la conexión se realizó correctamente o no.

#### UNBIND {#unbind}

El sistema debe enviar esta PDU antes de desconectarse. Debe esperar la coincidencia `UNBIND_RESP PDU` antes de cerrar la conexión.

La conformidad con SMSC no debe cerrar la conexión, la conexión TCP está controlada por el conector Adobe Campaign.

#### SUBMIT_SM {#submit-sm}

Esta PDU envía un MT al SMSC. Su PDU de respuesta proporciona el ID del MT.

Campos notables en una `SUBMIT_SM PDU`:

* **service_type**: requerido por algunos proveedores. Se establece en las propiedades de envío.

* **source_addr_ton** y **source_addr_npi**: indica qué tipo de dirección de origen se transmite. El significado de estos campos está estandarizado, pero dado que algunos proveedores lo utilizan de manera diferente, debe solicitar al proveedor su valor correcto. Se configura en la cuenta externa.

* **source_addr**: la dirección de origen / oADC del MT. Se mostrará en el teléfono móvil. Establecido en la cuenta externa y el envío, el valor del envío tiene prioridad sobre el valor de la cuenta externa.

* **dest_addr_ton** y **dest_addr_npi**: indica qué tipo de dirección de destino se transmite (por ejemplo, formato local o internacional). El significado de estos campos está estandarizado, pero dado que algunos proveedores lo utilizan de manera diferente, debe solicitar al proveedor su valor correcto. Se configura en la cuenta externa.

* **destination_addr**: dirección de destinatario, número de teléfono o MSISDN.

* **esm_class**: se utiliza para indicar si se usa UDH o no en el campo de texto. Habilitado automáticamente por el conector para SMS dividido si no se utiliza el modo `message_payload`.

* **priority_flag**: prioridad de este mensaje sobre otros. Esto está ligado a la prioridad del propio envío.

* **validity_period**: marca de tiempo después de la cual no se debe reintentar. Establecido en el envío mismo.

* **registered_delivery**: indica si se solicita o no un SR. Adobe Campaign siempre establece este indicador excepto para las respuestas automáticas. Para los mensajes de varias partes, el indicador solo se establece para la primera parte. Todas las versiones tienen el mismo comportamiento.

* **data_coding**: indica la codificación utilizada en el campo de texto. Consulte la sección [Codificación de texto SMS](../../administration/using/sms-protocol.md#sms-text-encoding) para obtener más información.

* **short_message**: el texto del mensaje. Si se usa UDH, también contiene el encabezado de UHD.

Adobe Campaign admite estos campos opcionales:

* **dest_addr_subunit**: utilizado para especificar el destinatario del SMS: flash, móvil o tarjeta SIM. Se establece en las propiedades de envío.

* **message_payload**: cuando se habilita en la cuenta externa, los mensajes largos se envían en una sola PDU y el texto se transmitirá en este campo en lugar de en el campo `short_message`.

#### SUBMIT_SM_RESP {#submit-sm-resp}

Esta PDU contendrá el ID del MT. Esto resulta útil para relacionarlo con SR entrante.

>[!IMPORTANT]
>
>Muchos proveedores transmiten el ID de MT en formato hexadecimal. Asegúrese de establecer correctamente el formato de ID **en la configuración de confirmación de MT** en la cuenta externa.

Algunos proveedores envían `SUBMIT_SM_RESP` después de enviar el SR. Para tener en cuenta ese comportamiento, Adobe Campaign espera 30 segundos antes de responder **ID de mensaje no válido** a un SR con un ID desconocido.

#### DELIVER_SM {#delivery-sm}

El SMSC envía esta PDU a Adobe Campaign. Contiene un MO o un SR.

La mayoría de los campos tienen el mismo significado que su contraparte `SUBMIT_SM`. Esta es la lista de campos útiles:

* **source_addr**: dirección de origen del MO/SR. Generalmente es un número de teléfono.

* **destination_addr**: código corto que recibió el MO o el SR.

* **esm_class**: se usa para saber si la PDU es un MO o un SR.

* **short_message**: texto del mensaje. Para SR, contiene datos descritos en el apéndice B de la especificación del protocolo SMPP. Consulte [Administración de errores de SR](../../administration/using/sms-protocol.md#sr-error-management) para obtener más detalles.

Adobe Campaign puede leer el ID del mensaje en la `receipted_message_id` campo opcional con algunos ajustes de configuración.

#### DELIVER_SM_RESP {#deliver-sm-resp}

Adobe Campaign envía esta PDU para reconocer SR y MO.

Adobe Campaign Standard solo envía un `DELIVER_SM_RESP` una vez que todos los pasos de procesamiento se hayan realizado correctamente. Esto garantiza que no se reconozca ningún SR o MO mientras exista el riesgo de errores de procesamiento.

#### ENQUIRE_LINK {#enquire-links}

Esta PDU solo se utiliza para comprobar que la conexión está activa. Su frecuencia debe establecerse de acuerdo con las necesidades del proveedor.

Los 60 segundos predeterminados deben coincidir con la mayoría de las configuraciones establecidas en la cuenta externa.

#### ENQUIRE_LINK_RESP {#enquire-links-resp}

Esta PDU reconoce que la conexión está activa.

### SMS de varias partes (SMS largos) {#multipart}

Los SMS de varias partes, o SMS largos, son SMS que se envían en varias partes. Debido a limitaciones técnicas en el protocolo de red móvil, un SMS no puede superar los 140 bytes o deberá dividirse. Consulte la sección [Codificación de texto SMS](../../administration/using/sms-protocol.md#sms-text-encoding) para obtener más información sobre el número de caracteres que pueden caber en un SMS.

Cada parte de un mensaje largo es un SMS individual. Estas partes viajan independientemente en la red y son montadas por el teléfono móvil receptor. Para gestionar reintentos y problemas de conectividad, Adobe Campaign envía estas piezas en orden inverso y solicita un SR únicamente en la primera parte del último mensaje que se envía. Dado que el teléfono móvil solo muestra un mensaje cuando se recibe la primera parte, los reintentos de partes adicionales no producirán duplicados en el teléfono móvil.

Se puede establecer el número máximo de SMS por mensaje por envío mediante la configuración **Número máximo de SMS por mensaje** en la **Plantilla de envíos**. Los mensajes que superen este límite fallarán al enviar un mensaje de error con el motivo SMS demasiado largo.

Hay dos maneras de enviar SMS largos:

* **UDH**: la forma predeterminada y recomendada de enviar mensajes largos. En este modo, el conector divide el mensaje en varios `SUBMIT_SM PDU` con información UDH en ellos. Este protocolo es el que utilizan los propios teléfonos móviles. Esto significa que Adobe Campaign tiene el mayor control sobre la generación de mensajes, lo que le permite calcular exactamente cuántas partes se enviaron y cómo se dividieron.

* **message_payload**: la manera de enviar el mensaje largo completo en un solo `SUBMIT_SM PDU`. El proveedor tendrá que dividirlo, lo que significa que es imposible para Adobe Campaign saber exactamente cuántas partes se han enviado. Algunos proveedores requieren este modo, pero le aconsejamos que lo utilice únicamente si no admiten UDH.

Consulte la descripción de los campos `esm_class`, `short_message` y `message_payload` de la [SUBMIT_SM PDU](../../administration/using/sms-protocol.md#information-pdu) para obtener más detalles sobre el protocolo y los formatos.

### Límite de rendimiento y basado en ventanas {#throughput-capping}

La mayoría de los proveedores requieren un límite de rendimiento para cada conexión SMPP. Esto se puede lograr estableciendo un número de SMS en la cuenta externa. Tenga en cuenta que la limitación del rendimiento se produce por conexión, el rendimiento efectivo total es el límite por conexión multiplicado por el número total de conexiones. Esto se detalla en la sección [Conexiones simultáneas](../../administration/using/sms-protocol.md#connection-settings).

Para alcanzar el máximo rendimiento posible, tendrá que ajustar la ventana de envío máxima. La ventana de envío es el número de `SUBMIT_SM PDU` que se puede enviar sin esperar a `SUBMIT_SM_RESP`. Consulte la sección [Configuración de la ventana de envío](../../administration/using/sms-protocol.md#throughput-timeouts) para obtener más detalles.

### SR y administración de errores (“Apéndice B”) {#sr-error-management}

El protocolo SMPP define errores sincrónicos estándar en `RESP PDU`, pero no define códigos de error para SR. Cada proveedor utiliza sus propios códigos de error con su significado.

Se hace una recomendación en la sección del Apéndice B del [Especificación del protocolo SMPP](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (página 167), pero esto no enumera los códigos de error reales ni su significado.

Para adaptarse a la administración de errores, se ha aprovechado el sistema de mensajes de banda ancha de Adobe Campaign para aprovisionar correctamente los errores y su gravedad (difícil, suave, etc.).

Como se mencionó anteriormente, hay dos tipos diferentes de errores:

* respuestas sincrónicas en el `SUBMIT_SM_RESP` que se producen inmediatamente después de enviar el mensaje al SMSC
* los recibos que pueden llegar mucho más tarde cuando el dispositivo móvil recibe el mensaje o cuando se agota el tiempo de espera del mensaje. En ese caso, el error se encuentra en un SR.

Cuando se recibe un SR, el estado y el error se pueden encontrar en su campo `short_message` (por ejemplo, para implementaciones conformes con el Apéndice B). El campo `short_message` de la PDU se denomina generalmente **campo de texto** porque contiene texto en MT. En el caso de SR, contiene información técnica más un subcampo denominado **Texto**. Estos 2 campos son diferentes y `short_message` en realidad contiene el campo **Texto** y otra información.

#### Formato de campo de texto SR {#sr-text-field-format}

La especificación recomienda utilizar este formato para el campo de texto SR. Es una lista de subcampos, separados por espacios con dos puntos para separar el nombre del campo y su valor. Los nombres de campo no distinguen entre mayúsculas y minúsculas.

Ejemplo de un campo de texto SR que coincide con la recomendación del Apéndice B:

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

El campo id es el ID recibido en el `SUBMIT_SM_RESP PDU`, el reconocimiento del MT.

`sub` y `dlvrd` deberían contar la cantidad de piezas enviadas y mensajes enviados, pero Adobe Campaign no lo utiliza, ya que el sistema de banda ancha proporciona una información mejor y más integrada.

Los campos `submit date` y `done date` son marcas de hora indicativas de cuándo se envió el mensaje MT y cuándo el dispositivo móvil envió el mensaje SR. Se esperan algunos problemas con los husos horarios o incluso marcas de hora incorrectas proporcionadas por los móviles con una fecha establecida incorrectamente.

El campo stat es importante porque indica el estado del mensaje. El único estado importante es `DELIVRD`, `UNDELIV` y `REJECTD`. El estado `DELIVRD` indica un resultado exitoso, los otros dos indican un error. Otros valores son posibles, pero suelen ser notificaciones intermedias, por ejemplo, el MT llegó al operador de telefonía móvil, pero no el teléfono móvil. Adobe Campaign ignora estas notificaciones intermedias.

El campo err contiene el código de error específico del proveedor. El proveedor debe proporcionar una tabla de posibles códigos de error junto con su significado para poder interpretar este valor.

Finalmente, el campo de texto en general contiene el principio del texto de MT. Adobe Campaign lo ignora y algunos proveedores no lo transmiten para evitar fugas de PII y consumo de ancho de banda de la red. Se puede utilizar durante la resolución de problemas para localizar el SR que coincide con un MT de prueba más fácilmente leyendo este campo.

### Ejemplo de procesamiento SR en SMPP genérico de Adobe Campaign Standard Extended {#sr-processing}

Este ejemplo muestra el caso de una implementación que sigue a la recomendación del Apéndice B, los valores predeterminados en la cuenta externa y un mensaje SMS MT correcto.

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

En primer lugar, la regex `id extraction` se aplica para extraer el ID y reconciliarlo con el MT correspondiente.

A continuación, la regex `status extraction` y la regex `error code extraction` se aplican para extraer estos campos y se anexan a la cadena.

El mensaje del &quot;broadlog&quot; se construye con esta información y la cadena original sin modificar se anexa como referencia:

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

A continuación, el mensaje se normaliza, eliminando la parte MENSAJE para poder hacer coincidir varios mensajes con los mismos códigos de estado y error.

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

Si el mensaje no se ha aprovisionado ya en la tabla de mensajes de &quot;broadlog&quot;, se creará una nueva entrada, con todo el mensaje como **firstText** y el mensaje normalizado. A continuación, el conector utiliza el éxito y la regex `error` para determinar si ha sido un éxito o un error:

* Si coincide con la regex `success`, se considera un éxito.

* Si coincide con la regex `error`, el mensaje se califica como un error.

* Si ninguna de estas dos regex coincide, se ignora el SR. Podría ser una notificación intermedia, que Adobe Campaign no gestiona.

De forma predeterminada, todos los errores se aprovisionan como errores leves. Esto significa que los errores graves deben aprovisionarse a mano.

### Codificación de texto SMS {#sms-text-encoding}

Siempre debe **ponerse en contacto con el proveedor SMSC en caso de problemas de codificación**. Solo los proveedores de SMSC tienen un conocimiento preciso de la codificación que admiten y de las reglas especiales que pueden aplicarse debido a las limitaciones en su plataforma técnica.

Los mensajes SMS utilizan una codificación especial de 7 bits, a menudo denominada codificación GSM7.

En el protocolo SMPP, el texto de GSM7 se expandirá a 8 bits por carácter para facilitar la resolución de problemas. El SMSC lo empaquetará en 7 bits por carácter antes de enviarlo al dispositivo móvil. Esto significa que el campo `short_message` del SMS puede tener hasta 160 bytes de longitud en el marco SMPP, mientras que está limitado a 140 bytes cuando se envía en la red móvil.

En caso de problemas de codificación, hay que comprobar algunos aspectos importantes:

* Asegúrese de saber qué caracteres pertenecen a cada codificación. GSM7 no admite completamente marcas diacríticas (acentos). Especialmente en francés, donde é y è son parte de GSM7, pero ê, â o ï no lo son. Lo mismo se aplica al español.

* La C con cedilla (ç) está presente solamente en mayúsculas en el alfabeto GSM7, pero algunos teléfonos la procesan en minúsculas o en mayúsculas &quot;inteligentes&quot;. La recomendación general es que se evite completamente y se quite la cedilla o se cambie a UCS-2.

* **No utilice ASCII en SMS** a menos que lo solicite explícitamente el proveedor SMSC. Esta codificación desperdicia espacio porque tiene caracteres de 8 bits y menos cobertura que GSM7. Esta codificación puede ser necesaria para las redes CDMA, utilizadas en Norteamérica.

* Latin-1 no siempre es compatible. Compruebe la compatibilidad con su proveedor SMSC antes de intentar usar Latin-1.

* El conector Adobe Campaign no admite tablas de cambio de idioma nacional. Debe utilizar UCS-2 u otro `data_coding` en su lugar.

* UCS-2 y UTF-16 suelen mezclarse por teléfono. Este problema se produce cuando se utilizan emojis y otros caracteres no presentes en UCS-2.

* La mayoría de los teléfonos no tienen glifos de fuentes para todos los caracteres UCS-2. Los teléfonos inteligentes suelen ser capaces de mostrar caracteres raros con bastante facilidad, pero los teléfonos funcionales generalmente tienen una compatibilidad limitada con lo que es útil en la lengua nativa del país en el que se compraron. Si desea usar emoji o ASCII-art, pruébelo en una amplia variedad de teléfonos antes de enviarlo. La previsualización de Adobe Campaign no simula los glifos que faltan y muestra los símbolos disponibles en el navegador web.

El campo `data_coding` indica qué codificación se utiliza. Un problema importante es que el valor 0 significa codificación SMSC predeterminada en la especificación, que suele referirse a GSM7. Consulte con el socio de SMSC la codificación asociada con `data_coding` = 0 que solo admite Adobe Campaign. Otros valores `data_coding` tienden a seguir la especificación, pero la única manera de estar seguros es consultar con el proveedor SMSC.

El tamaño máximo de un mensaje depende de su codificación. Esta tabla resume toda la información relevante:

| Codificación | Data_coding habitual | Tamaño del mensaje (caracteres) | Tamaño de la parte para SMS de varias partes | Caracteres disponibles |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | Conjunto de caracteres básico GSM7 + extensión (los caracteres extendidos tienen 2 caracteres) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode (varía de un teléfono a otro) |

## Parámetros de cuenta externa de SMPP {#SMPP-parameters-external}

Cada implementación del protocolo SMPP tiene muchas variaciones. Para mejorar la compatibilidad y la adaptabilidad, hay muchos ajustes disponibles para cambiar el comportamiento del conector SMPP. Esta sección describe todos los parámetros y sus efectos en el conector.

### Parámetros generales y enrutamiento {#general-parameters-routing}

**Limitar instancias de MTA para esta cuenta**

Es posible establecer un límite en el número de instancias de MTA permitidas para conectarse al proveedor de SMPP. Cuando se selecciona, puede especificar cuántos MTA se pueden usar como máximo.

Esta opción permite un control más preciso del número de conexiones; consulte [Conexiones simultáneas](../../administration/using/sms-protocol.md#connection-settings).

Si establece un valor mayor que el número de MTA en ejecución, todos los MTA se ejecutarán normalmente: esta opción es solo un límite y no puede generar MTA adicionales.

Si necesita controlar con precisión el número de conexiones, por ejemplo, el requisito del proveedor, se recomienda establecer siempre esta opción aunque la implementación actual tenga el número correcto de MTA en ejecución. Si después se agregan MTA adicionales, se respetará el límite de conexión.

### Configuración de conexión {#connection-settings}

#### Modo de conexión SMPP {#smpp-connection-mode}

Establece la conexión en **transceptor** modo o en separado **transmisor+receptor** modo. Cuando cambie a separado **transmisor+receptor** modo, configuración en **Modo de conexión SMPP** se aplican al transmisor y a la configuración en la **Configuración de conexión del receptor** se aplican a la conexión del receptor, solo si ha marcado la **Usar parámetros diferentes para el receptor** casilla de verificación

#### Nombre de implementación de SMSC {#smsc-implementation-name}

Define el nombre de la implementación de SMSC. Debe configurarse con el nombre de su proveedor. Póngase en contacto con el administrador o con el equipo de entregabilidad para saber qué añadir en este campo. La función de este campo se describe en la sección [gestión de errores SR](../../administration/using/sms-protocol.md#sr-error-management).

#### Servidor {#server}

El nombre DNS o la dirección IP del servidor al que se va a conectar.

#### Puerto {#port}

El puerto TCP al que se va a conectar.

#### Cuenta {#account}

Inicio de sesión de la conexión. Pasado en el campo `system_id` de la PDU BIND.

#### Contraseña {#password}

Contraseña de la conexión SMPP. Pasado en el campo de contraseña de la PDU BIND.

#### Tipo de sistema {#system-type}

Valor pasado en el campo `system_id` de la PDU BIND. Algunos proveedores necesitan un valor específico aquí.

#### Conexiones simultáneas {#simultaneous-connections}

En Adobe Campaign Standard, define el número de conexiones por subproceso SMS y por proceso MTA.
El número de procesos de MTA se determina mediante la implementación: normalmente hay 2 MTA y 1 subproceso. El número de subprocesos se puede cambiar en el archivo config-instance.xml mediante la configuración smppConnectorThreads. Normalmente, hay 1 proceso de MTA por contenedor y 1 subproceso por proceso de MTA.

Fórmula de conexiones totales para Adobe Campaign Standard:

* **Total de conexiones = Conexiones simultáneas * número de subprocesos * número de MTA**

Las conexiones simultáneas se establecen en la cuenta externa, el número de subprocesos se establece en el archivo config-instance.xml (smppConnectorThreads) y el número de MTA se puede limitar en la cuenta externa.

En espacios separados **transmisor/receptor** modo, el número de conexiones anterior representa el número de **transmisor/receptor** pares, lo que significa que habrá el doble del número total de conexiones.

#### Habilitar TLS en SMPP {#enable-TLS}

Utilice TLS para conectarse al proveedor. La conexión se cifrará. La conexión TLS es administrada por la biblioteca OpenSSL. Todo lo aplicable a OpenSSL será verdadero para esta conexión.

#### Habilitar los seguimientos SMPP detallados en el archivo de registro {#enable-verbose-log-file}

Esta configuración elimina todo el tráfico de SMPP en los archivos de registro. A menudo es necesario ajustar los parámetros durante la configuración inicial. Esto debe habilitarse al solucionar problemas del conector y compararse con el tráfico que ve el proveedor.

### Configuración de conexión del receptor {#receiver-connection}

Esta sección solo está visible en el modo separado **transmisor + receptor**.

#### Usar parámetros diferentes para el receptor {#receiver-parameters}

Cuando la casilla está desactivada, se utiliza la misma configuración para el transmisor y el receptor.

Cuando la casilla está activada, la configuración de la sección **Configuración de conexión** se aplicará al transmisor y la configuración en los ajustes de **conexión del receptor** se aplicará al receptor.

**Servidor receptor, puerto, cuenta, contraseña, tipo de sistema**

Esta configuración se aplica al receptor cuando se encuentra en **transmisor+receptor** modo. Funcionan como la parte del transmisor, ver arriba para más detalles.

### Configuración de canal SMPP {#smpp-channel-settings}

#### Permitir transliteración de caracteres {#allow-character-transliteration}

La transliteración es el proceso de encontrar caracteres equivalentes a los que faltan. Por ejemplo, el carácter francés &quot;ê&quot; (e con acento circunflejo) no aparece en la codificación GSM, pero se puede reemplazar por &quot;e&quot; sin afectar a la legibilidad.

Cuando esta casilla no está marcada, la codificación de texto fallará si no puede codificar la cadena exactamente como está.

Cuando esta casilla está activada, la codificación de texto intentará convertir la cadena a una versión aproximada en lugar de generar errores. Si algunos caracteres no tienen equivalente en la codificación de destinatario, la codificación de texto fallará.

Consulte la [Definición de una asignación específica de la configuración de codificaciones](../../administration/using/sms-protocol.md#SMSC-specifics) para obtener una explicación más general del proceso de codificación.

#### Almacenar el MO entrante en la base de datos {#incoming-mo-storing}

Cuando se habilita, el MO entrante se almacena en la tabla inSMS de la base de datos. Esta tabla se puede consultar mediante la actividad de consulta de cualquier flujo de trabajo.

#### Habilitar actualizaciones de KPI en tiempo real durante el procesamiento de SR {#real-time-kpi}

Cuando se habilita, los KPI se actualizan en tiempo real en la página de envío principal cuando se recibe un SR de error.

La desventaja puede ser un bajo rendimiento debido al contenido de la base de datos que genera. Si se deshabilita, las estadísticas se actualizan mediante el flujo de trabajo **syncfromexec**, que se ejecuta cada 20 minutos.

#### Número de origen {#source-number}

Define la dirección de origen predeterminada para los mensajes. Esta configuración solo se aplica si el número de origen se ha dejado vacío en el envío.

De forma predeterminada, el campo de número de origen no se pasa, por lo que el proveedor lo sustituirá por el código corto.

Esto habilita la función de anulación de dirección de remitente/oADC.

#### Código corto {#short-code}

Indica el código corto principal de la cuenta. Si se utilizan varios códigos cortos para esta cuenta o si se desconoce el código corto, deje este campo vacío.

Especificar código corto resulta útil para dos funciones:

* La previsualización mostrará el código corto si no se proporciona ningún número de origen. Reflejará el comportamiento real en el teléfono móvil.

* La configuración de lista de bloqueados de la función de respuesta automática solo envía a cuarentena al usuario de un código corto específico.

#### TON/NPI de origen, TON de destino/NPI {#ton-npi}

El TON (Tipo de número) y el NPI (Indicador del plan de numeración) se describen en la sección 5.2.5 de la [especificación SMPP 3.4](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (página 117). Estos valores deben configurarse según las necesidades del proveedor.

Se transmiten tal como están en los campos `source_addr_ton`, `source_addr_npi`, `dest_addr_ton` y `dest_addr_npi` de `SUBMIT_SM PDU`.

#### Tipo de servicio {#service-type}

Este campo se transmite tal como está en el campo `service_type` del `SUBMIT_SM PDU`. Configure esto según las necesidades del proveedor.

### Rendimiento y tiempo de espera {#throughput-timeouts}

Esta configuración controla todos los aspectos de tiempo del canal SMPP. Algunos proveedores requieren un control muy preciso de la velocidad de mensajes, la ventana y los tiempos de reintento. Esta configuración debe establecerse en valores que coincidan con la capacidad del proveedor y las condiciones indicadas en su contrato.

#### Ventana de envío {#sending-window}

La ventana es el número de `SUBMIT_SM PDU` que se pueden enviar sin esperar una `SUBMIT_SM_RESP` coincidente.

Ejemplo de una transmisión con una ventana máxima de 4:

![](assets/do-not-localize/sms_protocol_2.png)

La ventana ayuda a aumentar el rendimiento cuando el vínculo de red tiene una latencia alta.  El valor de la ventana debe ser al menos el número de SMS/s multiplicado por la latencia del vínculo en segundos, de modo que el conector nunca está esperando un `SUBMIT_SM_RESP` antes de enviar el siguiente mensaje.
Si la ventana es demasiado grande, puede enviar más mensajes de duplicado en caso de problemas de conexión. Además, la mayoría de los proveedores tienen un límite muy estricto para la ventana y rechazan los mensajes que sobrepasan el límite.

Calcular la fórmula óptima de la ventana de envío:

* Mida la latencia máxima entre `SUBMIT_SM` y `SUBMIT_SM_RESP`.

* Multiplicar este valor en segundos hasta el rendimiento máximo de MT. Esto proporcionará el valor óptimo de la ventana de envío.

Ejemplo: Si tiene 300 SMS/s configurados en el rendimiento máximo de MT y hay una latencia de 100 ms entre `SUBMIT_SM` y `SUBMIT_SM_RESP` en promedio, el valor óptimo sería `300×0.1 = 30`.

#### Rendimiento máximo de MT {#max-mt-throughput}

Número máximo de MT por segundo y por conexión. Esta configuración se aplica estrictamente y el MTA nunca insertará mensajes más rápido que este límite. Resulta útil para los proveedores que requieren una limitación precisa.

Para conocer el límite de rendimiento total, multiplique este número por el número total de conexiones, tal como se detalla en la fórmula anterior.

0 significa que no hay límite, el MTA enviará MT lo más rápido posible.

En general, se recomienda mantener esta configuración por debajo de 1000, ya que es imposible garantizar un rendimiento preciso por encima de este número a menos que se haya realizado una evaluación adecuada de la arquitectura final. Si necesita un rendimiento superior a 1000, póngase en contacto con su proveedor. Puede ser mejor aumentar el número de conexiones para superar los 1000 MT/s.

#### Tiempo antes de la reconexión {#time-reconnection}

Cuando se pierde la conexión TCP, el conector esperará este número de segundos antes de intentar realizar una conexión.

#### Período de caducidad del MT {#expiration-period}

Tiempo de espera entre `SUBMIT_SM` y su coincidencia `SUBMIT_SM_RESP`. Si el `RESP` no se recibe a tiempo, el mensaje se considerará fallido y se aplicará la política de reintentos global del MTA.

#### Tiempo de espera de vínculo {#bind-timeout}

Tiempo de espera entre el intento de conexión TCP y la respuesta `BIND_*_RESP`. Cuando se agota el tiempo de espera, la conexión se cierra mediante el conector de Adobe Campaign y esperará tiempo antes de volver a conectarse antes de intentarlo de nuevo.

#### período enquire_link {#enquire-link-period}

`enquire_link` es un tipo especial de PDU enviado para mantener la conexión viva. Este período es en segundos. El conector de campaña solo envía `enquire_link` cuando la conexión está inactiva para conservar el ancho de banda. Si no se recibe ningún RESP después de dos veces este período, la conexión se considerará muerta y se activará un proceso de reconexión.

### Detalles de SMSC {#SMSC-specifics}

Estas configuraciones son ajustes avanzados que adaptan el conector de Adobe Campaign a la mayoría de las peculiaridades de implementación de SMPP.

#### Defina una asignación específica de codificaciones {#encoding-specific-mapping}

Consulte la sección [Codificación de texto SMS](../../administration/using/sms-protocol.md#sms-text-encoding) para obtener más información sobre la codificación de texto.

Esta configuración le permite definir una asignación de codificación personalizada, diferente de la especificación. Podrá declarar una lista de codificaciones, junto con su valor `data_coding`.

El MTA intentará codificar usando la primera codificación de la lista. Si falla, intentará usar la siguiente codificación en la lista, etc. Si no se puede utilizar ninguna codificación para codificar el mensaje, se producirá un error. Una vez encontrada la codificación, el MTA creará el `SUBMIT_SM PDU` con el texto codificado y el campo establecido `data_coding` con el valor especificado en la tabla.

El orden de los elementos de la tabla es importante: las codificaciones prueban de arriba abajo. Debe colocar la codificación más barata o recomendada en la parte superior de la lista, seguida de codificaciones más y más caras.

Tenga en cuenta que la UCS-2 nunca fallará, ya que puede codificar todos los caracteres admitidos en Adobe Campaign y que la longitud máxima de un SMS UCS-2 es mucho menor: solo 70 caracteres.

También puede utilizar esta configuración para forzar que una codificación específica se utilice siempre declarando solo 1 línea en la tabla de asignación.

La asignación predeterminada que se utiliza cuando la casilla de verificación no está marcada equivale a la siguiente tabla:

| data_coding | Codificación |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

Esto significa que el MTA intentará codificar el mensaje en GSM. Si tiene éxito, lo enviará con `data_coding` establecido en 0.

Si el mensaje no se puede codificar en GSM, se codificará en UCS-2 y se establecerá `data_coding` en 8.

#### Habilitar message_payload {#enable-message-payload}

Cuando no se selecciona, los SMS largos se dividen por el MTA y se envían en múltiples `SUBMIT_SM PDU`s con UDH. El mensaje será recompuesto por el teléfono móvil según los datos UDH.

Cuando se selecciona, se envían SMS largos en una PDU SUBMIT_SM, colocando el texto en el campo opcional message_payload. Consulte la [especificación del SMPP](../../administration/using/sms-protocol.md#ACS-SMPP-connector) para obtener más información al respecto.

Si esta función está habilitada, Adobe Campaign no podrá contar las partes del SMS de forma individual: todos los mensajes se contarán como enviados en una parte.

#### Enviar el número de teléfono completo {#send-full-phone-number}

Cuando esta casilla de verificación no está activada, solo se envían dígitos del número de teléfono al proveedor (`destination_addr` campo del campo `SUBMIT_SM`). Este es el comportamiento predeterminado, ya que el indicador de número internacional, normalmente un prefijo +, se sustituye por los campos TON y NPI en el SMPP.

Cuando se marca la casilla de verificación, el número de teléfono se envía tal cual, sin preprocesamiento ni espacios potenciales, + prefijo o signos de almohadilla/asterisco.

Esta función también afecta al comportamiento de la función de respuesta automática de la lista de bloqueados: cuando la casilla de verificación no está marcada, se agrega un prefijo + a los números de teléfono insertados en la tabla de cuarentena para compensar la eliminación del prefijo + del número de teléfono por el protocolo SMPP mismo.

#### Omitir comprobación de certificado TLS {#skip-tls}

Cuando TLS está habilitado, omitir todas las comprobaciones de certificado.

Cuando se selecciona, la conexión ya no es segura, por lo que no debe habilitarse en producción.

Puede resultar útil para depurar o probar.

#### Enlazar TON/NPI {#bind-ton-npi}

TON (tipo de número) y NPI (indicador del plan de numeración) descritos en la sección 5.2.5 de la especificación [del SMPP 3.4](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (página 117). Estos valores deben ajustarse a lo que el proveedor necesite.

Se transmiten tal cual en los campos `addr_ton` y `addr_npi` de la BIND PDU.

#### Intervalo de direcciones {#address-range}

Se envía tal cual en el campo address_range del BIND PDU. Este valor debe ajustarse a lo que necesite el proveedor.

#### Cuenta de reconocimiento de ID no válida {#invalid-id}

Limita el número de **Mensaje de ID no válido** `DELIVER_SM_RESP` que se puede enviar para un único SR.

**Esto solo debe usarse para solucionar problemas como solución alternativa** y se establece en 0 en condiciones normales.

Ejemplo de Fox, cuando se establece en 2:

* El proveedor envía un SR (`DELIVER_SM`) con el ID &quot;1234&quot;.

* No se encontró el ID &quot;1234&quot; en la base de datos.

* El conector cuenta 1 error **ID no válido** para ese ID, por lo que envía `DELIVER_SM_RESP` con el código de error &quot;ID del mensaje no válido&quot; (comportamiento normal).

* El proveedor reintenta el mismo SR con el ID &quot;1234&quot;.

* El ID &quot;1234&quot; aún no se encuentra en la base de datos.

* El conector cuenta 2 errores **ID no válido** para ese ID, por lo que envía `DELIVER_SM_RESP` &quot;OK&quot;, aunque no se haya procesado correctamente.

* Esta función está diseñada para vaciar los búferes SR en el lado del proveedor cuando el bloque SR no válido legitima que los mensajes no se puedan procesar.

Si este campo se establece en 0, se deshabilita el mecanismo donde **ID de mensaje no válido** siempre se devuelve, este es un comportamiento normal.

Al establecer este campo en 1, el conector siempre responde &quot;OK&quot; aunque el ID no sea válido. Esto debe establecerse en 1 solamente bajo supervisión, para la resolución de problemas y durante el mínimo tiempo, p. ej.: para recuperarse de un problema del lado del proveedor.

#### Extracción del regex del ID en el SR {#regex-extraction}

El formato SR no se aplica estrictamente en la especificación de protocolo SMPP. Es solo una recomendación descrita en el [Apéndice B](../../administration/using/sms-protocol.md#sr-error-management) (página 167) del pliego de condiciones. Algunos implementadores SMPP dan un formato diferente a este campo, por lo que Adobe Campaign necesita una forma de extraer el campo correcto.

De forma predeterminada, captura hasta 10 caracteres alfanuméricos después de `id:`.

El regex debe tener exactamente un grupo de captura con una parte incluida entre paréntesis. Los paréntesis deben rodear la parte del ID. El formato regex es PCRE.

Al ajustar esta configuración, asegúrese de incluir el mayor contexto posible para evitar activaciones falsas. Si hay prefijos específicos, como `id:` en el estándar, inclúyalos en la regex. Utilice también delimitadores de palabras (\b) tanto como sea posible para evitar capturar texto en medio de una palabra.

No incluir suficiente contexto en la regex puede introducir un pequeño defecto de seguridad: el contenido real del mensaje puede incluirse en el SR. Si solo coincide con un formato de ID específico sin contexto, p. ej., un UUID, es posible que esté analizando el contenido de texto real, p. ej., un UUID incrustado en el campo de texto, en lugar del ID.

#### Regex aplicada para determinar el estado correcto/de error {#regex-applied}

Cuando se encuentran mensajes con una combinación de campo stat/err desconocida, estas regex se aplican en el campo estadísticas (&quot;stat&quot;) para determinar si el SR fue un éxito o un error. Se omiten los valores de SR con los valores estadísticos que no coinciden con ninguna de estas expresiones regulares.

De forma predeterminada, los valores de estadística comienzan por `DELIV`, p. ej.: `DELIVRD` en el [Apéndice B](../../administration/using/sms-protocol.md#sr-error-management), se considera que se ha entregado correctamente y todos los valores de estadística que coincidan con errores, p. ej.: `REJECTED`, `UNDELIV`, se consideran errores.

#### Formato de ID en reconocimiento MT {#id-format-mt}

Indica el formato del ID devuelto en el campo `message_id` del `SUBMIT_SM_RESP PDU`.

* **No modificar**: El ID se almacena tal cual en la base de datos, como texto con codificación ASCII. No hay ningún procesamiento previo ni filtrado.

* **Número decimal** : Se espera que el ID sea un número decimal en formato ASCII. Cuando se utiliza este ajuste, se eliminan los espacios iniciales y finales y los ceros al inicio.

* **Número hexadecimal**: Se espera que el ID sea un número hexadecimal en formato ASCII, sin 0x inicial ni h final. El ID se convierte a continuación en un número decimal antes de almacenarse en la base de datos.

* **Cadena hexadecimal**: Se espera que el ID sea un texto con codificación ASCII que es en sí mismo una cadena de bytes codificados como hexadecimales. P. ej.: en la PDU encontrará `0x34 0x31 0x34 0x32 0x34 0x33`, que se traduce como ASCII &quot;414243&quot;. A continuación, esta cadena se descodifica como una cadena hexadecimal de bytes y se obtiene &quot;ABC&quot; como resultado: almacenará el ID &quot;ABC&quot; en la base de datos.

#### Formato de ID en SR {#id-format-sr}

Esto indica el formato del ID capturado por la regex `Extraction` del ID en el SR. Los valores tienen el mismo significado y el mismo comportamiento que el formato de MT anterior.

**ID de SR o código de error en el campo opcional**

Si se selecciona, el contenido de los campos opcionales se anexará al texto procesado por las expresiones regulares anteriores. El texto tendrá el formato `0xTAG:VALUE`, `0xTAG` siendo el valor hexadecimal de 4 dígitos de la etiqueta en mayúsculas, p. ej.: `0x002E`.

Por ejemplo, es posible que desee capturar el ID en el campo `receipted_message_id`. Para ello, active esta casilla de verificación y el siguiente texto se agrega al estado:

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

En este ejemplo, 0x001E es la etiqueta del campo opcional y UUID es el valor del campo.

Para capturar este valor, ahora puede establecer la siguiente regex en la regex de Extracción del ID en el campo SR:

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>Solo puede capturar campos opcionales que tengan valores de texto (ASCII/UTF-8). Concretamente, los campos binarios no se pueden capturar de forma fiable con el sistema regex actual.

**ID de SR o código de error en el campo de texto**

Si se selecciona, el campo **Texto** se mantendrá durante el procesamiento del texto de estado del SR.

Esto resulta útil si el proveedor coloca datos importantes en este campo, como el ID o el estado. Normalmente, este campo se puede descartar de forma segura, ya que puede contener texto con una codificación que no sea ASCII e interrumpir el procesamiento de regex.

Si se habilita esta opción, puede que se produzca un error de seguridad muy pequeño si la regex del ID `Extraction` en el campo SR no es lo suficientemente específico. El contenido del campo **Texto** puede analizarse como un ID y un atacante puede utilizarlo para inyectar ID falsificados, lo que puede conducir a una situación de denegación de servicio parcial.

**Etiqueta de ID de servicio**

Permite añadir un TLV personalizado. Este campo establece la porción de etiqueta. El valor se puede personalizar por envío en el valor **ID de servicio o programa** en los parámetros avanzados del envío.

Esta configuración solo permite añadir una opción TLV por mensaje.

>[!NOTE]
>
>A partir de la versión 21.1, ahora es posible añadir más de un parámetro opcional. Para obtener más información, consulte [esta sección](../../administration/using/sms-protocol.md#automatic-reply-tlv).

### Respuesta automática enviada al MO {#automatic-reply}

Esta función permite responder texto rápidamente a MO y controlar el envío de código corto a la lista de bloqueados.

Las columnas **Palabra clave** y **Código corto** definen condiciones para la activación de la respuesta automática. Si coinciden ambos campos, se envía el MO y se activa la acción adicional. Para especificar un comodín, debe dejar el campo vacío. La palabra clave coincide con la primera palabra alfanumérica del texto MO, omitiendo la puntuación y los espacios iniciales. Esto significa que el campo **Palabra clave** no puede contener espacios y debe ser una sola palabra.

La configuración **Palabra clave** es un prefijo. Por ejemplo, si especifica &quot;AD&quot;, coincidirá con &quot;AD&quot;, &quot;ADAPT&quot; y &quot;ADOBE&quot;. Si tiene varias palabras clave con un prefijo común, debe prestar atención al orden, ya que las palabras clave se procesan de arriba a abajo.

La columna **Respuesta** es el texto que se va a responder. No hay personalización disponible en este campo. Si deja este campo vacío, no se responderá ningún mensaje, pero la acción adicional se activará de todos modos.

La columna **Acción adicional** proporciona una acción adicional cuando tanto la **Palabra clave** como el **Código corto** coinciden, el código corto vacío coincide con todos los códigos cortos. Puede enviar a la cuarentena o quitar de la cuarentena, ningún valor responde al texto. Si especifica una **Acción adicional** pero deja vacío el campo **Respuesta**, la acción se ejecutará pero no se enviará ninguna respuesta. La cuarentena solo se aplica al código corto especificado o a todos los códigos cortos si el campo se deja vacío.

>[!IMPORTANT]
>
>La configuración del número de teléfono completo de envío afecta al comportamiento del mecanismo de cuarentena de respuesta automática: si el número de teléfono de envío completo no está marcado, el número de teléfono puesto en cuarentena estará marcado con un signo más (&quot;+&quot;) para que sea compatible con el formato de número de teléfono internacional.

Todas las entradas de la tabla se procesan en el orden especificado, hasta que una regla coincida. Si varias reglas coinciden con un MO, solo se aplicará la regla superior.

### Parámetros opcionales de respuesta automática (TLV) {#automatic-reply-tlv}

A partir de la versión 21.1, puede añadir parámetros opcionales al mensaje MT de respuesta automática. Se añaden como parámetros TLV opcionales al `SUBMIT_SM PDU` de la respuesta, tal como se describe en la sección 5.3 del [Especificación de SMPP](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)(página 131).

Para obtener más información sobre los parámetros opcionales, consulte [sección](../../administration/using/sms-protocol.md#smpp-optional-parameters).

## Parámetros de plantilla de envíos de SMS {#sms-delivery-template-parameters}

Algunos parámetros se pueden definir por la plantilla de envíos.

### Del campo {#from-field}

Este campo es opcional. Permite anular la dirección del remitente (oADC). El contenido de este campo se coloca en el campo `source_addr` del `SUBMIT_SM PDU`.

El campo está limitado a 21 caracteres por la especificación del SMPP, pero algunos proveedores pueden permitir valores más largos. Tenga en cuenta también que en algunos países se pueden aplicar restricciones muy estrictas, como longitud, contenido, caracteres permitidos.

### Parámetros de envío {#delivery-parameters}

#### Número máximo de SMS por mensaje {#maximum-sms}

Esta configuración solo funciona si la configuración **Carga útil del mensaje** está deshabilitada. Para obtener más información, consulte [página](../../administration/using/configuring-sms-channel.md). Si el mensaje requiere más SMS que este valor, se activará un error.

El protocolo SMS limita los SMS a 255 partes, pero algunos teléfonos móviles tienen problemas para reunir mensajes largos con más de 10 partes, el límite depende del modelo exacto. Le recomendamos que no pase más de 5 partes por mensaje.

Debido a cómo funcionan los mensajes personalizados en Adobe Campaign, el tamaño de los mensajes puede variar. Si tiene una gran cantidad de mensajes largos, el coste del envío podría aumentar.

#### Modo de transmisión {#transmission-mode}

Este campo indica el tipo de SMS que desea transferir: mensajes normales o flash, almacenados en el móvil o en la tarjeta SIM.

Esta configuración se transmite en el campo opcional `dest_addr_subunit` de `SUBMIT_SM PDU`.

* **Sin especificar** no envía ningún campo opcional en la PDU.

* **Flash** establece el valor en 1. Envía un mensaje flash que aparece en el dispositivo móvil y no se almacena en la memoria.

* **Normal** establece el valor en 0. Envía un mensaje normal.

* **Guardar en un móvil** establece el valor en 2. Le dice al teléfono que almacene el SMS en la memoria interna.

* **Guardar en un terminal** establece el valor en 3. Le dice al teléfono que almacene el SMS en la tarjeta SIM.

#### Período de validez {#validity-period}

El período de validez se transmite en el campo `validity_period` del `SUBMIT_SM PDU`. La fecha siempre está formateada con un formato de hora UTC absoluta (el campo de fecha finalizará con &quot;00+&quot;).

#### Parámetros opcionales de SMPP (TLV) {#smpp-optional-parameters}

A partir de la versión 21.1, puede añadir varios parámetros opcionales a cada MT enviado para esta entrega. Estos parámetros opcionales se añaden a `SUBMIT_SM PDU` de la respuesta, tal como se describe en la sección 5.3 del [Especificación de SMPP](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)(página 131).

Cada fila de la tabla representa un parámetro opcional:

* **Parámetro**: descripción del parámetro. No se transmite al proveedor.
* **ID de etiqueta**: etiqueta del parámetro opcional. Debe ser hexadecimal válido, con el formato 0x1234. Los valores no válidos provocarán un error de preparación de la entrega.
* **Valor**: Valor del campo opcional. Se codifica como UTF-8 cuando se transmite al proveedor. El formato de codificación no se puede cambiar, no es posible enviar valores binarios ni utilizar diferentes codificaciones, como UTF-16 o GSM7.

Si algún parámetro opcional tiene el mismo **ID de etiqueta** como el **ID de etiqueta de servicio** definido en la cuenta externa, prevalecerá el valor definido en esta tabla.

## Conector SMPP {#ACS-SMPP-connector}

![](assets/do-not-localize/sms_protocol_3.png)

Las flechas representan el flujo de datos.

Lo más importante que debe tener en cuenta aquí es que hay varios hilos de conector SMPP. Todos estos subprocesos son idénticos y comparten la misma configuración. Por este motivo, el número de conexiones siempre se multiplica por el número de subprocesos.

El cliente no puede cambiar el número de subprocesos porque requiere cambiar los archivos de configuración.

### Descripción del comportamiento del conector SMPP {#behavior-smpp-connector}

#### Entradas de MT, SR y “broadlog” que coinciden {#matching-mt-sr}

En Adobe Campaign, un mensaje es una entrada de broadlog. En Adobe Campaign Standard, los conectores externos solo necesitan conocer la tabla de &quot;broadlog&quot; en funcionamiento: `nmsBroadLogExec`. Un flujo de trabajo se encarga de copiar las entradas de &quot;broadlog&quot; a sus dimensiones de objetivo específicas (nmsBroadLogXXX).

Lamentablemente, SMPP no permite enviar un ID junto con un mensaje: el proveedor da un ID de MT a cada MT y, a continuación, proporciona uno o más SR con el mismo ID.

El ID proporcionado por el proveedor se almacena en la variable `sProviderId` columna de `nmsBroadLogExec` tabla. SR siempre llega después de que el MT se haya enviado y reconocido correctamente, pero a veces puede llegar sin orden, conocido en Adobe Campaign como SR sobresaliente. El subproceso de procesamiento almacena estos SR temporalmente en la RAM hasta que llega la información completa.

Cuando se reconoce un mensaje MT (`SUBMIT_SM_RESP`), `sProviderId` se actualiza inmediatamente en la base de datos.

Cada SR se procesa individualmente mediante subprocesos de procesamiento SMPP. Este proceso es seudosincrónico: se ve como sincrónico desde el exterior, pero se implementa internamente con implementaciones impulsadas por eventos. Los SR solo se reconocen cuando el registro general se ha actualizado correctamente; si se produce un error, se rechaza el SR.

Este es el proceso aplicado a cada SR:

* El ID del SR se extrae mediante una expresión regular.
* La ID se busca en `nmsBroadLogExec:sProviderId`.
* El estado y el código de error se extraen del SR mediante expresiones regulares.
* El mecanismo de mensajes del &quot;broadlog&quot; se utiliza para clasificar el error y encontrar el ID del mensaje del &quot;broadlog&quot;.
* El &quot;broadlog&quot; se actualiza con toda la información anterior.
* Se reconoce el SR.

La comprobación de los pasos anteriores requiere lo siguiente **Habilite seguimientos detallados del SMPP** para comprobar manualmente que todos los pasos se aplican correctamente. Esto es necesario cada vez que Adobe Campaign se conecta a un nuevo proveedor SMPP.

## Antes de empezar a usarlo {#checklist}

Esta lista de verificación le proporciona una lista de las cosas que debe comprobar antes de empezar a usarlo. Una configuración incompleta puede provocar muchos problemas.

### Comprobación de conflictos en la cuenta externa {#external-account-conflict}

Compruebe que no tiene cuentas externas de SMS antiguas. Si deja desactivada la cuenta de prueba, corre el riesgo de que se vuelva a habilitar en el sistema de producción y se generen posibles conflictos.

Compruebe que ninguna otra instancia se conecte a esta cuenta. En particular, asegúrese de que el entorno de ensayo no se conecta a la cuenta. Algunos proveedores admiten esto, pero requiere una configuración muy específica tanto en el lado de Adobe Campaign como en la plataforma del proveedor.

Si necesita tener varias cuentas en la misma instancia de Adobe Campaign que se conecten al mismo proveedor, póngase en contacto con el proveedor para asegurarse de que realmente se distinguen las conexiones entre estas cuentas. Si tiene varias cuentas con el mismo inicio de sesión necesita una configuración adicional.

### Habilitación de los seguimientos detallados del SMPP durante las comprobaciones {#enable-verbose}

Siempre debe habilitar los seguimientos detallados del SMPP durante las comprobaciones.
Incluso si no puede comprobar los registros usted mismo, será más fácil para la asistencia técnica ayudarle.

### Prueba de SMS {#test}

* **Envíe SMS con todo tipo de caracteres**
Si necesita enviar un SMS con caracteres que no sean GSM o ASCII, intente enviar algunos mensajes con tantos caracteres diferentes como sea posible. Si configura una tabla de asignación de caracteres personalizada, envíe al menos un SMS para todos los valores `data_coding` posibles.

* **Verifique que SR se procesa correctamente**
El SMS debe marcarse como recibido en el registro de envíos. El registro de envíos debe tener el siguiente aspecto:
  `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
Compruebe que ha cambiado el nombre del proveedor de envío. El registro de envíos nunca debe contener **SR genérico** en entornos de producción.

* **Compruebe que se procesan los MO**
Si necesita procesar los MO (respuestas automáticas, almacenar los MO en la base de datos, etc.) intente realizar algunas pruebas. Envíe algunos SMS para cada una de las palabras clave de respuesta automática y compruebe si la respuesta es lo suficientemente rápida, no más de unos segundos.
Compruebe en el registro que Adobe Campaign responde con `DELIVER_SM_RESP` correctamente (command_status=0).

### Compruebe las PDU {#check-pdus}

Aunque los mensajes parezcan correctos, es importante comprobar que las PDU están formateadas correctamente.

Este paso es necesario cuando se conecta a un proveedor que no estaba conectado a Adobe Campaign anteriormente.

#### BIND {#bind}

Verifique que `BIND_* PDUs` se envíen correctamente. Lo más importante que hay que comprobar es que el proveedor siempre devuelve `BIND_*_RESP PDUs` (command_status = 0) correctamente.

Compruebe que no hay demasiadas `BIND_* PDU`. Si hay demasiados, podría indicar que la conexión es inestable. Consulte la sección [Problemas con conexiones inestables](../../administration/using/sms-protocol.md#issues-unstable-connection) para obtener más información.

#### ENQUIRE_LINK {#enquire-link-pdus}

Compruebe que las `ENQUIRE_LINK PDU` se intercambian regularmente cuando la conexión está inactiva.

#### SUBMIT_SM / DELIVER_SM {#submit-sm-deliver-sm}

Envíe un mensaje y luego busque en los registros sus correspondientes `SUBMIT_SM`, `SUBMIT_SM_RESP`, `DELIVER_SM` y `DELIVER_SM_RESP PDU`.

Con el `SUBMIT_SM PDU`:

* Compruebe que `data_coding` es correcto, 0 de forma predeterminada.
* Compruebe que `short_message` está codificado correctamente. Intente descodificarlo con un convertidor hexadecimal que admita varias codificaciones.

Con el `SUBMIT_SM_RESP PDU`:

* Compruebe que se ha realizado correctamente, command_status = 0.
* Compruebe que su cuerpo contiene un ID formateado correctamente seguido de un byte &#39;0&#39;.

Con el `DELIVER_SM PDU`:

* Descodificar el campo hexadecimal `short_message`.
* Compruebe con una herramienta de comprobación de regex que la expresión regular definida en la regex `Extraction` del ID en el SR devuelve exactamente un grupo de captura y que captura el ID completo en el mensaje.
* Compruebe que el ID extraído coincide con el de `SUBMIT_SM_RESP`.
* Compruebe que la expresión regular definida en la regex `Extraction` del estado en el SR devuelve el contenido del campo de estadística.
* Compruebe que la expresión regular definida en la regex `Extraction` del error en el SR devuelve el contenido del campo error.

Con el `DELIVER_SM_RESP PDU`:

* Compruebe que se envió rápidamente después de recibir `DELIVER_SM PDU`, por lo general menos de 1 segundo.
* Compruebe que se ha realizado correctamente, command_status = 0.

### Pregunte al proveedor si todo está bien {#provider}

Aunque el SMS se haya enviado correctamente, póngase en contacto con el proveedor para ver si todo está en orden.

### Deshabilite los seguimientos detallados del SMPP {#disable-verbose}

Una vez completadas todas las comprobaciones, lo último que debe hacer es **Deshabilitar los seguimientos detallados del SMPP** para no generar demasiados registros. Puede volver a activarlos para solucionar los problemas incluso en sistemas de producción.

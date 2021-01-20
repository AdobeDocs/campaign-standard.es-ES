---
solution: Campaign Standard
product: campaign
title: Solución de problemas de SMS
description: Solución de problemas de SMS
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 80e4f752a1b9b6c8b0125a502c05c19796e98104
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 0%

---


# Solución de problemas de SMS {#sms-troubleshooting}

## Conflicto entre diferentes cuentas externas {#external-account-conflict}

Si la instancia tiene varias cuentas externas SMS, debe comprobar que los problemas no son causados por un conflicto entre cuentas externas.

Adobe Campaign trata las cuentas externas como entidades no relacionadas.

Si tiene varias cuentas, siga este procedimiento para aislar la cuenta externa que causa problemas:

1. Deshabilite todas las cuentas externas.
1. Habilitar una cuenta externa.
1. Trata de reproducir el problema.
1. Si el problema inicial no siempre aparece, realice una cantidad razonable de intentos antes de concluir.
1. Si el problema no aparece con esa única cuenta, desactívela y reiníciela en el paso 2 de la cuenta siguiente.

Una vez que ha comprobado cada cuenta individualmente, existen dos escenarios posibles:

* **El problema apareció en una o varias cuentas**

   En este caso, puede aplicar otros procedimientos de resolución de problemas en cada cuenta de forma individual. Es mejor desactivar otras cuentas al diagnosticar una cuenta para reducir el tráfico de red y el número de registros.

* **El problema no aparecía cuando solo una cuenta estaba activa en cualquier momento**

   Tiene un conflicto entre cuentas. Como se mencionó anteriormente, Adobe Campaign trata las cuentas individualmente, pero el proveedor puede tratarlas como una sola cuenta.

   * Utiliza diferentes combinaciones de inicio de sesión y contraseña entre todas las cuentas.
Tendrá que ponerse en contacto con el proveedor para diagnosticar conflictos potenciales de su parte.

   * Algunas de las cuentas externas comparten la misma combinación de inicio de sesión y contraseña.
El proveedor no tiene forma de saber de qué cuenta externa proviene el `BIND PDU`, por lo que trata todas las conexiones de las cuentas múltiples como una sola. Es posible que hayan enrutado MO y SR de manera aleatoria sobre las dos cuentas, causando problemas.
Si el proveedor admite varios códigos cortos para la misma combinación de inicio de sesión y contraseña, tendrá que preguntarles dónde colocar ese código corto en el `BIND PDU`. Tenga en cuenta que esta parte de información debe colocarse dentro de `BIND PDU` y no en `SUBMIT_SM`, ya que `BIND PDU` es el único lugar que permitirá los MO de enrutamiento correctamente.
Consulte la sección [Información en cada tipo de PDU](../../administration/using/sms-protocol.md#information-pdu) anterior para saber qué campo está disponible en `BIND PDU`, generalmente agrega el código corto en `address_range`, pero eso requiere soporte especial del proveedor. Póngase en contacto con ellos para saber cómo esperan enrutar varios códigos cortos de forma independiente.
Adobe Campaign admite el manejo de varios códigos cortos en la misma cuenta externa.

## Problema con la cuenta externa en general {#external-account-issues}

* Investigue si el conector se ha cambiado recientemente y quién lo ha cambiado (compruebe las Cuentas externas como grupo).

   ```
   select saccount, (sserver ||':'||sport) as serverPort, iextaccountid, CASE WHEN N0.iactive=1 THEN 'Yes' ELSE 'No' END as "(x) Enabled",
   
   (select X1.sname from xtkoperator X1 where N0.icreatedbyid = X1.ioperatorid) as "Created By",
   
   (select X1.sname from xtkoperator X1 where N0.imodifiedbyid = X1.ioperatorid) as "Last Modified By",
   
   N0.slabel as "External Account", N0.tslastmodified as "LastModifiedDate"
   
   from nmsextaccount N0 LEFT JOIN xtkoperator X0 ON (N0.icreatedbyid=X0.ioperatorid) order by 8 DESC LIMIT 50;
   ```

* Investigar (en el directorio /postupgrade) si el sistema se ha actualizado y cuándo
* Investigue si algún paquete que afecte a SMS puede haber sido actualizado recientemente (/var/log/dpkg.log).

## Problema al conectarse al proveedor {#issue-provider}

* Si el `BIND PDU` devuelve un código `command_status` distinto de cero, pida al proveedor más información.

* Compruebe que la red está configurada correctamente para que la conexión TCP se pueda establecer con el proveedor.

* Pida al proveedor que compruebe que ha agregado correctamente las IP a la lista de permitidos de la instancia de Adobe Campaign.

* Compruebe la configuración de **Cuenta externa**. Pregunte al proveedor el valor de los campos.

* Si la conexión es correcta pero inestable, consulte la sección [Problema con conexiones inestables](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Si los problemas de conexión son difíciles de diagnosticar, una captura de red puede proporcionar información. Asegúrese de que la captura de red se ejecuta simultáneamente mientras que el problema aparece para él se puede analizar de forma eficaz. También debe tener en cuenta la hora exacta en la que aparece el problema.

## Problemas con la conexión inestable {#issues-unstable-connection}

Una conexión se considera inestable si se produce alguna de las siguientes situaciones:

* Reiniciar el MTA arreglará las cosas temporalmente. Significa que una conexión inestable desencadena la limitación de MTA en Adobe Campaign Standard, reiniciando el MTA borra la limitación. Ocurrirá de nuevo hasta que se encuentre la causa raíz.

* El proveedor envía `UNBIND PDU`s.

* `enquire_link` tiempos de espera agotados, ya sea en el lado de Adobe Campaign o en el del proveedor. Puede ver `ENQUIRE_LINK_RESP` con un código de error distinto de cero en ese caso.

* Hay muchos `BIND PDU`s. No debe haber más de unos pocos durante un día, según el número de conexiones. Más de una PDU BIND por hora debe estar alertando.

Cómo solucionar los problemas de estabilidad de la conexión:

* Las conexiones inestables rara vez son la causa principal, a menudo es el resultado de otro problema que desencadena una desconexión. La prioridad es encontrar la causa raíz.

* Habilite trazos SMPP detallados. Necesitará que vean lo que sucede cuando se reinicia la conexión.

* Si el proveedor envía `BIND PDU`s, algo podría estar mal. Pregunte al proveedor por qué se envía `UNBING`.

* Realizar una captura de red es a veces la única manera de ver cómo se cierra la conexión.

* Si el proveedor cierra las conexiones enviando un paquete `TCP FIN` o `TCP RST`, pregunte a su proveedor más información.

* Si el proveedor cierra la conexión después de enviar un error limpio como `DELIVER_SM_RESP` con un código de error, deberá corregir su conector de lo contrario, lo que impedirá que se transmitan otros tipos de mensajes y activará la limitación de MTA. Esto es especialmente importante en el modo transceptor, donde el cierre de la conexión afecta tanto a MT como SR.

## Problema al enviar un mensaje MT (SMS regular enviado a un usuario final){#issue-MT}

* Compruebe que la conexión es estable. Una conexión SMPP debe permanecer activa durante al menos 1 hora de forma continua. Consulte la sección [Problema con conexiones inestables](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Si reiniciar el MTA hace que el envío de MT funcione de nuevo durante un período de tiempo pequeño, probablemente tenga problemas debido a una conexión inestable. Consulte la sección [Problema con conexiones inestables](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Compruebe que el registro amplio está presente y que tiene el estado correcto con las fechas correctas. Si no es así, podría tratarse de un problema de preparación de envíos o envíos.

* Compruebe que el MTA procesa realmente el mensaje. Si no es el caso, puede que este no sea un problema de SMS.

* Compruebe que el conector SMS está enlazado con el equipo del proveedor. Solicite comentarios al proveedor para asegurarse de que todos los sistemas se comunican correctamente. Consulte `BIND_TRANSMITTER` y `BIND_TRANSCEIVER PDU`s para obtener información sobre el proceso de enlace. Es posible que deba habilitar los seguimientos SMPP para la correcta resolución de problemas.

* Con los seguimientos de SMPP activados, compruebe que `SUBMIT_SM PDU` contiene la información correcta.

* Compruebe que el proveedor responde con un `SUBMIT_SM_RESP PDU` con un valor &quot;OK&quot; (código 0). Asegúrese de que la PDU llega con un retraso razonable: cualquier valor superior a 1 segundo debe ser discutido con el proveedor, normalmente llega en menos de 100 ms.

* Si todos estos pasos funcionan, puede estar seguro de que el problema está en el lado del proveedor. Tendrán que hacer la resolución de problemas en su plataforma.

* Si funciona pero el rendimiento es incoherente, intente ajustar la ventana de envío y reducir el rendimiento de MT. Tendrá que trabajar con el proveedor para ajustar eso. Adobe Campaign puede enviar mensajes muy rápidamente para que puedan surgir problemas de rendimiento en el equipo del proveedor.

## MT duplicados (el mismo SMS se envía varias veces seguidas){#duplicated-MT}

Los duplicados suelen ser causados por reintentos. Es normal tener duplicados al reintentar mensajes, en su lugar debe intentar eliminar la causa raíz de los reintentos.

* Si ve duplicados enviados exactamente con 60 segundos de diferencia, probablemente sea un problema en el proveedor, no envían un `SUBMIT_SM_RESP` lo suficientemente rápido.

* Si ve muchos `BIND/UNBIND`, tiene una conexión inestable. Consulte la sección[Problema con conexiones inestables](../../administration/using/troubleshooting-sms.md#issues-unstable-connection) para obtener soluciones antes de intentar resolver problemas de mensajes de duplicado.

Reducción de la cantidad de duplicados cuando hay un reintento:

* Baje la ventana de envío. La ventana de envío debe ser lo suficientemente grande como para cubrir la latencia `SUBMIT_SM_RESP`. Su valor representa el número máximo de mensajes que se pueden duplicar si se produce un error mientras la ventana está llena.

## Problema al procesar SR (recibos de envío) {#issue-process-SR}

* Necesitará los rastros SMPP activados para realizar cualquier tipo de resolución de problemas de SR.

* Compruebe que el `DELIVER_SM PDU` proviene del proveedor y que está bien formado.

* Compruebe que Adobe Campaign responde con éxito `DELIVER_SM_RESP PDU` de manera oportuna. En Adobe Campaign Standard, esto garantiza que se ha aplicado toda la lógica de procesamiento, si no es el caso, se garantiza que tenga un mensaje de error en los registros que indique por qué falló el procesamiento.

Si el `DELIVER_SM PDU` no se reconoce correctamente, debe comprobar lo siguiente:

* Consulte regex relacionado con la extracción de ID y el procesamiento de errores en la **Cuenta externa**. Es posible que tenga que validarlos con el contenido de `DELIVER_SM PDU`.

* Compruebe que los errores se han aprovisionado correctamente en la tabla `broadLogMsg`.

* Para Adobe Campaign Standard, compruebe que las tablas `broadLog` y `broadLogExec` están correctamente sincronizadas.

Si ha corregido todo pero algunos SR no válidos siguen en los búferes del proveedor, puede omitirlos con la opción **Recuento de reconocimiento de ID no válido**. Debe utilizarse con cuidado y restablecerse a 0 lo antes posible después de que los búferes estén limpios.

## Problema al procesar MO (y lista negra/respuesta automática){#issue-process-MO}

* Habilite los seguimientos de SMPP durante las pruebas. Si no habilita TLS, debe realizar una captura de red al solucionar problemas de MO para comprobar que las PDU contienen la información correcta y tienen el formato adecuado.

* Al capturar tráfico de red o analizar los seguimientos SMPP, asegúrese de capturar toda la conversación con el MO y su mensaje MT de respuesta si se configura una respuesta.

* Si el MO (`DELIVER_SM PDU`) no aparece en los seguimientos, el problema está en el lado del proveedor. Tendrán que resolver problemas en su plataforma.

* Si aparece `DELIVER_SM PDU`, compruebe que Adobe Campaign lo ha reconocido con un `DELIVER_SM_RESP PDU` correcto (código 0). Este RESP garantiza que Adobe Campaign ha aplicado toda la lógica de procesamiento (respuesta automática y permitir/lista de bloqueados). Si no es así, busque un mensaje de error en los registros de MTA.

* Si las respuestas automáticas están habilitadas, compruebe que `SUBMIT_SM` se haya enviado al proveedor. De lo contrario, se garantiza que encontrará un mensaje de error en los registros de MTA.

* Si el `SUBMIT_SM MT PDU` que contiene la respuesta se encuentra en los seguimientos pero el SMS no llega al teléfono móvil, tendrá que ponerse en contacto con el proveedor para obtener ayuda sobre la resolución de problemas.

## Problema durante la preparación del envío sin excluir destinatarios en cuarentena (en cuarentena por la función de respuesta automática) {#issue-delivery-preparation}

* Compruebe que el formato del número de teléfono es exactamente el mismo en la tabla de cuarentenas y en el registro de envíos.  Si no es así, consulte esta [sección](../../administration/using/sms-protocol.md#automatic-reply) si tiene problemas con el prefijo más del formato del número de teléfono internacional.

* Compruebe los códigos cortos. Las exclusiones pueden producirse si el código corto del destinatario es el mismo que se define en la cuenta externa o si está vacío (vacío = cualquier código abreviado). Si solo se utiliza un código corto para toda la instancia de Adobe Campaign, es más fácil dejar vacíos todos los campos **de código corto**.

## Problemas de codificación {#encoding-issues}

**Paso 1: Póngase en contacto con el proveedor**

Póngase en contacto con ellos y vea qué les pasa. Deberían poder decirle si el problema está de su lado o de Adobe Campaign. Si el problema está en Adobe Campaign, deben poder indicarle exactamente qué campo es incorrecto.

**Paso 2: Saber qué hay en el mensaje**

Unicode permite muchas variantes para caracteres similares y Adobe Campaign no puede manejarlos todos.

La fuente más común de problemas es una copia y pegado desde un procesador de textos, que cambia los caracteres habituales a versiones tipográficamente correctas: espacios cambiados a espacios sin saltos, comillas de doble cambiadas por comillas de apertura y cierre, menos signos cambiados a varios tipos de guiones, etc.

No copie y pegue el mensaje durante la prueba, escríbalo siempre directamente en la interfaz.

Con hexadecimal, puede distinguir la diferencia entre caracteres similares. Una L minúscula, una I mayúscula, O, 0, todos los diferentes tipos de comillas, codificaciones no latinas o incluso distintos tipos de espacios pueden verse igual o incluso no mostrarse.

Para convertir unicode a hexadecimal, puede utilizar herramientas en línea como el sitio web [convertidor de código Unicode](https://r12a.github.io/app-conversion/). Escriba el texto, asegúrese de que no haya PII como números de teléfono y haga clic en **Convertir**. Verá los valores hexadecimales en la parte inferior (zona UTF-32).

Al abrir entradas sobre problemas de codificación, ya sea con el proveedor o con la asistencia de Adobe Campaign, siempre incluya una versión hexadecimal de lo que escribe y lo que ve.

**Paso 3: Saber lo que debe enviar**

Determine la codificación que espera usar y busque en línea su tabla de caracteres. Compruebe que los caracteres que desea enviar están disponibles en la página de código de destinatario. Compruebe que el campo `data_coding` es correcto y coincide con lo que usted y el proveedor esperan.

**Paso 4: Conocer lo que realmente enviaste**

Necesitará la salida de depuración del conector para ver exactamente qué bytes envía al proveedor. Los problemas de codificación aparecen en `SUBMIT_SM PDU`s, por lo que asegúrese de capturarlos. Envíe mensajes muy distintos que sean fáciles de encontrar en el registro.

Envíe diferentes tipos de caracteres especiales al realizar pruebas. Por ejemplo, la codificación GSM7 tiene caracteres extendidos que son muy distintos en su forma hexadecimal; son fáciles de identificar, ya que no aparecen en ninguna otra codificación.

## Elementos que se deben incluir al comunicar sobre un problema de SMS {#element-include}

Siempre que busques ayuda sobre un problema de SMS, ya sea abriendo un ticket de soporte a Adobe Campaign, al proveedor de SMS o cualquier tipo de comunicación sobre el tema, necesitarás incluir la siguiente información para asegurarte de que esté debidamente cualificado. Los problemas debidamente calificados son clave para resolverlos más rápido.

* **Active los** mensajes SMPP detallados cuando aparezca el problema. La mayoría de los problemas de SMS son imposibles de resolver sin esto.

* Si el problema está relacionado con el tráfico de SMS, póngase en contacto primero con el proveedor. Su plataforma es más adecuada para un diagnóstico eficiente de los problemas de tráfico SMS en tiempo real.

* Incluya una descripción breve pero objetiva del problema.

* Incluya una descripción del resultado esperado.

* Incluya los comentarios del proveedor.

* Incluya registros relevantes y/o capturas de red. Al realizar capturas, asegúrese de reproducir el problema durante la captura.

* Si incluye registros, rastros o capturas, indique la ubicación exacta en el archivo cuando aparezca el problema.

* Si hace referencia a mensajes, PDU o registros, indique claramente su marca de tiempo para facilitar su búsqueda.

* Intente reproducir el problema en un entorno de prueba. Si no está seguro de un ajuste, pruébelo en el entorno de prueba y compruebe el resultado con los seguimientos de SMPP. Generalmente es mejor informar de problemas replicados en entornos de prueba que problemas de sistema de informes directo en entornos de producción.

* Incluya cualquier cambio o ajuste realizado en la plataforma. Además, incluya cualquier cambio que el proveedor pueda haber realizado de su parte.

### Captura de red {#network-capture}

No siempre se necesita una captura de red, por lo general los mensajes SMPP detallados son suficientes. Estas son algunas directrices que le ayudarán a determinar si es necesaria una captura de red:

* Problemas de conexión, pero los mensajes detallados no muestran ningún `BIND_RESP PDU`.

* Desconexiones inexplicables sin mensaje de error, el comportamiento habitual del conector cuando detecta un error de protocolo de bajo nivel.

* El proveedor se queja del proceso de desvinculación/desconexión.

* Problemas de codificación en campos TLV opcionales.

* Se sospecha que el tráfico se mezcla entre diferentes conexiones.

En todas las demás situaciones, intente analizar primero los mensajes SMPP detallados y solicite una captura de red solo si está claro que falta información en los registros detallados.

En algunos casos, no es necesario capturar el tráfico de red. Estas son las situaciones más comunes:

* TLS habilitado: Por definición, el tráfico TLS está cifrado para que no se pueda capturar.

* Problemas de rendimiento: Los registros contienen toda la información necesaria para rastrear los problemas de rendimiento.

* Problemas de temporización (`retry timing`, `enquire_link` período, límite de rendimiento, etc.)

* Análisis y procesamiento de SR: Los registros detallados proporcionan mucho más contexto y una mejor presentación.

* Procesamiento de MO (respuestas automáticas, cuarentena).

* Errores que no implican tráfico SMPP real: Preparación de envíos, problemas de API de centros de mensajes, problemas de flujo de trabajo, etc.

## Activación de los seguimientos de SMPP {#enabling-smpp-traces}

El nuevo conector admite el registro extendido mediante seguimientos: SMPP. Los seguimientos aparecen en el registro MTA, no en la salida estándar.

**Activación por cuenta externa (método preferido)**

1. En la **Cuenta externa**, seleccione **Habilitar los rastros SMPP detallados en el archivo de registro**.
1. Guardar, el conector se reconectará con los rastros habilitados.

**Activación sobre la marcha**

Adobe Campaign Standard MTA tiene una interfaz de control HTTP que permite cambiar el filtro de seguimiento sobre la marcha.
Una llamada de POST puede habilitar o deshabilitar los seguimientos. Ejemplo de URL para habilitar los seguimientos de SMPP:

```
POST http://host:7780/mta/trace?filter=SMPP
```

Para deshabilitar los seguimientos, establezca un filtro vacío:

```
POST http://host:7780/mta/trace?filter=
```

**Habilitar en la configuración**

En el archivo `config-instance.xml`, establezca los siguientes parámetros:

```
<mta args="-tracefilter:SMPP"/>
```

## Comprobación del número de conexiones abiertas en un contenedor {#open-connections}

Para comprobar el número de conexiones abiertas en un contenedor, puede utilizar este comando:

```
(for pid in $(ss -neopts  | sed -n ‘s/^.*:3600[ \t].*users:(([0-9A-Za-z”]*,pid=\([0-9]*\),.*$/\1/p’ | sort ); do  cat /proc/$pid/cmdline; echo  ” $pid” ;done;) | uniq --count
```

Esto lista el número de conexiones abiertas para un puerto determinado. Aquí estamos usando el puerto 3600.

El resultado debe ser el siguiente:

```
4 nlserversms -noconsole -tracefile:sms@INSTANCE_NAME -instance:INSTANCE_NAME -detach 15180
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 1838
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24025
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24029
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 29088
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 30390
```

4 conexiones abiertas para el proceso sms y 2 por mta secundaria con 5 niños.
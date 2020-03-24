---
title: Configuración del canal de correo electrónico en Adobe Campaign Standard
description: Obtenga información sobre cómo configurar el canal de correo electrónico en Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b85633e278e3824a58390ee538b4a6e6954785af

---


# Configuración de canales de correo electrónico{#configuring-email-channel}

## Parámetros de canal de correo electrónico {#email-channel-parameters}

La pantalla de configuración de correo electrónico permite definir los parámetros del canal de correo electrónico.

![](assets/channels_1.png)

* **Parámetros de encabezado de correos electrónicos enviados**

   En esta sección, puede especificar la dirección de remitente y la dirección de error **[!UICONTROL masks]** autorizada. Si es necesario, estas máscaras se pueden separar mediante comas. Esta configuración es opcional. Cuando se especifican estos campos, durante la fase de preparación del mensaje, Adobe Campaign comprueba que las direcciones especificadas son válidas. Este modo operativo garantiza que no se utilicen direcciones que puedan desencadenar problemas de entrega. Las direcciones de entrega deben configurarse en el servidor de entrega.

* **Capacidad de entrega**

   Esta ID la proporciona la asistencia técnica. Es necesario que los informes de entregabilidad funcionen correctamente.

* **Parámetros de envío**

   Adobe Campaign envía los mensajes a partir de la fecha de inicio. El **[!UICONTROL Message delivery duration]** campo permite especificar la duración durante la cual se pueden enviar los mensajes.

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).

* **Reintentos**

   Los mensajes no entregados temporalmente están sujetos a un reintento automático. Esta sección indica cuántos reintentos se deben realizar el día siguiente al inicio del envío (**Número de reintentos**) y el retraso mínimo entre reintentos (período **de** reintento).

   De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, repartidos en las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Parámetros de cuarentena de correo electrónico**

   En el **[!UICONTROL Time between two significant errors]** campo, introduzca un valor para definir el tiempo que la aplicación espera antes de incrementar el contador de errores en caso de error. Valor predeterminado: **&quot;1d&quot;**, durante 1 día.

   Cuando se alcanza el **[!UICONTROL Maximum number of errors before quarantine]** valor, la dirección de correo electrónico se pone en cuarentena. Valor predeterminado: **&quot;5&quot;**: la dirección se pondrá en cuarentena en el sexto error. Esto significa que el contacto se excluirá automáticamente de las entregas posteriores.

**Tema** relacionado:

[Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)

## Cuentas de enrutamiento de correo electrónico {#email-routing-accounts}

La cuenta **[!UICONTROL Integrated email routing]** externa se proporciona de forma predeterminada. Contiene los parámetros técnicos que permiten a la aplicación enviar correos electrónicos.

![](assets/channels_2.png)

El tipo de cuenta siempre debe estar establecido en **[!UICONTROL Routing]**, el canal a **[!UICONTROL Email]** y el modo de entrega establecido en **[!UICONTROL Bulk delivery]**.

**Tema** relacionado:

[Cuentas externas](../../administration/using/external-accounts.md)

## Reglas de procesamiento de correo electrónico {#email-processing-rules}

Los administradores **[!UICONTROL Email processing rules]** pueden acceder a la página a través del **[!UICONTROL Administration > Channels > Email]** menú.

Estas reglas contienen la lista de cadenas de caracteres que pueden devolver los servidores remotos y que le permiten clasificar el error (**Grave**, **leve** o **ignorado**).

Las reglas predeterminadas son las siguientes:

### Mensajes de devolución {#bounce-mails}

Para los mensajes de error de error de entrega sincrónica, el MTA mejorado determina el tipo de devolución y la calificación, y envía esa información a Campaign. Para obtener más información sobre el MTA mejorado de Adobe Campaign, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Las devoluciones asincrónicas siguen siendo calificadas por el proceso Campaña en correo a través de la **[!UICONTROL Bounce mails]** regla.

>[!IMPORTANT]
>
>Una vez actualizado a la MTA mejorada, ya no se utilizan las cualificaciones de devolución de la tabla Campaña **[!UICONTROL Message qualification]** . Para obtener más información sobre la calificación de correo de devolución, consulte esta [sección](../../sending/using/understanding-delivery-failures.md).

<!--The user can create his own rules.

>[!IMPORTANT]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.-->

### Administración de dominios de correo electrónico {#managing-email-domains}

<!--The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP relay**: lets you configure the IP address and the port of a relay server for a particular domain.-->

>[!IMPORTANT]
>
>Una vez actualizadas a la MTA mejorada, ya no se utilizan las reglas de Adobe Campaign **[!UICONTROL Domain management]** .

**La firma de autenticación por correo electrónico de DKIM (DomainKeys Identified Mail)** se realiza mediante el MTA mejorado para todos los mensajes con todos los dominios. No se firma con **el ID** del remitente, **DomainKeys** o **S/MIME** a menos que se especifique lo contrario en el nivel de MTA mejorado.

Para obtener más información sobre el MTA mejorado de Adobe Campaign, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### MX management {#mx-management}

<!--The MX management rules are used to regulate the flow of outgoing emails for a specific domain. They sample the bounce messages and block sending where appropriate.

The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

To configure MX management rules, simply set a threshold and select certain SMTP parameters. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.-->

>[!IMPORTANT]
>
>Una vez actualizado a MTA mejorado, ya no se utilizan las reglas de rendimiento de entrega de Adobe Campaign **[!UICONTROL MX management]** .

El MTA mejorado utiliza sus propias reglas MX que le permiten personalizar el rendimiento por dominio en función de su propia reputación histórica de correo electrónico y de los comentarios en tiempo real procedentes de los dominios a los que envía correos electrónicos.

Para obtener más información sobre el MTA mejorado de Adobe Campaign, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

<!--Each rule defines an address mask for the MX. Any MX whose name matches this mask is therefore eligible. The mask can contain "&#42;" and "?" generic characters.

For example, the following addresses:

* a.mx.yahoo.com 
* b.mx.yahoo.com 
* c.mx.yahoo.com

are compatible with the following masks:

* &#42;.yahoo.com
* ?.mx.yahoo.com

These rules are applied in sequence: the first rule whose MX mask is compatible with the targeted MX is applied.

The following parameters are available for each rule:

* **[!UICONTROL Range of IDs]**: this option lets you indicate the ranges of identifiers (publicId) for which the rule applies. You can specify:

    * A number: the rule will only apply to this publicId.
    * A range of numbers (number1-number2): the rule will apply to all publicIds between these two numbers.

  If the field is empty, the rule applies to all IDs.

* **[!UICONTROL Shared]**: this option indicates that the highest number of messages per hour and of connections applies to all MXs linked to this rule. 
* **[!UICONTROL Maximum number of connections]**: maximum number of simultaneous connections to an MX from a given address. 
* **Maximum number of messages**: maximum number of messages that can be sent by one connection. After this amount, the connection is closed and a new one is reopened. 
* **[!UICONTROL Messages per hour]**: maximum number of messages that can be sent in one hour for an MX via a given address.

>[!IMPORTANT]
>
>* The delivery server (MTA) must be restarted if the parameters have been changed. 
>* The modification or creation of management rules is for expert users only. -->

## Lista de propiedades de correo electrónico {#list-of-email-properties}

Esta sección detalla la lista de parámetros disponibles en la pantalla de propiedades de una plantilla de correo electrónico o de correo electrónico.

>[!NOTE]
>
>Algunos parámetros solo están disponibles en plantillas. Los parámetros a los que puede acceder [dependen de sus permisos](../../administration/using/users-management.md).

Para editar las propiedades de un correo electrónico o una plantilla de correo electrónico, utilice el **[!UICONTROL Edit properties]** botón .

![](assets/delivery_options_1.png)

### Parámetros generales {#general-parameters}

En la parte superior de la pantalla del parámetro de correo electrónico, identifique el correo electrónico mediante los campos **[!UICONTROL Label]** y **[!UICONTROL ID]** . Esta información aparece en la interfaz pero no es visible para los destinatarios del mensaje.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>El ID debe ser único.

El **[!UICONTROL Brand]** campo permite seleccionar la marca vinculada a la entrega. Para obtener más información sobre el uso y la configuración de marcas, consulte la sección [Marcas](../../administration/using/branding.md) .

El **[!UICONTROL Campaign]** campo permite introducir la campaña vinculada al correo electrónico.

También puede agregar un **[!UICONTROL Description]** en el campo correspondiente y editar la imagen mostrada en la miniatura de correo electrónico en las listas.

### Envío de parámetros {#sending-parameters}

La **[!UICONTROL Send]** sección solo está disponible para plantillas de correo electrónico. Contiene los siguientes parámetros:

#### Parámetros de reintentos {#retries-parameters}

Los mensajes no entregados temporalmente están sujetos a un reintento automático. Esta sección indica cuántos reintentos se deben realizar el día siguiente al inicio del envío ( **[!UICONTROL Max. number of retries]** ) y el retraso mínimo entre reintentos ( **[!UICONTROL Retry period]** ).

De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, repartidos en las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

El número de reintentos se puede cambiar globalmente (póngase en contacto con el administrador técnico de Adobe) o para cada plantilla de entrega o entrega

#### Parámetros de formato de correo electrónico {#email-format-parameters}

Puede configurar el formato de los mensajes de correo electrónico que se van a enviar. Hay tres opciones disponibles:

* **Usar preferencias** de destinatario (modo predeterminado): el formato del mensaje se define según los datos almacenados en el perfil del destinatario y se almacena de forma predeterminada en el campo Formato **de** correo electrónico (@emailFormat). Si un destinatario desea recibir mensajes en un formato determinado, este es el formato enviado. Si el campo no se ha completado, se envía un mensaje alternativo de varias partes (véase más adelante).
* **Permita que el cliente de correo del destinatario elija el formato más adecuado (multipart-alternativa)**: el mensaje contiene ambos formatos: texto y HTML. El formato que se muestra tras la recepción depende de la configuración del software de correo del destinatario (multipart-alternativa).

   >[!IMPORTANT]
   >
   >Esta opción incluye ambas versiones del mensaje. Por lo tanto, afecta al rendimiento de la entrega, ya que el tamaño del mensaje es bueno.

* **Enviar todos los mensajes en formato** de texto: el mensaje se envía en formato de texto. El formato HTML no se enviará, sino que se utilizará para la página de reflejo únicamente cuando el destinatario haga clic en el vínculo del mensaje.

#### Modo de prueba SMTP {#smtp-test-mode}

La **[!UICONTROL Enable SMTP test mode]** opción le permite probar el envío de correos electrónicos a través de una conexión SMTP sin realmente enviar mensajes.
Los mensajes se procesan hasta que se logra la conexión con el servidor SMTP, pero no se envían.

![](assets/smtp-test-mode.png)

Esta opción está disponible para correos electrónicos y plantillas de correo electrónico.

Si activa la opción de modo de prueba SMTP para una plantilla de correo electrónico, todos los mensajes de correo electrónico creados a partir de esta plantilla tendrán esta opción activada.

>[!IMPORTANT]
>
>Cuando esta opción está habilitada para un correo electrónico, no se enviará ningún mensaje hasta que no esté activada.
>Se mostrará una advertencia en el tablero de plantillas de correo electrónico o correo electrónico.

Para obtener más información sobre la configuración de SMTP, consulte la sección [Lista de parámetros](#list-of-email-smtp-parameters) SMTP de correo electrónico.

### Parámetros del período de validez {#validity-period-parameters}

La **[!UICONTROL Validity period]** sección contiene los siguientes parámetros:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**:: cuando esta casilla está desactivada, debe introducir una duración en los campos **[!UICONTROL Delivery duration]** y **[!UICONTROL Resource validity limit]** . Marque esta casilla si desea definir fechas y horas específicas.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**:: Adobe Campaign envía los mensajes a partir de la fecha de inicio. Este campo permite especificar la duración durante la cual se pueden enviar los mensajes.

   >[!IMPORTANT]
   >
   >Una vez actualizado a la MTA mejorada, el **[!UICONTROL Delivery duration]** parámetro de las entregas de la campaña se utiliza solamente si se establece en 3,5 días o menos. Si define un valor superior a 3,5 días, no se tendrá en cuenta. Todos los impactos se detallan en el documento MTA [mejorado de](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) Adobe Campaign.

* **[!UICONTROL Resource validity duration]**:: este campo se utiliza para los recursos cargados, principalmente para la página reflejada y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).
* **[!UICONTROL Mirror page management]**:: la página reflejada es una página HTML a la que se puede acceder en línea a través de un navegador web. Su contenido es idéntico al del correo electrónico. De forma predeterminada, la página reflejada se genera si el vínculo se inserta en el contenido del correo. Este campo permite modificar la forma en que se genera esta página:

   >[!IMPORTANT]
   >
   >Se debe haber definido un contenido HTML para el correo electrónico de la página reflejada que se va a crear.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo predeterminado): la página reflejada se genera si el vínculo se inserta en el contenido del correo.
   * **Forzar la generación de la página** de reflejo: aunque no se inserte ningún vínculo a la página de reflejo en los mensajes, se creará la página de reflejo.
   * **No genere la página** reflejada: no se genera ninguna página reflejada, aunque el vínculo esté en los mensajes.
   * **Genere una página reflejada a la que se pueda acceder utilizando únicamente el ID** del mensaje: esta opción le permite acceder al contenido de la página reflejada, con información de personalización, en la ventana del registro de entrega.

>[!NOTE]
>
>El **[!UICONTROL Delivery duration]** parámetro no se aplica a los mensajes transaccionales. Para obtener más información sobre la mensajería transaccional, consulte [esta sección](../../channels/using/about-transactional-messaging.md).

### Parámetros de seguimiento {#tracking-parameters}

La **[!UICONTROL Tracking]** sección contiene los siguientes parámetros:

* **[!UICONTROL Activate tracking]**:: le permite activar o desactivar el seguimiento de direcciones URL de mensajes. Para administrar el seguimiento de cada dirección URL de mensaje, utilice el **[!UICONTROL Links]** icono de la barra de acciones de Email Designer. Consulte [Acerca de las direcciones URL](../../designing/using/links.md#about-tracked-urls)rastreadas.
* **[!UICONTROL Tracking validity limit]**:: le permite definir la duración durante la cual se activará el seguimiento en las direcciones URL.
* **[!UICONTROL Substitution URL for expired URLs]**:: puede introducir una dirección URL a una página web que se mostrará una vez que el seguimiento haya caducado.

### Parámetros avanzados {#advanced-parameters}

La **[!UICONTROL Advanced parameters]** sección contiene varios parámetros.

Los primeros campos permiten introducir la información necesaria para elaborar los encabezados de los mensajes de correo electrónico. Aquí puede administrar la dirección de respuesta y el texto, así como la dirección del remitente (que rellena el campo &quot;De:&quot;). Dicha información puede personalizarse.

Haga clic en el botón a la derecha del campo que se va a cambiar y, a continuación, agregue el campo de personalización, el bloque de contenido o el texto dinámico.

![](assets/advancedparameters.png)

La inserción y el uso del contenido de personalización se detallan en la documentación [Personalización del contenido](../../designing/using/personalization.md) de correo electrónico.

#### Contexto de Target {#target-context}

El contexto de segmentación permite definir un conjunto de tablas que se utilizarán para direccionamiento por correo electrónico (en la pantalla de definición de audiencia) y personalización (definiendo campos de personalización en el editor de contenido HTML).

#### Enrutamiento {#routing}

Este campo indica el modo de enrutamiento utilizado. Hace referencia a una cuenta externa. Por ejemplo, esto se puede utilizar si desea utilizar una cuenta externa que contenga configuraciones de marca específicas.

>[!NOTE]
>
>Se puede acceder a las cuentas externas a través del menú **Administración** > Ajustes **** de aplicación > Cuentas **** externas.

#### Preparación {#preparation}

La preparación de los mensajes se detalla en la sección [Aprobación de mensajes](../../sending/using/preparing-the-send.md) .

* **[!UICONTROL Typology]**:: antes de cualquier envío, los mensajes deben prepararse para validar el contenido y la configuración. The verification rules applied during the preparation phase are defined in a **typology**. Por ejemplo, para los correos electrónicos, la preparación implica comprobar el asunto, las direcciones URL y las imágenes, etc. Seleccione la tipología que se aplicará en este campo.

   >[!NOTE]
   >
   >Las tipologías, a las que se puede acceder a través del **[!UICONTROL Administration]** menú > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , se presentan en la sección [Tipologías](../../administration/using/about-typology-rules.md) .

* **[!UICONTROL Compute the label during delivery preparation]**:: permite calcular el valor de etiqueta del correo electrónico durante la fase de preparación del mensaje mediante campos de personalización, bloques de contenido y texto dinámico.

   También es posible personalizar la etiqueta de entrega con variables de eventos que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información, consulte [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**:: esta opción le permite agregar registros de consultas SQL en el diario durante la fase de preparación.

#### Configuración de prueba {#proof-settings}

Esta sección le permite configurar el prefijo predeterminado para utilizarlo en la línea de asunto de la prueba. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Lista de parámetros SMTP de correo electrónico {#list-of-email-smtp-parameters}

La **[!UICONTROL SMTP]** sección contiene los siguientes parámetros:

* **[!UICONTROL Character encoding]**:: marque la **[!UICONTROL Force encoding]** casilla si desea forzar la codificación del mensaje y, a continuación, seleccione la codificación que desee utilizar.
* **[!UICONTROL Bounce mails]**:: de forma predeterminada, los mensajes de devolución se reciben en la bandeja de entrada de errores de la plataforma (definida en la pantalla **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). Para definir una dirección de error específica para un correo electrónico, introduzca la dirección en el **[!UICONTROL Error address]** campo.
* **[!UICONTROL Additional SMTP headers]**:: esta opción permite agregar encabezados SMTP adicionales a los mensajes. La secuencia de comandos introducida en el **[!UICONTROL Headers]** campo debe hacer referencia a un encabezado por línea, en forma de **nombre:valor**. Los valores se codifican automáticamente si es necesario.

   >[!IMPORTANT]
   >
   >La adición de secuencias de comandos para insertar encabezados SMTP se reserva para usuarios avanzados. La sintaxis de esta secuencia de comandos debe cumplir con los requisitos de este tipo de contenido: no dejar espacios sin utilizar, ninguna línea vacía, etc.

### Lista de parámetros de autorización de acceso {#list-of-access-authorization-parameters}

La **[!UICONTROL Access authorization]** sección contiene los siguientes parámetros:

* El **[!UICONTROL Organizational unit]** campo permite restringir el acceso a este correo electrónico a determinados usuarios. Los usuarios asociados con la unidad o las unidades principales especificadas tendrán acceso de lectura y escritura a este correo electrónico. Los usuarios asociados con unidades secundarias solo tendrán acceso de lectura a este correo electrónico.

   >[!NOTE]
   >
   >Puede configurar las unidades organizativas mediante el menú **Administración** > **Usuarios y seguridad** .

* Los campos **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Modified by]** y **[!UICONTROL Last modified]** se completan automáticamente.

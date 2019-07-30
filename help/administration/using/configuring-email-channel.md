---
title: Configuración del canal de correo electrónico
seo-title: Configuración del canal de correo electrónico
description: Configuración del canal de correo electrónico
seo-description: Descubra cómo configurar el canal de correo electrónico.
page-status-flag: no activado nunca
uuid: 9 fddb 655-b 445-41 f 3-9 b 02-5 d 356 fc 88 aa 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: configurar canales
discoiquuid: 3752 d 41 f -8 c 59-4 fad-b 30 f-e 98 e 09 cd 74 a 8
context-tags: Extaccountemail, overview; Emailconfig, main; Ruleset, overview; entrega, propiedades, abrir
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f737b1f66b40862d0e0f64cf7d7f4a2d4d29518

---


# Configuring email channel{#configuring-email-channel}

## Email channel parameters {#email-channel-parameters}

La pantalla de configuración de correo electrónico permite definir los parámetros del canal de correo electrónico.

![](assets/channels_1.png)

* **Parámetros de encabezado de los correos electrónicos enviados**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. Si es necesario, estas máscaras se pueden separar mediante comas. Esta configuración es opcional. Cuando se especifican estos campos, durante la etapa de preparación del mensaje, Adobe Campaign comprueba que las direcciones introducidas son válidas. Este modo operativo garantiza que no se utilicen direcciones que puedan desencadenar problemas de entrega. Las direcciones de entrega deben configurarse en el servidor de entrega.

* **Capacidad de entrega**

   Este ID se proporciona mediante compatibilidad. Es necesario que los informes de entregas funcionen correctamente.

* **Parámetros de entrega**

   Adobe Campaign envía los mensajes a partir de la fecha de inicio. **[!UICONTROL Message delivery duration]** El campo permite especificar la duración durante la cual se pueden enviar los mensajes.

   **[!UICONTROL Online resources validity duration]** El campo se utiliza para los recursos cargados, principalmente para la página reflejada y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en disco).

* **Reintentos**

   Los mensajes desacoplados temporalmente están sujetos a un reintento automático. This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**).

   De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, propagado durante las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Parámetros de cuarentena de correo electrónico**

   In the **[!UICONTROL Time between two significant errors]** field, enter a value to define the time the application waits before incrementing the error counter in case of failure. Defaut value: **"1d"**, for 1 day.

   When the **[!UICONTROL Maximum number of errors before quarantine]** value is reached, the email address is then quarantined. Default value: **"5"**: the address will be quarantined on the sixth error. Esto significa que el contacto se excluirá automáticamente de los envíos subsiguientes.

**Tema relacionado**:

[Información sobre la administración de cuarentena](../../sending/using/understanding-quarantine-management.md)

## Email routing accounts {#email-routing-accounts}

The **[!UICONTROL Integrated email routing]** external account is provided by default. Contiene los parámetros técnicos que permiten a la aplicación enviar correos electrónicos.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Tema relacionado**:

[Cuentas externas](../../administration/using/external-accounts.md)

## Email processing rules {#email-processing-rules}

These rules contain the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

Las reglas predeterminadas son las siguientes:

**Mensajes de devolución**

Cuando falla un mensaje de correo electrónico, el servidor de mensajes remoto devuelve un mensaje de error de devolución a la dirección especificada en la configuración de la aplicación. Adobe Campaign compara el contenido de cada correo con las cadenas de la lista de reglas y, a continuación, lo asigna uno de los tres tipos de error.

El usuario puede crear sus propias reglas.

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**Administración de dominios de correo electrónico**

Las reglas de administración de dominios se utilizan para regular el flujo de correos electrónicos salientes para un dominio específico. Muestran los mensajes de devolución y el bloque que se envían cuando corresponde. El servidor de mensajería de Adobe Campaign aplica reglas específicas de los dominios y, a continuación, las reglas para el caso general representado por un asterisco en la lista de reglas. Las reglas para los dominios de Hotmail y MSN están disponibles de forma predeterminada en Adobe Campaign.

Para configurar reglas de administración de dominios, simplemente establezca un umbral y seleccione algunos parámetros SMTP. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.

Por ejemplo, en el caso general, para un mínimo de 300 mensajes, el envío de correos electrónicos se bloquea durante tres horas si la tasa de error alcanza el 90%.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **Rellamada SMTP**: permite configurar la dirección IP y el puerto de un servidor de rellamada para un dominio en particular.

**MX Management**

Cada regla define una máscara de dirección para MX. Por lo tanto, cualquier MX cuyo nombre coincida con esta máscara es elegible. La máscara puede contener " *" y "?" caracteres genéricos.

Por ejemplo, las siguientes direcciones:

* a.mx.ya hoo.com
* b.mx.ya hoo.com
* c.mx.ya hoo.com

son compatibles con las siguientes máscaras:

* *.yahoo.com
* ? .mx.yahoo.com

Estas reglas se aplican en secuencia: la primera regla cuya máscara MX es compatible con la MX objetivo.

Los parámetros siguientes están disponibles para cada regla:

* **[!UICONTROL Range of IDs]**: esta opción le permite indicar los rangos de identificadores (publicidad) para los que se aplica la regla. Puede especificar:

   * Un número: la regla solo se aplicará a este anuncio.
   * Un rango de números (número 1-número 2): la regla se aplicará a todos los anuncios entre estos dos números.
   Si el campo está vacío, la regla se aplica a todos los ID.

* **[!UICONTROL Shared]**: esta opción indica que la mayor cantidad de mensajes por hora y de conexiones se aplica a todos los MXS vinculados a esta regla.
* **[!UICONTROL Maximum number of connections]**: número máximo de conexiones simultáneas a un MX desde una dirección dada.
* **Número máximo de mensajes**: número máximo de mensajes que puede enviar una conexión. Después de esta cantidad, se cierra la conexión y se vuelve a abrir una nueva.
* **[!UICONTROL Messages per hour]**: número máximo de mensajes que pueden enviarse en una hora para un MX a través de una dirección determinada.

>[!CAUTION]
>
>* El servidor de entrega (MTA) debe reiniciarse si se han cambiado los parámetros.
>* La modificación o creación de reglas de administración es solo para usuarios expertos.
>



## List of email properties {#list-of-email-properties}

This section details the list of parameters available in the properties screen of an email or [email template](../../start/using/about-templates.md).

>[!NOTE]
>
>Algunos parámetros solo están disponibles en plantillas. Parameters you can access [depend on your permissions](../../administration/using/users-management.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### General parameters {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. Esta información aparece en la interfaz pero no es visible para los destinatarios del mensaje.

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>El ID debe ser único.

The **[!UICONTROL Brand]** field allows you to select the brand linked to the delivery. For more information on using and configuring brands, refer to the [Branding](../../administration/using/branding.md) section.

The **[!UICONTROL Campaign]** field allows you to enter the campaign linked to the email.

You can also add a **[!UICONTROL Description]** in the corresponding field and edit the image displayed on the email thumbnail in the lists.

### Sending parameters {#sending-parameters}

The **[!UICONTROL Send]** section is only available for email templates. Contiene los parámetros siguientes:

#### Retries parameters {#retries-parameters}

Los mensajes desacoplados temporalmente están sujetos a un reintento automático. This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, propagado durante las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters) section.

El número de reintentos puede cambiarse globalmente (comuníquese con el administrador técnico de Adobe) o con cada plantilla de entrega o entrega

#### Email format parameters {#email-format-parameters}

Puede configurar el formato de mensajes de correo electrónico que se enviarán. Existen tres opciones disponibles:

* **Usar las preferencias del destinatario** (modo predeterminado): el formato de mensaje se define según los datos almacenados en el perfil del destinatario y se almacenan de forma predeterminada en el campo **de formato** Correo electrónico (@ emailformat). Si un destinatario desea recibir mensajes en un formato determinado, es el formato enviado. Si el campo no se completa, se envía un mensaje con varias partes (ver más abajo).
* **Permitir que el cliente de correo electrónico elija el formato más adecuado (multipart-alternative)**: El mensaje contiene ambos formatos: texto y HTML. El formato que se muestra en la recepción depende de la configuración del software de correo electrónico del destinatario (varias partes).

   >[!CAUTION]
   >
   >Esta opción incluye ambas versiones del mensaje. Por lo tanto, influye en el rendimiento de entrega, ya que el tamaño del mensaje es mayor.

* **Enviar todos los mensajes en formato de texto**: el mensaje se envía en formato de texto. No se enviará el formato HTML, pero se utilizará para la página de reflejo solo cuando el destinatario haga clic en el vínculo del mensaje.

#### SMTP test mode {#smtp-test-mode}

The **[!UICONTROL Enable SMTP test mode]** option allows you to test sending emails via an SMTP connection without actually sending messages.
Los mensajes se procesan hasta que se logra la conexión con el servidor SMTP, pero no se envían.

![](assets/smtp-test-mode.png)

Esta opción está disponible para correos electrónicos y plantillas de correo electrónico.

Si activa la opción del modo de prueba SMTP para una plantilla de correo electrónico, todos los mensajes de correo electrónico creados a partir de esta plantilla tendrán habilitada esta opción.

>[!CAUTION]
>
>Cuando esta opción está habilitada para un mensaje de correo electrónico, no se enviarán mensajes hasta que no esté activada.
>Se mostrará una advertencia en el tablero de correo electrónico o de plantillas de correo electrónico.

For more information on configuring SMTP, refer to the [List of email SMTP parameters](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) section.

### Validity period parameters {#validity-period-parameters}

The **[!UICONTROL Validity]** section contains the following parameters:

* **[!UICONTROL Explicitly set validity dates]**: Cuando esta casilla no está marcada, debe especificar una duración en los campos **[!UICONTROL Delivery duration]** y en los **[!UICONTROL Resource validity limit]** campos. Marque esta casilla si desea definir momentos y fechas específicos.
* **[!UICONTROL Delivery duration]**: Adobe Campaign envía los mensajes a partir de la fecha de inicio. Este campo permite especificar la duración durante la cual se pueden enviar los mensajes.
* **[!UICONTROL Resource validity duration]**: este campo se utiliza para los recursos cargados, principalmente para la página reflejada y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en disco).
* **[!UICONTROL Mirror page management]**: La página reflejada es una página HTML accesible en línea a través de un explorador Web. Su contenido es idéntico al contenido de correo electrónico. De forma predeterminada, la página reflejada se genera si el vínculo se inserta en el contenido del correo. Este campo permite modificar la manera en que se genera esta página:

   >[!CAUTION]
   >
   >Se debe haber definido un contenido HTML para el correo electrónico de la página reflejada que se creará.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo predeterminado): la página reflejada se genera si el vínculo se inserta en el contenido del correo.
   * **Forzar la generación de la página reflejada**: aunque no se inserte ningún vínculo a la página reflejada en los mensajes, se creará la página reflejada.
   * **No genere la página reflejada**: no se genera ninguna página reflejada, aunque el vínculo esté en los mensajes.
   * **Genere una página de reflejo accesible utilizando únicamente el ID de mensaje**: esta opción le permite acceder al contenido de la página reflejada, con información de personalización, en la ventana de registro de entrega.

>[!NOTE]
>
>The **[!UICONTROL Explicitly set validity dates]** and **[!UICONTROL Delivery duration]** parameters do not apply to transactional messages. For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Tracking parameters {#tracking-parameters}

The **[!UICONTROL Tracking]** section contains the following parameters:

* **[!UICONTROL Activate tracking]**: permite activar/desactivar el seguimiento de URL del mensaje. To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. See [About tracked URLs](../../designing/using/about-tracked-urls.md).
* **[!UICONTROL Tracking validity limit]**: permite definir la duración para la cual se activará el seguimiento en las direcciones URL.
* **[!UICONTROL Substitution URL for expired URLs]**: Puede introducir una URL a una página web que se mostrará una vez que el seguimiento haya caducado.

### Advanced parameters {#advanced-parameters}

The **[!UICONTROL Advanced parameters]** section contains multiple parameters.

Los dos primeros campos permiten introducir la información necesaria para preparar encabezados de mensaje de correo electrónico (dirección de respuesta y texto de dirección de respuesta). Esta información se puede personalizar. Para ello, haga clic en el botón a la derecha del campo que va a cambiarse y, a continuación, agregue los campos de personalización. Inserting and using the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

#### Target context {#target-context}

El contexto de objetivo permite definir un conjunto de tablas que se utilizarán para la segmentación por correo electrónico (en la pantalla de definición de audiencia) y personalización (definir campos de personalización en el editor de contenido HTML).

#### Routing {#routing}

Este campo indica el modo de enrutamiento utilizado. Hace referencia a una cuenta externa. Por ejemplo, esto puede utilizarse si desea utilizar una cuenta externa que contenga configuraciones de marca específicas.

>[!NOTE]
>
>External accounts are accessible via the **Administration** &gt; **Application settings** &gt; **External accounts** menu.

#### Preparation {#preparation}

Preparing messages is detailed in the [Approving messages](../../sending/using/preparing-the-send.md) section.

* **[!UICONTROL Typology]**: antes de cualquier envío, los mensajes deben prepararse para validar el contenido y la configuración. The verification rules applied during the preparation phase are defined in a **typology**. Por ejemplo: para los correos electrónicos, la preparación implica comprobar el asunto, las direcciones URL y las imágenes, etc. Seleccione la tipología que aplicar en este campo.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery preparation]**: permite calcular el valor de etiqueta del correo electrónico durante la fase de preparación de los mensajes mediante campos de personalización, bloques de contenido y texto dinámico.

   También es posible personalizar la etiqueta de entrega con variables de eventos que se han declarado en la actividad de señal externa del flujo de trabajo. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: esta opción le permite agregar registros de consulta SQL en el diario durante la fase de preparación.

### List of email SMTP parameters {#list-of-email-smtp-parameters}

The **[!UICONTROL SMTP]** section contains the following parameters:

* **[!UICONTROL Character encoding]**: marque la **[!UICONTROL Force encoding]** casilla si desea forzar la codificación del mensaje y, a continuación, seleccione la codificación que desee utilizar.
* **[!UICONTROL Bounce mails]**: de forma predeterminada, los mensajes de salida hacia otro sitio se reciben en la bandeja de entrada de errores de la plataforma (definida en **[!UICONTROL Administration]** la pantalla &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: esta opción permite agregar encabezados SMTP adicionales a los mensajes. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Los valores se codifican automáticamente si es necesario.

   >[!CAUTION]
   >
   >La adición de una secuencia de comandos para insertar encabezados SMTP adicionales está reservada para usuarios avanzados. La sintaxis de esta secuencia de comandos debe cumplir con los requisitos de este tipo de contenido: sin espacio no utilizado, sin línea vacía, etc.

### List of access authorization parameters {#list-of-access-authorization-parameters}

The **[!UICONTROL Access authorization]** section contains the following parameters:

* The **[!UICONTROL Organizational unit]** field allows you to restrict access to this email to certain users. Los usuarios asociados con la unidad o las unidades principales especificadas tendrán acceso de lectura y escritura a este correo electrónico. Los usuarios asociados con las unidades secundarias tendrán acceso de lectura a este correo electrónico.

   >[!NOTE]
   >
   >You can configure organizational units via the **Administration** &gt; **Users &amp; Security** menu.

* **[!UICONTROL Created by]** Los campos, **[!UICONTROL Created]** y **[!UICONTROL Modified by]****[!UICONTROL Last modified]** los campos se completan automáticamente.

## Archiving emails {#archiving-emails}

Puede configurar Adobe Campaign para que mantenga una copia de los mensajes de correo electrónico enviados desde su plataforma.

Sin embargo, Adobe Campaign sí no gestiona los archivos archivados. Permite enviar los mensajes de su elección a una dirección dedicada, desde donde pueden procesarse y archivarse con un sistema externo.

Cuando se activa en la plantilla de entrega, esta función permite enviar una copia exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de envío) que debe especificar.

### Recommendations and limitations {#recommendations-and-limitations}

* Esta función es opcional. Verifique su contrato de licencia y comuníquese con el ejecutivo de cuentas para activarlo.
* Solo puede utilizar una dirección de correo electrónico BCC.
* Solo se toman en cuenta los mensajes de correo electrónico enviados correctamente. Las devoluciones no.
* Por razones de privacidad, los mensajes de correo electrónico BCC deben ser procesados por un sistema de archivos capaz de almacenar información de identificación personal segura (PII).
* Al crear una nueva plantilla de envío, Email BCC no está habilitado de forma predeterminada, incluso si se ha adquirido la opción. Debe habilitarla manualmente en cada plantilla de entrega donde desee usarla.

### Activating email archiving {#activating-email-archiving}

Email BCC is activated in the [email template](../../start/using/about-templates.md), through a dedicated option:

1. Go to **Resources** &gt; **Templates** &gt; **Delivery templates**.
1. Duplicate the out-of-the-box **[!UICONTROL Send via email]** template.
1. Seleccione la plantilla duplicada.
1. Click the **[!UICONTROL Edit properties]** button to edit the template's properties.
1. Expand the **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.


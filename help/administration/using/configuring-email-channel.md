---
title: Configuración del canal de correo electrónico en Adobe Campaign Standard
description: Obtenga información sobre cómo configurar el canal de correo electrónico en Adobe Campaign Standard.
audience: administration
content-type: reference
topic-tags: configuring-channels
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2597'
ht-degree: 77%

---

# Configuración de canales de correo electrónico{#configuring-email-channel}

Como [administrador](../../administration/using/users-management.md#functional-administrators) de Campaign, puede configurar los canales de correo electrónico. Estas opciones avanzadas incluyen parámetros generales de canal de correo electrónico, cuentas de enrutamiento de correo electrónico, reglas de procesamiento de correo electrónico y propiedades de correo electrónico. En esta página, aprenderá a editar los valores predeterminados del correo electrónico general y a enviar parámetros.

## Parámetros de canal de correo electrónico {#email-channel-parameters}

La pantalla de configuración de correo electrónico le permite definir los parámetros del canal de correo electrónico. Los administradores pueden acceder a estas configuraciones en el menú **[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Campos de máscaras autorizadas**

   La sección **[!UICONTROL Header parameters of sent emails]** enumera las direcciones de correo electrónico autorizadas que puede utilizar para enviar correos electrónicos a sus destinatarios (dirección del remitente) y para permitirles enviar respuestas automatizadas como devoluciones asincrónicas, respuestas de fuera de la oficina, etc. (dirección de error).  Adobe Campaign comprueba que las direcciones especificadas son válidas durante la fase de preparación del mensaje. Este modo operativo garantiza que no se utilicen direcciones que puedan activar problemas de la capacidad de entrega.
   * Adobe configura las direcciones del remitente y de error. Estos campos no pueden estar vacíos.
   * No puede editar esos campos. Para actualizar una dirección, póngase en contacto con el equipo de Atención al cliente de Adobe.
   * Para agregar otra dirección, puede utilizar el [Panel de control](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=es) para configurar un nuevo subdominio o ponerse en contacto con el equipo de Atención al cliente de Adobe. Tenga en cuenta que si se utilizan varias máscaras, se separarán con comas.
   * Se recomienda configurar las direcciones con un asterisco como *@yourdomain.com; de esta forma, le permite utilizar cualquier dirección que termine con su nombre de subdominio.

* **Capacidad de entrega**

   El equipo de Atención al cliente de Adobe proporciona el **[!UICONTROL Delivery reports ID]**. Identifica cada instancia con un ID de capacidad de entrega que se utiliza en los informes técnicos de la capacidad de entrega.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Parámetros de entrega**

   Adobe Campaign envía los mensajes a partir de la fecha de inicio.

   El campo **[!UICONTROL Message delivery duration]** le permite especificar el lapso de tiempo en el que se reintentará cualquier mensaje de la entrega que detecte un error temporal o una devolución del mensaje.

   >[!IMPORTANT]
   >
   >**Este parámetro en Campaign ahora solo se utiliza si se establece en 3,5 días o menos.** Si define un valor superior a 3,5 días, no se tendrá en cuenta.

   El campo **[!UICONTROL Online resources validity duration]** se utiliza para los recursos cargados, principalmente para la página espejo y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).

* **Reintentos**

   Los mensajes no entregados temporalmente están sujetos a un reintento automático. Para obtener más información, consulte [Reintentos después de un error temporal de entrega](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!IMPORTANT]
   >
   >El número máximo de reintentos que se deben realizar y el retraso mínimo entre reintentos ahora se basan en el rendimiento histórico y actual de una IP en un dominio determinado. Se ignorarán las configuraciones **[!UICONTROL Retry period]** y **[!UICONTROL Number of retries]** en Campaign.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parámetros de cuarentena de correo electrónico**

   En el campo **[!UICONTROL Time between two significant errors]**, introduzca un valor para definir el tiempo que la aplicación espera antes de incrementar el contador de errores en caso de que se produzca un error de devolución del mensaje. El valor predeterminado es **“1d”**, para 1 día.

   Cuando se alcanza el valor **[!UICONTROL Maximum number of errors before quarantine]**, la dirección de correo electrónico se pone en cuarentena. El valor predeterminado es **“5”**: la dirección se pondrá en cuarentena en el quinto error. Esto significa que el contacto se excluirá automáticamente de las entregas posteriores.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Para obtener más información sobre cuarentenas, consulte [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md).

## Cuentas de enrutamiento de correo electrónico {#email-routing-accounts}

La cuenta externa **[!UICONTROL Integrated email routing]** se proporciona de forma predeterminada. Contiene los parámetros técnicos que permiten a la aplicación enviar correos electrónicos.

![](assets/channels_2.png)

El tipo de cuenta siempre debe estar establecido en **[!UICONTROL Routing]**, el canal en **[!UICONTROL Email]** y el modo de entrega establecido en **[!UICONTROL Bulk delivery]**.

**Temas relacionados**:

[Cuentas externas](../../administration/using/external-accounts.md)

## Reglas de procesamiento de correo electrónico {#email-processing-rules}

Los administradores pueden acceder a **[!UICONTROL Email processing rules]** a través del menú **[!UICONTROL Administration > Channels > Email]**.

>[!IMPORTANT]
>
>Los dominios de correo electrónico y las reglas MX ahora se administran automáticamente<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> y no se pueden cambiar.

* **La firma de autenticación por correo electrónico de DKIM (DomainKeys Identified Mail)**  se realiza para todos los mensajes con todos los dominios. No se firma con **ID del remitente**, **DomainKeys** o **S/MIME**.
* Las reglas MX personalizan automáticamente el rendimiento por dominio en función de su propia reputación histórica de correo electrónico y de los comentarios en tiempo real procedentes de los dominios a los que envía correos electrónicos.

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### Correos devueltos {#bounce-mails}

Las devoluciones asincrónicas siguen siendo calificadas por el proceso inMail de Campaign a través de las reglas **[!UICONTROL Bounce mails]**.

Estas reglas contienen la lista de cadenas de caracteres que pueden devolver los servidores remotos y que le permiten clasificar el error (**Grave**, **leve** o **ignorado**).

>[!IMPORTANT]
>
>Los mensajes de error de error de envío sincrónico ahora son calificados por el MTA mejorado de Adobe Campaign, que determina el tipo de rechazo y la calificación, y envía esa información a Campaign.

Para obtener más información sobre la calificación de correo devuelto, consulte esta [sección](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Lista de las propiedades de correo electrónico {#list-of-email-properties}

Esta sección detalla la lista de los parámetros disponibles en la pantalla de propiedades de un correo electrónico o de una plantilla de correo electrónico.

>[!NOTE]
>
>Algunos parámetros solo están disponibles en plantillas. Los parámetros a los que puede acceder [dependen de sus permisos](../../administration/using/users-management.md).

Para editar las propiedades de un correo electrónico o una plantilla de correo electrónico, utilice el botón **[!UICONTROL Edit properties]**.

![](assets/delivery_options_1.png)

### Parámetros generales {#general-parameters}

En la parte superior de la pantalla del parámetro de correo electrónico, identifique el correo electrónico mediante los campos **[!UICONTROL Label]** y **[!UICONTROL ID]**. Esta información aparece en la interfaz pero no es visible para los destinatarios de mensajes.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>El ID debe ser único.

El campo **[!UICONTROL Brand]** le permite seleccionar la marca vinculada al envío. Para obtener más información sobre el uso y la configuración de marcas, consulte la sección [Marcas](../../administration/using/branding.md).

El campo **[!UICONTROL Campaign]** le permite introducir la campaña vinculada al correo electrónico.

También puede agregar una **[!UICONTROL Description]** en el campo correspondiente y editar la imagen mostrada en la miniatura del correo electrónico en las listas.

### Envío de parámetros {#sending-parameters}

La sección **[!UICONTROL Send]** solo está disponible para plantillas de correo electrónico. Contiene los siguientes parámetros:

#### Parámetros de reintentos {#retries-parameters}

Los mensajes no entregados temporalmente están sujetos a un reintento automático. Para obtener más información, consulte [Reintentos después de un error temporal de entrega](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!IMPORTANT]
>
>El retraso mínimo entre reintentos y el número máximo de reintentos que se van a realizar ahora se basa en el rendimiento histórico y actual de una IP en un dominio determinado. Se ignorarán las configuraciones **[!UICONTROL Retry period]** y **[!UICONTROL Max. number of retries]** en Campaign.

La **configuración de la duración de la entrega** (definida en la sección [Parámetros del periodo de validez](#validity-period-parameters)) **configurada en Campaign se seguirá cumpliendo, pero solo hasta 3,5 días**. En ese momento, cualquier mensaje de la cola de reintentos se eliminará de la cola y se enviará de nuevo como una devolución. Para obtener más información sobre los fallos de entrega, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Parámetros del formato del correo electrónico {#email-format-parameters}

Puede configurar el formato de los correos electrónicos que se van a enviar. Hay tres opciones disponibles:

* **Uso de preferencias del destinatario** (modo predeterminado): el formato de mensaje se define según los datos almacenados en el perfil de destinatario y se almacena de forma predeterminada en el campo **Formato del correo electrónico** (@emailFormat). Si un destinatario desea recibir mensajes en un formato determinado, este es el formato enviado. Si el campo no está completo, se envía un mensaje multipart-alternative (consulte a continuación).
* **Permita que el cliente de correo destinatario elija el formato más adecuado (multipart-alternative)**: el mensaje contiene ambos formatos, de texto y HTML. El formato que se muestra al recibirlo depende de la configuración del software de correo del destinatario (multipart-alternative).

   >[!IMPORTANT]
   >
   >Esta opción incluye ambas versiones del mensaje. Por lo tanto, esto afecta al rendimiento de entrega, ya que el tamaño del mensaje es mayor.

* **Enviar todos los mensajes en formato de texto**: el mensaje se envía en formato de texto. El formato HTML no se envía, pero se utiliza solo para la página espejo cuando el destinatario hace clic en el enlace del mensaje.

#### Modo de prueba SMTP {#smtp-test-mode}

La opción **[!UICONTROL Enable SMTP test mode]** le permite probar el envío de correos electrónicos a través de una conexión SMTP sin realmente enviar mensajes.
Los mensajes se procesan hasta que se logra la conexión con el servidor SMTP, pero no se envían.

![](assets/smtp-test-mode.png)

Esta opción está disponible para correos electrónicos y plantillas de correo electrónico.

Si activa la opción de modo de prueba SMTP para una plantilla de correo electrónico, todos los mensajes de correo electrónico creados a partir de esta plantilla tendrán esta opción habilitada.

>[!IMPORTANT]
>
>Cuando esta opción está habilitada para un correo electrónico, no se enviará ningún mensaje hasta que esté desmarcada.
>Se mostrará una advertencia en el panel del correo electrónico o de la plantilla de correo electrónico.

Para obtener más información sobre la configuración de SMTP, consulte la sección [Lista de parámetros SMTP de correo electrónico](#list-of-email-smtp-parameters).

### Parámetros del periodo de validez {#validity-period-parameters}

La sección **[!UICONTROL Validity period]** contiene los siguientes parámetros:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: cuando esta casilla está desmarcada, debe introducir una duración en **[!UICONTROL Delivery duration]** y **[!UICONTROL Resource validity limit]**.

   Marque esta casilla si desea definir fechas y horas específicas.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign envía los mensajes a partir de la fecha de inicio. Este campo le permite especificar la duración durante la cual se pueden enviar los mensajes.

   >[!IMPORTANT]
   >
   >**Debe definir un valor de hasta 3,5 días.** Si establece un valor superior a 3,5 días, no se tendrá en cuenta.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: este campo se utiliza para los recursos cargados, principalmente para la página espejo y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).
* **[!UICONTROL Mirror page management]**: la página espejo es una página HTML accesible en línea mediante un explorador web. Su contenido es idéntico al contenido del correo electrónico. De forma predeterminada, la página espejo se genera si el vínculo se inserta en el contenido del correo. Este campo le permite modificar la forma en que se genera esta página:

   >[!IMPORTANT]
   >
   >Se debe definir el contenido HTML para el correo electrónico de la página espejo que se va a crear.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo predeterminado): la página espejo se genera si el vínculo se inserta en el contenido del correo.
   * **Forzar la generación de la página espejo**: incluso si no se inserta ningún vínculo a la página espejo en el mensaje se creará la página espejo.
   * **No generar la página espejo**: no se genera ninguna página espejo, aunque el vínculo esté en los mensajes.
   * **Genera una página espejo accesible solo con el ID de mensaje**: esta opción permite acceder al contenido de la página espejo, con información de personalización, en la ventana del registros de entregas.

>[!NOTE]
>
>El parámetro **[!UICONTROL Delivery duration]** no se aplica a mensajes transaccionales. Para obtener más información sobre la mensajería transaccional, consulte [esta sección](../../channels/using/getting-started-with-transactional-msg.md).

### Parámetros de seguimiento {#tracking-parameters}

La sección **[!UICONTROL Tracking]** contiene los siguientes parámetros:

* **[!UICONTROL Activate tracking]**: le permite activar o desactivar el seguimiento de URL de mensajes. Para administrar el seguimiento de cada URL de mensaje, utilice el icono **[!UICONTROL Links]** de la barra de acciones del Diseñador de correo electrónico. Consulte [Acerca de las URL rastreadas](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: le permite definir la duración durante la cual se activará el seguimiento en las URL.
* **[!UICONTROL Substitution URL for expired URLs]**: puede introducir una URL a una página web que se mostrará una vez que el seguimiento haya caducado.

### Parámetros avanzados {#advanced-parameters}

La sección **[!UICONTROL Advanced parameters]** contiene varios parámetros.

Los primeros campos permiten introducir la información necesaria para elaborar los encabezados de los mensajes de correo electrónico. Aquí puede administrar la dirección de respuesta y el texto, así como la dirección del remitente (que rellena el campo “De:”). Dicha información puede personalizarse.

Haga clic en el botón a la derecha del campo que se va a cambiar y, a continuación, añada el campo de personalización, el bloque de contenido o el texto dinámico.

![](assets/advancedparameters.png)

La inserción y el uso del contenido de personalización se detallan en la documentación [Personalización del contenido del correo electrónico](../../designing/using/personalization.md).

#### Contexto de direccionamiento {#target-context}

El contexto de direccionamiento le permite definir un conjunto de tablas que se utilizarán para el direccionamiento (en la pantalla de definición de audiencia) y la personalización (definiendo campos de personalización en el editor de contenido HTML) de correo electrónico.

#### Enrutamiento {#routing}

Este campo indica el modo de enrutamiento utilizado. Hace referencia a una cuenta externa. Por ejemplo, esto se puede utilizar si desea utilizar una cuenta externa que contenga configuraciones de marca específicas.

>[!NOTE]
>
>Se puede acceder a las cuentas externas desde el menú **Administración** > **Configuración de aplicación** > **Cuentas externas**.

#### Preparación {#preparation}

La preparación de los mensajes se detalla en la sección [Aprobación de mensajes](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: antes de cualquier envío, los mensajes deben prepararse para validar el contenido y la configuración. Las reglas de verificación aplicadas durante la fase de preparación se definen en una **tipología**. Por ejemplo, para los correos electrónicos, la preparación implica comprobar el asunto, las direcciones URL y las imágenes, etc. Seleccione la tipología que se aplicará en este campo.

   >[!NOTE]
   >
   >Las tipologías a las que se puede acceder a través del menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** se presentan en [esta sección](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: le permite calcular el valor de la etiqueta del correo electrónico durante la fase de preparación del mensaje mediante campos de personalización, bloques de contenido y texto dinámico.

   También es posible personalizar la etiqueta de entrega con variables de eventos que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información, consulte [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: esta opción le permite añadir registros de consulta SQL en el historial durante la fase de preparación.

#### Configuración de prueba {#proof-settings}

Esta sección le permite configurar el prefijo predeterminado para utilizarlo en la línea de asunto de la prueba. Para obtener más información, consulte [esta sección](../../sending/using/sending-proofs.md).

### Lista de los parámetros SMTP de correo electrónico {#list-of-email-smtp-parameters}

La sección **[!UICONTROL SMTP]** contiene los siguientes parámetros:

* **[!UICONTROL Character encoding]**: marque la casilla **[!UICONTROL Force encoding]** si desea forzar la codificación del mensaje y, a continuación, seleccione la codificación que desee utilizar.
* **[!UICONTROL Bounce mails]**: de forma predeterminada, los mensajes devueltos se reciben en la bandeja de entrada de errores de la plataforma (definida en la pantalla **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Para definir una dirección de error específica para un correo electrónico, introduzca la dirección en el campo **[!UICONTROL Error address]**.
* **[!UICONTROL Additional SMTP headers]**: esta opción permite agregar encabezados SMTP adicionales a los mensajes. La secuencia de comandos introducida en el campo **[!UICONTROL Headers]** debe hacer referencia a un encabezado por línea en forma de **name:value**. Los valores se codifican automáticamente si es necesario.

   >[!IMPORTANT]
   >
   >La adición de secuencias de comandos para insertar encabezados SMTP se reserva para usuarios avanzados. La sintaxis de esta secuencia de comandos debe cumplir con los requisitos de este tipo de contenido: no dejar espacios sin utilizar, ninguna línea vacía, etc.

### Lista de los parámetros de autorización de acceso {#list-of-access-authorization-parameters}

La sección **[!UICONTROL Access authorization]** contiene los siguientes parámetros:

* El campo **[!UICONTROL Organizational unit]** le permite restringir el acceso a este correo electrónico a determinados usuarios. Los usuarios asociados con la unidad o las unidades principales especificadas tendrán acceso de lectura y escritura a este correo electrónico. Los usuarios asociados con unidades secundarias solo tendrán acceso de lectura a este correo electrónico.

   >[!NOTE]
   >
   >Puede configurar las unidades organizativas mediante el menú **Administración** > **Usuarios y seguridad**.

* Los campos **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** y **[!UICONTROL Last modified]** se completan automáticamente.

## Configuración heredada {#legacy-settings}

Si está **NOT** ejecutando la versión más reciente de Campaign, los parámetros y las secciones de interfaz de usuario que se describen a continuación le seguirán siendo aplicables.

### Reintentos {#legacy-retries}

La configuración **[!UICONTROL Retries]** del [menú Configuración](#email-channel-parameters) y de los [Parámetros de envío](#retries-parameters) de las propiedades de correo electrónico indican cuántos reintentos se deben realizar el día después de que se inicie el envío (**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**) y el retardo mínimo entre los reintentos (**[!UICONTROL Retry period]**).

El número de reintentos se puede cambiar globalmente (póngase en contacto con el administrador técnico del Adobe) o para cada envío o plantilla de envío.

De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, distribuidos en las 24 horas del día. Después de ello, se programa un reintento por día hasta la fecha límite de envío, que se define globalmente en la sección **[!UICONTROL Delivery parameters]** del menú **[!UICONTROL Configuration]** o en la sección **[!UICONTROL Validity period]** en el nivel de envío (consulte la sección [Duración de envío](#legacy-delivery-duration) a continuación).

### Duración de la entrega {#legacy-delivery-duration}

El parámetro **[!UICONTROL Message delivery duration]** del [menú de configuración](#email-channel-parameters) le permite especificar el lapso de tiempo en el que se reintentará cualquier mensaje del envío que detecte un error temporal o una devolución del mensaje.

El parámetro **[!UICONTROL Delivery duration]** o **[!UICONTROL Validity limit for sending messages]** de la sección [Parámetros del periodo de validez](#validity-period-parameters) permite especificar la duración durante la cual se pueden enviar los mensajes.

### Reglas de procesamiento de correo electrónico {#legacy-email-processing-rules}

Los administradores pueden acceder y modificar las reglas **[!UICONTROL MX management]**, **[!UICONTROL Bounce mails]** y **[!UICONTROL Domain management]** a través del **[!UICONTROL Administration > Channels > Email > Email processing rules]** [menú](#email-processing-rules).

### Clasificación del correo rechazado {#legacy-bounce-mail-qualification}

Para enumerar los distintos rechazos y sus tipos de error asociados y sus motivos, haga clic en el logotipo **Adobe** en la parte superior izquierda y, a continuación, seleccione **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

Las devoluciones pueden tener los siguientes estados de calificación:

* **[!UICONTROL To qualify]**: el correo rechazado debe estar clasificado. El equipo de entrega debe realizar la clasificación para garantizar que la capacidad de entrega de la plataforma funciona correctamente. Siempre y cuando no esté clasificado, el correo rechazado no se utiliza para enriquecer la lista de reglas de procesamiento de correo electrónico.
* **[!UICONTROL Keep]**: el correo rechazado se ha clasificado y el flujo de trabajo  **Update for** deliverability lo usa para compararlo con las reglas de procesamiento de correo electrónico existentes y enriquecer la lista.
* **[!UICONTROL Ignore]**: el correo rechazado se ha clasificado, pero el flujo de trabajo  **Update for** deliverability no lo usa. Por lo tanto, no se envía a las instancias de cliente.

>[!NOTE]
>
>En caso de una interrupción de un ISP, los correos electrónicos enviados a través de Campaign se marcan erróneamente como rechazos. Para corregir esto, debe actualizar la calificación de devoluciones. Para obtener más información, consulte [esta página](../../administration/using/update-bounce-qualification.md).

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### Informes de indicadores entregados {#legacy-delivered-status-report}

En la vista **[!UICONTROL Summary]** de cada mensaje, el porcentaje **[!UICONTROL Delivered]** aumentará progresivamente durante el periodo de validez del envío, a medida que se devuelvan los informes de devoluciones leves y duras.

Los mensajes de devolución en blanco se mostrarán como **[!UICONTROL Failed]** después del primer día del envío y se volverán a intentar en cada día adicional del periodo de validez del envío.

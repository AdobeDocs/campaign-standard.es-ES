---
title: Configuración de canales de correo electrónico
description: Obtenga información sobre cómo configurar el canal de correo electrónico.
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
source-git-commit: a3f760385da20a3aa39f96d955cfc2d77b708de2

---


# Configuración de canales de correo electrónico{#configuring-email-channel}

## Parámetros de canal de correo electrónico {#email-channel-parameters}

La pantalla de configuración de correo electrónico permite definir los parámetros del canal de correo electrónico.

![](assets/channels_1.png)

* **Parámetros de encabezado de correos electrónicos enviados**

   En esta sección, puede especificar la dirección de remitente y la dirección de error **[!UICONTROL masks]**autorizada. Si es necesario, estas máscaras se pueden separar mediante comas. Esta configuración es opcional. Cuando se especifican estos campos, durante la fase de preparación del mensaje, Adobe Campaign comprueba que las direcciones especificadas son válidas. Este modo operativo garantiza que no se utilicen direcciones que puedan desencadenar problemas de entrega. Las direcciones de entrega deben configurarse en el servidor de entrega.

* **Capacidad de entrega**

   Esta ID la proporciona la asistencia técnica. Es necesario que los informes de entregabilidad funcionen correctamente.

* **Parámetros de envío**

   Adobe Campaign envía los mensajes a partir de la fecha de inicio. El **[!UICONTROL Message delivery duration]**campo permite especificar la duración durante la cual se pueden enviar los mensajes.

   The **[!UICONTROL Online resources validity duration]**field is used for uploaded resources, mainly for the mirror page and images. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).

* **Reintentos**

   Los mensajes no entregados temporalmente están sujetos a un reintento automático. Esta sección indica cuántos reintentos se deben realizar el día siguiente al inicio del envío (**Número de reintentos**) y el retraso mínimo entre reintentos (período **de** reintento).

   De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, repartidos en las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]**section.

* **Parámetros de cuarentena de correo electrónico**

   En el **[!UICONTROL Time between two significant errors]**campo, introduzca un valor para definir el tiempo que la aplicación espera antes de incrementar el contador de errores en caso de error. Valor predeterminado:**&quot;1d&quot;**, durante 1 día.

   Cuando se alcanza el **[!UICONTROL Maximum number of errors before quarantine]**valor, la dirección de correo electrónico se pone en cuarentena. Valor predeterminado:**&quot;5&quot;**: la dirección se pondrá en cuarentena en el sexto error. Esto significa que el contacto se excluirá automáticamente de las entregas posteriores.

**Tema** relacionado:

[Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)

## Cuentas de enrutamiento de correo electrónico {#email-routing-accounts}

La cuenta **[!UICONTROL Integrated email routing]**externa se proporciona de forma predeterminada. Contiene los parámetros técnicos que permiten a la aplicación enviar correos electrónicos.

![](assets/channels_2.png)

El tipo de cuenta siempre debe estar establecido en **[!UICONTROL Routing]**, el canal a**[!UICONTROL Email]** y el modo de entrega establecido en **[!UICONTROL Bulk delivery]**.

**Tema** relacionado:

[Cuentas externas](../../administration/using/external-accounts.md)

## Reglas de procesamiento de correo electrónico {#email-processing-rules}

Estas reglas contienen la lista de cadenas de caracteres que pueden devolver los servidores remotos y que le permiten clasificar el error (**Grave**, **leve** o **ignorado**).

Las reglas predeterminadas son las siguientes:

**Mensajes de devolución**

Cuando falla un mensaje de correo electrónico, el servidor de mensajes remoto devuelve un mensaje de error de devolución a la dirección especificada en la configuración de la aplicación. Adobe Campaign compara el contenido de cada mensaje de rechazo con las cadenas de la lista de reglas y, a continuación, lo asigna a uno de los tres tipos de error.

El usuario puede crear sus propias reglas.

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**Administración de dominios de correo electrónico**

Las reglas de administración de dominios se utilizan para regular el flujo de correos electrónicos salientes para un dominio específico. Realizan muestras de los mensajes de rechazo y bloquean el envío a donde corresponda. El servidor de mensajería de Adobe Campaign aplica reglas específicas a los dominios y, a continuación, las reglas para el caso general representado por un asterisco en la lista de reglas. Las reglas para los dominios de Hotmail y MSN están disponibles de forma predeterminada en Adobe Campaign.

Para configurar las reglas de administración de dominios, simplemente configure un umbral y seleccione ciertos parámetros SMTP. Un **umbral** es un límite calculado como un porcentaje de error por encima del cual se bloquean todos los mensajes dirigidos a un dominio específico.

Por ejemplo, en el caso general, para un mínimo de 300 mensajes, el envío de correos electrónicos se bloquea durante tres horas si la tasa de error alcanza el 90 %.

Los **parámetros SMTP** actúan como filtros aplicados a una regla de bloqueo.

* Se puede elegir si activar o no determinadas normas de identificación y claves de cifrado para comprobar el nombre del dominio como, por ejemplo, **ID de remitente**, **DomainKeys**, **DKIM** y **S/MIME**.
* **SMTP relay**: permite configurar la dirección IP y el puerto de un servidor de transmisión para un dominio determinado.

**Administración MX**

Cada regla define una máscara de dirección para el MX. Cualquier MX cuyo nombre coincida con esta máscara es elegible. La máscara puede contener &quot;*&quot; y &quot;?&quot; caracteres genéricos.

Por ejemplo, las siguientes direcciones:

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

son compatibles con las siguientes máscaras:

* *.yahoo.com
* ?.mx.yahoo.com

Estas reglas se aplican de forma secuencial: se aplica la primera regla cuya máscara MX es compatible con el MX de destino.

Los siguientes parámetros están disponibles para cada regla:

* **[!UICONTROL Range of IDs]**:: esta opción le permite indicar los rangos de identificadores (publicId) para los que se aplica la regla. Puede especificar:

   * Un número: la regla solo se aplicará a este publicId.
   * Un rango de números (número1-número2): la regla se aplicará a todos los publicIds entre estos dos números.
   Si el campo está vacío, la regla se aplica a todos los ID.

* **[!UICONTROL Shared]**:: esta opción indica que el mayor número de mensajes por hora y de conexiones se aplica a todos los MX vinculados a esta regla.
* **[!UICONTROL Maximum number of connections]**:: número máximo de conexiones simultáneas a un MX desde una dirección determinada.
* **Número máximo de mensajes**: número máximo de mensajes que se pueden enviar mediante una conexión. Después de esta cantidad, la conexión se cierra y se vuelve a abrir una nueva.
* **[!UICONTROL Messages per hour]**:: número máximo de mensajes que se pueden enviar en una hora para un MX a través de una dirección determinada.

>[!CAUTION]
>
>* El servidor de envío (MTA) debe reiniciarse si los parámetros se han modificado.
>* La modificación o creación de reglas de administración solo es para usuarios expertos.
>



## Lista de propiedades de correo electrónico {#list-of-email-properties}

Esta sección detalla la lista de parámetros disponibles en la pantalla de propiedades de una plantilla de correo electrónico o de correo electrónico.

>[!NOTE]
>
>Algunos parámetros solo están disponibles en plantillas. Los parámetros a los que puede acceder [dependen de sus permisos](../../administration/using/users-management.md).

Para editar las propiedades de un correo electrónico o una plantilla de correo electrónico, utilice el **[!UICONTROL Edit properties]**botón .

![](assets/delivery_options_1.png)

### Parámetros generales {#general-parameters}

En la parte superior de la pantalla del parámetro de correo electrónico, identifique el correo electrónico mediante los campos **[!UICONTROL Label]**y**[!UICONTROL ID]** . Esta información aparece en la interfaz pero no es visible para los destinatarios del mensaje.

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>El ID debe ser único.

El **[!UICONTROL Brand]**campo permite seleccionar la marca vinculada a la entrega. Para obtener más información sobre el uso y la configuración de marcas, consulte la sección[Marcas](../../administration/using/branding.md).

El **[!UICONTROL Campaign]**campo permite introducir la campaña vinculada al correo electrónico.

También puede agregar un **[!UICONTROL Description]**en el campo correspondiente y editar la imagen mostrada en la miniatura de correo electrónico en las listas.

### Envío de parámetros {#sending-parameters}

La **[!UICONTROL Send]**sección solo está disponible para plantillas de correo electrónico. Contiene los siguientes parámetros:

#### Parámetros de reintentos {#retries-parameters}

Los mensajes no entregados temporalmente están sujetos a un reintento automático. Esta sección indica cuántos reintentos se deben realizar el día siguiente al inicio del envío ( **[!UICONTROL Max. number of retries]**) y el retraso mínimo entre reintentos (**[!UICONTROL Retry period]** ).

De forma predeterminada, se programan cinco reintentos para el primer día con un intervalo mínimo de una hora, repartidos en las 24 horas del día. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

El número de reintentos se puede cambiar globalmente (póngase en contacto con el administrador técnico de Adobe) o para cada plantilla de entrega o entrega

#### Parámetros de formato de correo electrónico {#email-format-parameters}

Puede configurar el formato de los mensajes de correo electrónico que se van a enviar. Hay tres opciones disponibles:

* **Usar preferencias** de destinatario (modo predeterminado): el formato del mensaje se define según los datos almacenados en el perfil del destinatario y se almacena de forma predeterminada en el campo Formato **de** correo electrónico (@emailFormat). Si un destinatario desea recibir mensajes en un formato determinado, este es el formato enviado. Si el campo no se ha completado, se envía un mensaje alternativo de varias partes (véase más adelante).
* **Permita que el cliente de correo del destinatario elija el formato más adecuado (multipart-alternativa)**: el mensaje contiene ambos formatos: texto y HTML. El formato que se muestra tras la recepción depende de la configuración del software de correo del destinatario (multipart-alternativa).

   >[!CAUTION]
   >
   >Esta opción incluye ambas versiones del mensaje. Por lo tanto, afecta al rendimiento de la entrega, ya que el tamaño del mensaje es mayor.

* **Enviar todos los mensajes en formato** de texto: el mensaje se envía en formato de texto. El formato HTML no se enviará, sino que se utilizará para la página de reflejo únicamente cuando el destinatario haga clic en el vínculo del mensaje.

#### Modo de prueba SMTP {#smtp-test-mode}

La **[!UICONTROL Enable SMTP test mode]**opción le permite probar el envío de correos electrónicos a través de una conexión SMTP sin realmente enviar mensajes.
Los mensajes se procesan hasta que se logra la conexión con el servidor SMTP, pero no se envían.

![](assets/smtp-test-mode.png)

Esta opción está disponible para correos electrónicos y plantillas de correo electrónico.

Si activa la opción de modo de prueba SMTP para una plantilla de correo electrónico, todos los mensajes de correo electrónico creados a partir de esta plantilla tendrán esta opción activada.

>[!CAUTION]
>
>Cuando esta opción está habilitada para un correo electrónico, no se enviará ningún mensaje hasta que no esté activada.
>Se mostrará una advertencia en el tablero de plantillas de correo electrónico o correo electrónico.

Para obtener más información sobre la configuración de SMTP, consulte la sección [Lista de parámetros](#list-of-email-smtp-parameters) SMTP de correo electrónico.

### Parámetros del período de validez {#validity-period-parameters}

La **[!UICONTROL Validity]**sección contiene los siguientes parámetros:

* **[!UICONTROL Explicitly set validity dates]**:: cuando esta casilla está desactivada, debe introducir una duración en los campos**[!UICONTROL Delivery duration]** y **[!UICONTROL Resource validity limit]**. Marque esta casilla si desea definir fechas y horas específicas.
* **[!UICONTROL Delivery duration]**::Adobe Campaign envía los mensajes a partir de la fecha de inicio. Este campo permite especificar la duración durante la cual se pueden enviar los mensajes.
* **[!UICONTROL Resource validity duration]**:: este campo se utiliza para los recursos cargados, principalmente para la página reflejada y las imágenes. Los recursos de esta página son válidos durante un tiempo limitado (para ahorrar espacio en el disco).
* **[!UICONTROL Mirror page management]**:: la página reflejada es una página HTML a la que se puede acceder en línea a través de un navegador web. Su contenido es idéntico al del correo electrónico. De forma predeterminada, la página reflejada se genera si el vínculo se inserta en el contenido del correo. Este campo permite modificar la forma en que se genera esta página:

   >[!CAUTION]
   >
   >Se debe haber definido un contenido HTML para el correo electrónico de la página reflejada que se va a crear.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]**(modo predeterminado): la página reflejada se genera si el vínculo se inserta en el contenido del correo.
   * **Forzar la generación de la página** de reflejo: aunque no se inserte ningún vínculo a la página de reflejo en los mensajes, se creará la página de reflejo.
   * **No genere la página** reflejada: no se genera ninguna página reflejada, aunque el vínculo esté en los mensajes.
   * **Genere una página reflejada a la que se pueda acceder utilizando únicamente el ID** del mensaje: esta opción le permite acceder al contenido de la página reflejada, con información de personalización, en la ventana del registro de entrega.

>[!NOTE]
>
>Los parámetros **[!UICONTROL Explicitly set validity dates]**y**[!UICONTROL Delivery duration]** no se aplican a los mensajes transaccionales. Para obtener más información sobre la mensajería transaccional, consulte [esta sección](../../channels/using/about-transactional-messaging.md).

### Parámetros de seguimiento {#tracking-parameters}

La **[!UICONTROL Tracking]**sección contiene los siguientes parámetros:

* **[!UICONTROL Activate tracking]**:: le permite activar o desactivar el seguimiento de direcciones URL de mensajes. Para administrar el seguimiento de cada dirección URL de mensaje, utilice el**[!UICONTROL Links]** icono de la barra de acciones de Email Designer. Consulte [Acerca de las direcciones URL](../../designing/using/links.md#about-tracked-urls)rastreadas.
* **[!UICONTROL Tracking validity limit]**:: le permite definir la duración durante la cual se activará el seguimiento en las direcciones URL.
* **[!UICONTROL Substitution URL for expired URLs]**:: puede introducir una dirección URL a una página web que se mostrará una vez que el seguimiento haya caducado.

### Parámetros avanzados {#advanced-parameters}

La **[!UICONTROL Advanced parameters]**sección contiene varios parámetros.

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

* **[!UICONTROL Typology]**:: antes de cualquier envío, los mensajes deben prepararse para validar el contenido y la configuración. The verification rules applied during the preparation phase are defined in a** typology **. Por ejemplo, para los correos electrónicos, la preparación implica comprobar el asunto, las direcciones URL y las imágenes, etc. Seleccione la tipología que se aplicará en este campo.

   >[!NOTE]
   >
   >Las tipologías, a las que se puede acceder a través del **[!UICONTROL Administration]**menú >**[!UICONTROL Channels]** > **[!UICONTROL Typologies]**, se presentan en la sección[Tipologías](../../administration/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**:: permite calcular el valor de etiqueta del correo electrónico durante la fase de preparación del mensaje mediante campos de personalización, bloques de contenido y texto dinámico.

   También es posible personalizar la etiqueta de entrega con variables de eventos que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información, consulte [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**:: esta opción le permite agregar registros de consultas SQL en el diario durante la fase de preparación.

### Lista de parámetros SMTP de correo electrónico {#list-of-email-smtp-parameters}

La **[!UICONTROL SMTP]**sección contiene los siguientes parámetros:

* **[!UICONTROL Character encoding]**:: marque la**[!UICONTROL Force encoding]** casilla si desea forzar la codificación del mensaje y, a continuación, seleccione la codificación que desee utilizar.
* **[!UICONTROL Bounce mails]**:: de forma predeterminada, los mensajes de devolución se reciben en la bandeja de entrada de errores de la plataforma (definida en la pantalla**[!UICONTROL Administration]** > **[!UICONTROL Channels]**>**[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Para definir una dirección de error específica para un correo electrónico, introduzca la dirección en el**[!UICONTROL Error address]** campo.
* **[!UICONTROL Additional SMTP headers]**:: esta opción permite agregar encabezados SMTP adicionales a los mensajes. La secuencia de comandos introducida en el**[!UICONTROL Headers]** campo debe hacer referencia a un encabezado por línea, en forma de **nombre:valor**. Los valores se codifican automáticamente si es necesario.

   >[!CAUTION]
   >
   >La adición de secuencias de comandos para insertar encabezados SMTP se reserva para usuarios avanzados. La sintaxis de esta secuencia de comandos debe cumplir con los requisitos de este tipo de contenido: no dejar espacios sin utilizar, ninguna línea vacía, etc.

### Lista de parámetros de autorización de acceso {#list-of-access-authorization-parameters}

La **[!UICONTROL Access authorization]**sección contiene los siguientes parámetros:

* El **[!UICONTROL Organizational unit]**campo permite restringir el acceso a este correo electrónico a determinados usuarios. Los usuarios asociados con la unidad o las unidades principales especificadas tendrán acceso de lectura y escritura a este correo electrónico. Los usuarios asociados con unidades secundarias solo tendrán acceso de lectura a este correo electrónico.

   >[!NOTE]
   >
   >Puede configurar las unidades organizativas mediante el menú **Administración** > **Usuarios y seguridad** .

* Los campos **[!UICONTROL Created by]**,**[!UICONTROL Created]****[!UICONTROL Modified by]**y**[!UICONTROL Last modified]** se completan automáticamente.

## Archivado de correos electrónicos {#archiving-emails}

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma.

Sin embargo, la propia Adobe Campaign no administra los archivos archivados. Le permite enviar los mensajes de su elección a una dirección dedicada, desde donde se pueden procesar y archivar usando un sistema externo.

Cuando se activa en la plantilla de envío, esta función le permite enviar una copia exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de la entrega) que debe especificar.

### Recomendaciones y limitaciones {#recommendations-and-limitations}

* Esta función es opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.
* Solo puede usar una dirección de correo electrónico CCO.
* Solo se tienen en cuenta los correos electrónicos enviados correctamente. Las devoluciones no lo son.
* Por razones de privacidad, los correos electrónicos CCO deben ser procesados por un sistema de archiving capaz de almacenar información personal (PII) de manera segura.
* Al crear una nueva plantilla de entrega, Email BCC no está habilitado de forma predeterminada, aunque la opción se haya adquirido. Debe habilitarlo manualmente en cada plantilla de envío donde desee utilizarla.

### Activación del archivado de correo electrónico {#activating-email-archiving}

Email BCC se activa en la plantilla [de](../../start/using/marketing-activity-templates.md)correo electrónico mediante una opción dedicada:

1. Go to **Resources** > **Templates** > **Delivery templates**.
1. Duplique la plantilla lista para usar **[!UICONTROL Send via email]**.
1. Seleccione la plantilla duplicada.
1. Haga clic en el **[!UICONTROL Edit properties]**botón para editar las propiedades de la plantilla.
1. Expanda la **[!UICONTROL Send]**sección.
1. Marque la **[!UICONTROL Archive emails]**casilla para guardar una copia de todos los mensajes enviados para cada envío en función de esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]**and**[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

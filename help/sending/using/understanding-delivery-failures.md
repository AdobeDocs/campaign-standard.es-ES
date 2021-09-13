---
title: Comprensión de los errores de entrega
description: Aprenda a administrar los errores de envío con Campaign.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 71%

---

# Comprensión de los errores de entrega{#understanding-delivery-failures}

## Acerca de los errores de entrega {#about-delivery-failures}

Cuando una entrega no se puede enviar a un perfil, el servidor remoto envía automáticamente un mensaje de error que recoge la plataforma de Adobe Campaign para determinar si la dirección de correo electrónico o el número de teléfono deben ponerse en cuarentena. Consulte [Cualificación de correo rechazado](#bounce-mail-qualification).

>[!NOTE]
>
>Los mensajes de error de **correo electrónico** (o “devoluciones”) están calificados por el MTA mejorado (devoluciones sincrónicas) o por el proceso de inMail (devoluciones asincrónicas).
>
>**Los mensajes de error de SMS (o “SR”, de “informe de estado”) se clasifican mediante el proceso MTA.**

Los mensajes también se pueden excluir durante la preparación de la entrega si una dirección está en cuarentena o si un perfil está en la  de la lista de bloqueados. Los mensajes excluidos se enumeran en la pestaña **[!UICONTROL Exclusion logs]** del panel de entrega (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Temas relacionados:**

* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [Devoluciones](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## Identificación de errores de entrega para un mensaje {#identifying-delivery-failures-for-a-message}

Una vez que se envía una entrega, la pestaña **[!UICONTROL Sending logs]** (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#sending-logs)) le permite ver el estado de entrega de cada perfil y el tipo y motivo de error asociados (consulte [Tipos y motivos de error de entrega](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

También hay disponible un informe dedicado listo para su uso. Este informe detalla los errores generales, tanto los errores graves como los leves que se han encontrado durante las entregas, así como el procesamiento automático de las devoluciones. Para obtener más información, consulte [esta sección](../../reporting/using/bounce-summary.md).

## Tipos y motivos de errores de entrega {#delivery-failure-types-and-reasons}

Existen tres tipos de errores cuando falla una entrega:

* **Hard**: Un error “grave” indica una dirección no válida. Esto implica un mensaje de error que indica explícitamente que la dirección no es válida, como: “Usuario desconocido”.
* **Soft**: Podría tratarse de un error temporal o uno que no se pudiera categorizar, como: “Dominio no válido” o “Buzón lleno”.
* **Ignored**: Se trata de un error temporal, como “Fuera de la oficina”, o un error técnico, por ejemplo, si el tipo de remitente es “Administrador de correo”.

Los posibles motivos de un error de entrega son:

| Etiqueta de error | Tipo de error | Descripción |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | Grave | La dirección no existe. No se intenta realizar entregas adicionales para este perfil. |
| **[!UICONTROL Quarantined address]** | Grave | La dirección se envió a cuarentena. |
| **[!UICONTROL Unreachable]** | Leve/Grave | Se ha producido un error en la cadena de entrega de mensajes (como un dominio temporalmente inaccesible). Según el error devuelto por el proveedor, la dirección se enviará directamente a cuarentena o la entrega se volverá a intentar hasta que Campaign reciba un error que justifique el estado de la cuarentena o hasta que el número de errores alcance 5. |
| **[!UICONTROL Address empty]** | Grave | La dirección no está definida. |
| **[!UICONTROL Mailbox full]** | Leve | El buzón de este usuario está lleno y no puede aceptar más mensajes. Esta dirección se puede eliminar de la lista de cuarentena para realizar otro intento. Se elimina automáticamente al cabo de 30 días. Para que la dirección se elimine de forma automática de la lista de direcciones en cuarentena, debe iniciarse el flujo de trabajo técnico **[!UICONTROL Database cleanup]**. |
| **[!UICONTROL Refused]** | Leve/Grave | La dirección se ha enviado a cuarentena debido a un comentario de seguridad que informa de correo no deseado. Según el error devuelto por el proveedor, la dirección se enviará directamente a cuarentena o la entrega se volverá a intentar hasta que Campaign reciba un error que justifique el estado de la cuarentena o hasta que el número de errores alcance 5. |
| **[!UICONTROL Duplicate]** | Ignorado | La dirección ya se ha detectado en la segmentación. |
| **[!UICONTROL Not defined]** | Leve | la dirección se encuentra sin clasificar porque no se han sumado errores. | sin embargo. Este tipo de error se produce cuando el servidor envía un nuevo mensaje de error: puede tratarse de un error aislado; sin embargo, si vuelve a producirse, el contador de errores aumenta, lo que advierte a los equipos técnicos. |
| **[!UICONTROL Error ignored]** | Ignorado | La dirección está en lista de permitidos y se le enviará un correo electrónico en cualquier caso. |
| **[!UICONTROL Address on denylist]** | Grave | La dirección se agregó a la lista de bloqueados al momento del envío. |
| **[!UICONTROL Account disabled]** | Leve/Grave | Cuando el proveedor de acceso a Internet (IAP) detecta un largo periodo de inactividad, puede cerrar la cuenta del usuario: los envíos a la dirección del usuario serán imposibles. El tipo leve o grave depende del tipo de error recibido: si la cuenta se desactiva temporalmente debido a seis meses de inactividad y aún puede activarse, el estado **[!UICONTROL Erroneous]** se asignará y el envío se volverá a intentar. Si el error recibido indica que la cuenta está desactivada de forma permanente, se envía directamente a Cuarentena. |
| **[!UICONTROL Not connected]** | Ignorado | El teléfono móvil del perfil está apagado o no está conectado a la red cuando se envía el mensaje. |
| **[!UICONTROL Invalid domain]** | Leve | El dominio de la dirección del correo electrónico es incorrecto o ya no existe. Este perfil se vuelve a seleccionar hasta que el recuento de errores llegue a 5. Después de esto, el registro se pone en estado de cuarentena y no se realiza ningún reintento. |
| **[!UICONTROL Text too long]** | Ignorado | El número de caracteres del mensaje SMS supera el límite. Para obtener más información, consulte [Codificación, longitud y transliteración del SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Character not supported by encoding]** | Ignorado | El mensaje SMS contiene uno o varios caracteres que no son compatibles con la codificación. Para obtener más información, consulte [Tabla de caracteres: estándar GSM](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |


**Temas relacionados:**
* [Rechazos graves](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [Rechazos leves](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## Reintentos tras un fallo temporal de entrega {#retries-after-a-delivery-temporary-failure}

Si un mensaje falla debido a un error temporal, los reintentos se realizan durante la duración del envío. Para obtener más información sobre los tipos de errores, consulte [Tipos y motivos de errores de entrega](#delivery-failure-types-and-reasons).

El número de reintentos (cuántos reintentos se deben realizar el día siguiente al inicio del envío) y el retardo mínimo entre los reintentos ahora son<!--managed by the Adobe Campaign Enhanced MTA,--> en función del rendimiento histórico y actual de una IP en un dominio determinado. La configuración de **Reintentos** en Campaign se ignora.

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

Para modificar la duración de una entrega, vaya a los parámetros avanzados de la entrega o la plantilla de entrega y edite el campo **[!UICONTROL Delivery duration]** de la sección [Periodo de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**El parámetro **[!UICONTROL Delivery duration]**de las entregas de Campaign ahora solo se utiliza si se establece en 3,5 días o menos.** Si define un valor superior a 3,5 días, no se tendrá en cuenta.

Por ejemplo, si desea que los reintentos de un envío se detengan después de un día, puede establecer la duración del envío en **1d** y los mensajes de la cola de reintentos se eliminarán después de un día.

>[!NOTE]
>
>Una vez que un mensaje ha estado en la cola de reintentos durante un máximo de 3,5 días y no se ha podido entregar, se agotará el tiempo de espera y su estado se actualizará<!--from **[!UICONTROL Sent]**--> a **[!UICONTROL Failed]** en los [registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Errores sincrónicos y asíncronos {#synchronous-and-asynchronous-errors}

Una entrega puede fallar inmediatamente (error sincrónico), o más tarde, después de enviarla (error asíncrono).

* **Error sincrónico**: el servidor remoto contactado mediante el servidor de entrega de Adobe Campaign devuelve inmediatamente un mensaje de error y la entrega no puede enviarse al servidor del perfil.
* **Error asíncrono**: el servidor receptor reenvía más tarde un correo electrónico devuelto o una SR. Pueden producirse errores asíncronos hasta una semana después de mandar la entrega.

## Clasificación del correo rechazado {#bounce-mail-qualification}

Para los mensajes de error de error de envío sincrónico, el MTA mejorado de Adobe Campaign (Agente de transferencia de mensajes) determina el tipo de rechazo y la calificación, y envía esa información a Campaign.

>[!NOTE]
>
>Ya no se utilizan las cualificaciones de devolución de la tabla **[!UICONTROL Message qualification]** de Campaign.

Las devoluciones asincrónicas siguen siendo calificadas por el proceso enMail a través de las **[!UICONTROL Inbound email]** reglas. Para acceder a estas reglas, haga clic en el logotipo **Adobe** en la parte superior izquierda, luego seleccione **[!UICONTROL Administration > Channels > Email > Email processing rules]** y seleccione **[!UICONTROL Bounce mails]**. Para obtener más información sobre esta regla, consulte [esta sección](../../administration/using/configuring-email-channel.md#email-processing-rules).

Para obtener más información sobre las devoluciones y los distintos tipos de devoluciones, consulte [esta sección](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimización de la capacidad de entrega de correo electrónico con el mecanismo de inclusión doble {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

El mecanismo de inclusión doble es una práctica recomendada al enviar correos electrónicos. Protege la plataforma de direcciones de correo electrónico erróneas o no válidas, bots de spam y evita posibles reclamaciones de spam.

El principio es enviar un correo electrónico para confirmar el acuerdo del visitante antes de almacenarlo como “perfiles” en la base de datos de Campaign: el visitante rellena una página de aterrizaje en línea, luego recibe un correo electrónico y tiene que hacer clic en el enlace de confirmación para finalizar su suscripción.

Para obtener más información, consulte [esta sección](../../channels/using/setting-up-a-double-opt-in-process.md).

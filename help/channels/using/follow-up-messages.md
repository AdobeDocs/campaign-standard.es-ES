---
title: Mensajes de seguimiento
description: Obtenga información sobre cómo crear y publicar un mensaje de seguimiento.
page-status-flag: never-activated
uuid: d2a17da2-e935-420a-8531-78ed6a1fe68b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 9615e369-754f-4f6a-a1b1-14462f946666
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 5%

---


# Mensajes de seguimiento{#follow-up-messages}

Puede enviar un mensaje de seguimiento a los clientes que hayan recibido un mensaje transaccional específico. Para ello, debe configurar un flujo de trabajo dirigido al evento correspondiente.

Vamos a reutilizar el ejemplo descrito en la sección de principios [operativos de mensajería](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) transaccional: se envía un correo electrónico de abandono del carro de compras a los usuarios del sitio web que han agregado productos al carro de compras, pero que han abandonado el sitio sin pasar por sus compras.

Desea enviar un recordatorio práctico a todos los clientes que recibieron la notificación de abandono del carro de compras pero que no la abrieron después de tres días.

A continuación, cada cliente interesado recibirá un mensaje de seguimiento basado en los mismos datos que se usaron en el primer correo electrónico enviado.

## Acceso a los mensajes de seguimiento {#accessing-the-follow-up-messages}

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) above), the corresponding transactional message and follow-up message are created automatically.

The configuration steps are presented in the [Configuring an event to send a follow-up message](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message) section.

Para gestionar un evento en un flujo de trabajo, se requiere una Plantilla de envíos. Sin embargo, al publicar el evento, el [mensaje transaccional](../../channels/using/event-transactional-messages.md) que se crea no se puede usar como plantilla. Por lo tanto, debe crear una Plantilla de envíos de seguimiento específica diseñada para admitir este tipo de evento y para utilizarse como plantilla en un flujo de trabajo.

Para acceder a esta plantilla:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Marque la **[!UICONTROL Follow-up messages]** casilla en el panel izquierdo.

   ![](assets/message-center_follow-up-search.png)

Solo se muestran los mensajes de seguimiento.

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de seguridad **[!UICONTROL Administrators (all units)]**.

## Envío de un mensaje de seguimiento {#sending-a-follow-up-message}

Una vez creada la Plantilla de envíos de seguimiento, puede utilizarla en un flujo de trabajo para enviar un mensaje de seguimiento.

1. Acceda a la lista de actividad de marketing y cree un nuevo flujo de trabajo.

   Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow and open it. Establezca la frecuencia de ejecución en una vez al día.

   La actividad del Planificador se presenta en la sección [Planificador](../../automating/using/scheduler.md) .

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. Para ejecutar la consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y haga clic en la lista **[!UICONTROL Resource]** desplegable.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >De forma predeterminada, la actividad está preconfigurada para buscar perfiles.

1. Seleccione el evento que desea destinatario para que solo pueda acceder a los datos de este evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vaya a la ficha de la actividad **[!UICONTROL Target]** y arrastre y suelte el **[!UICONTROL Delivery logs (logs)]** elemento de la paleta en el espacio de trabajo.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Seleccione **[!UICONTROL Exists]** para el destinatario de todos los clientes que recibieron el correo electrónico.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Mueva el **[!UICONTROL Tracking logs (tracking)]** elemento de la paleta al espacio de trabajo y seleccione **[!UICONTROL Does not exist]** el destinatario de todos los clientes que no abrieron el correo electrónico.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Arrastre y suelte el evento objetivo (abandono **del** carro en este ejemplo) desde la paleta al espacio de trabajo. A continuación, defina una regla para el destinatario de todos los mensajes enviados hace tres días.

   ![](assets/message-center_follow-up-created.png)

   Esto significa que todos los destinatarios que recibieron el mensaje transaccional tres días antes de la ejecución del flujo de trabajo y que aún no lo han abierto están segmentados.

   Click **[!UICONTROL Confirm]** to save the query.

1. Drag and drop an **Email delivery** activity into your workflow.

   La actividad envío de correo electrónico se presenta en la sección envío [de](../../automating/using/email-delivery.md) correo electrónico.

   ![](assets/message-center_follow-up-workflow.png)

   También puede usar un envío [](../../automating/using/sms-delivery.md) SMS o una actividad de envío [de aplicaciones](../../automating/using/push-notification-delivery.md) móviles. En este caso, asegúrese de seleccionar el **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** canal al crear la configuración de evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Open the **Email delivery** activity. En el asistente de creación, marque la **[!UICONTROL Follow-up messages]** casilla y seleccione la Plantilla de envíos de seguimiento que se creó después de publicar el evento.

   ![](assets/message-center_follow-up-template.png)

1. En el contenido del mensaje de seguimiento, puede aprovechar el contenido del evento agregando campos de personalización.

   ![](assets/message-center_follow-up-content.png)

1. Busque los campos que definió al crear el evento seleccionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. See [Personalizing a transactional message](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Esto significa que puede aprovechar el mismo contenido, incluidos los datos enriquecidos, que se utilizó la primera vez que se envió el evento, para crear un recordatorio personalizado y sencillo.

1. Guarde la actividad y inicio del flujo de trabajo.

Una vez iniciado el flujo de trabajo, todos los clientes que hayan recibido la notificación de abandono del carro de compras hace tres días pero que no la hayan abierto recibirán un mensaje de seguimiento basado en los mismos datos.

>[!NOTE]
>
>Si seleccionó la **[!UICONTROL Profile]** dimensión de segmentación al crear la configuración de evento, el mensaje de seguimiento también aprovechará la base de datos de marketing de Adobe Campaign. Consulte [Mensajes transaccionales de perfil ](../../channels/using/profile-transactional-messages.md).

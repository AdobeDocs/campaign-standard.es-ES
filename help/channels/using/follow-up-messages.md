---
title: Mensajes de seguimiento
seo-title: Mensajes de seguimiento
description: Mensajes de seguimiento
seo-description: Descubra cómo crear y publicar un mensaje de seguimiento.
page-status-flag: no activado nunca
uuid: d 2 a 17 da 2-e 935-420 a -8531-78 ed 6 a 1 fe 68 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajes transaccionales
discoiquuid: 9615 e 369-754 f -4 f 6 a-a 1 b 1-14462 f 946666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Follow-up messages{#follow-up-messages}

Puede enviar un mensaje de seguimiento a los clientes que recibieron un mensaje de transacción específico. Para ello, debe configurar un flujo de trabajo dirigido al evento correspondiente.

Let's reuse the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section: a cart abandonment email is sent to your website users who added products to their cart, but left the site without going through with their purchases.

Desea enviar un recordatorio práctico a todos los clientes que recibieron la notificación de abandono del carro pero que no lo abrieron después de tres días.

A continuación, cada cliente interesado recibirá un mensaje de seguimiento basado en los mismos datos que se utilizaron en el primer correo electrónico enviado.

## Accessing the follow-up messages {#accessing-the-follow-up-messages}

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message and follow-up message are created automatically.

The configuration steps are presented in the [Configuring an event to send a follow-up message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para gestionar un evento en un flujo de trabajo, se requiere una plantilla de envío. However, when publishing the event, the [transactional message](../../channels/using/event-transactional-messages.md) that is created cannot be used as a template. Por lo tanto, debe crear una plantilla de envío de seguimiento específica diseñada para admitir este tipo de evento y utilizarse como plantilla en un flujo de trabajo.

Para acceder a esta plantilla:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]**.
1. Check the **[!UICONTROL Follow-up messages]** box in the left pane.

   ![](assets/message-center_follow-up-search.png)

Solo se muestran los mensajes de seguimiento.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Sending a follow-up message {#sending-a-follow-up-message}

Una vez creada la plantilla de envío de seguimiento, puede utilizarla en un flujo de trabajo para enviar un mensaje de seguimiento.

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo.

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow and open it. Establezca la frecuencia de ejecución una vez al día.

   The Scheduler activity is presented in the [Scheduler](../../automating/using/scheduler.md) section.

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. To run the query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and click the **[!UICONTROL Resource]** drop-down list.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >De forma predeterminada, la actividad está preconfigurada para buscar perfiles.

1. Seleccione el evento al que desee dirigir para que solo pueda acceder a los datos desde este evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Go to the activity's **[!UICONTROL Target]** tab and drag and drop the **[!UICONTROL Delivery logs (logs)]** element from the **[!UICONTROL Email]** section into the workspace.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Select **[!UICONTROL Exists]** to target all of the customers who received the email.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Move the **[!UICONTROL Tracking logs (tracking)]** element from the palette to the workspace and select **[!UICONTROL Does not exist]** to target all of the customers who did not open the email.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Drag and drop the event that you are targeting (**Cart abandonment** in this example) from the **[!UICONTROL Email]** section into the workspace. Luego defina una regla para dirigirse a todos los mensajes enviados hace tres días.

   ![](assets/message-center_follow-up-created.png)

   Esto significa que se dirigirá a todos los destinatarios que reciban el mensaje transaccional tres días antes de la ejecución del flujo de trabajo y que aún no lo hayan abierto.

   Click **[!UICONTROL Confirm]** to save the query.

1. Drag and drop an **Email delivery** activity into your workflow.

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

   ![](assets/message-center_follow-up-workflow.png)

   You can also use an [SMS delivery](../../automating/using/sms-delivery.md) or a [Mobile app delivery](../../automating/using/push-notification-delivery.md) activity. In this case, make sure you select the **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** channel when creating your event configuration. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Open the **Email delivery** activity. In the creation wizard, check the **[!UICONTROL Follow-up messages]** box and select the follow-up delivery template that was created after publishing the event.

   ![](assets/message-center_follow-up-template.png)

1. En el contenido de mensaje de seguimiento, puede aprovechar el contenido del evento añadiendo campos de personalización.

   ![](assets/message-center_follow-up-content.png)

1. Find the fields that you defined when creating your event by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**. See [Personalizing a transactional message](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Esto significa que puede aprovechar el mismo contenido, incluidos los datos enriquecidos utilizados la primera vez que se envió el evento, para crear un recordatorio práctico personalizado.

1. Guarde la actividad e inicie el flujo de trabajo.

Una vez que se inicie el flujo de trabajo, cada cliente que reciba la notificación de abandono del carro de compras hace tres días, pero que no se abrió, recibirá un mensaje de seguimiento basado en los mismos datos.

>[!NOTE]
>
>If you selected the **[!UICONTROL Profile]** targeting dimension when creating the event configuration, the follow-up message will also leverage the Adobe Campaign marketing database. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).


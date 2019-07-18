---
title: Envío de mensajes en la zona horaria del destinatario
seo-title: Envío de mensajes en la zona horaria del destinatario
description: Envío de mensajes en la zona horaria del destinatario
seo-description: Obtenga información sobre cómo enviar mensajes en la zona horaria del destinatario.
page-status-flag: no activado nunca
uuid: 70228 c 07-451 f -4 ddb -8 d 26-92 a 5 a 4814 e 3 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa 980 ba -8 c 7 c -4673-a 68 f -379 d 63 e 4 b 8 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

Al administrar una campaña en la que la fecha y la hora son importantes, puede programar una entrega que tenga en cuenta la hora local de cada destinatario: recibirán correo electrónico, SMS o notificaciones push en el momento programado, en su propia zona horaria.

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

En el siguiente ejemplo, queremos enviar un código promocional que solo sea válido en el día de San Valentín para todos los clientes del mundo. Para proporcionar tiempo suficiente para utilizarlo durante el día, todos los clientes deben recibir su mensaje el 14 de febrero a las 8:00 AM, según sus husos horarios.

1. In the **[!UICONTROL Marketing activities]** tab, start creating your delivery, in our case an email. To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. Then in the **[!UICONTROL Start sending from]** field, set the contact date, in our case February 14th at 8:00 AM so that every recipient receives it on Valentine's Day.

   ![](assets/send-time_opt_valentine.png)

1. In the **[!UICONTROL Time zone of the contact date]** field, select at which time zone your delivery should be sent by default.

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. From the **[!UICONTROL Optimize the sending time per recipient]** drop-down menu, choose **[!UICONTROL Send at the recipient's time zone]**. Esto permite a los destinatarios recibir el correo electrónico del día de San Valentín el 14 de febrero, según su zona horaria.

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   Asegúrese de confirmar el envío por lo menos 24 horas antes. De lo contrario, según sus ubicaciones, algunos destinatarios podrían recibir la entrega antes del evento de día de San Valentín real.

   ![](assets/send-time_opt_valentine_4.png)

Independientemente de dónde se encuentren, todos los destinatarios recibirán el mensaje el 14 de febrero a las 8:00 AM, hora local.

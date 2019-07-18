---
title: Acerca de la programación de mensajes
seo-title: Acerca de la programación de mensajes
description: Acerca de la programación de mensajes
seo-description: Obtenga información sobre cómo programar sus mensajes.
page-status-flag: no activado nunca
uuid: 286 fceee -65 a 9-4 cb 9-b 205-9 ce 5 d 024675 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9 c 7 fd 670-bba 9-4 f 3 c -8 cb 1-87397 a 1 acd 27
context-tags: entrega, programación, atrás
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

**[!UICONTROL Schedule]** Las propiedades permiten definir las opciones de envío de sus correos electrónicos, SMS o notificaciones Push:

* **[!UICONTROL Messages to be sent once confirmed]**: los mensajes se envían tan pronto como se confirma el envío. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: los mensajes se enviarán en una fecha y hora posteriores. Specify the **contact date** in the **Start sending from** field.

   Puede preparar y confirmar el envío, pero los mensajes solo se enviarán comenzando la fecha y hora seleccionadas. Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   The **[!UICONTROL Time zone of the contact date]** drop-down list allows you to modify the time zone that will be taken into account for the sending time. For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field and if you select Brussels, Copenhagen, Madrid, Paris (GMT+1) in the **[!UICONTROL Time zone of the contact date]** drop-down list, all recipients will receive the message at 9:00 AM Paris time. Por lo tanto, un destinatario ubicado en Moscú (GMT +3) recibirá el mensaje a las 11:00 AM Hora de Moscú.

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. Esta opción está habilitada de forma predeterminada.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Al duplicar una entrega, se eliminan todos los ajustes de programación. A menos que programe una nueva fecha de contacto, la entrega duplicada se enviará en cuanto se confirma el envío.

**Temas relacionados**:

* [Optimización del tiempo de envío](../../sending/using/optimizing-the-sending-time.md)
* [Envío de mensajes en la zona horaria del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcular la fecha de envío](../../sending/using/computing-the-sending-date.md)


---
title: Acerca de la programación de mensajes
description: Aprenda a programar sus mensajes.
page-status-flag: nunca activado
uuid: 286fce-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: programar mensajes
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: entrega,programación,devolución
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de la programación de mensajes{#about-scheduling-messages}

>[!CAUTION]
>
>Siempre que realice cambios en la programación de un envío, debe volver a preparar el envío haciendo clic en el botón **Preparar** antes de hacer clic en **Confirmar**.

En el panel de mensajes, el **[!UICONTROL Schedule]** bloque le permite definir cuándo se enviarán los mensajes (correo electrónico, SMS o notificaciones push).

![](assets/delivery_dashboard.png)

Las **[!UICONTROL Schedule]** propiedades le permiten establecer opciones de envío para sus correos electrónicos, SMS o notificaciones push:

* **[!UICONTROL Messages to be sent once confirmed]**:: se envían en cuanto se confirma el envío. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**:: los mensajes se enviarán más adelante. Especifique la fecha **de** contacto en el campo **Comenzar a enviar desde** .

   Puede preparar y confirmar el envío, pero los mensajes solo se enviarán a partir de la fecha y hora seleccionadas. La preparación y confirmación del envío se presentan en las secciones [Preparación del envío](../../sending/using/preparing-the-send.md) y [Confirmación del envío](../../sending/using/confirming-the-send.md) .

   La **[!UICONTROL Time zone of the contact date]** lista desplegable le permite modificar el huso horario que se tendrá en cuenta para la hora de envío. Por ejemplo, si introduce 9:00 AM en el campo y selecciona Bruselas, Copenhague, Madrid, París (GMT+1) en la lista **[!UICONTROL Start sending from]** **[!UICONTROL Time zone of the contact date]** desplegable, todos los destinatarios recibirán el mensaje a las 9:00 AM, hora de París. Por lo tanto, un destinatario ubicado en Moscú (GMT+3) recibirá el mensaje a las 11:00 AM hora de Moscú.

   Si desea confirmar manualmente el envío, marque la **[!UICONTROL Request confirmation before sending messages]** opción. Esta opción está activada de forma predeterminada.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Al duplicar un envío, se eliminan todos los ajustes de programación. A menos que programe una nueva fecha de contacto, el envío duplicado se enviará en cuanto se confirme el envío.

**Temas relacionados**:

* [Optimización del tiempo de envío](../../sending/using/optimizing-the-sending-time.md)
* [Envío de mensajes en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Cálculo de la fecha de envío](../../sending/using/computing-the-sending-date.md)


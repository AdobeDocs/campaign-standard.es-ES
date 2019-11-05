---
title: Envío de mensajes en el huso horario del destinatario
description: Obtenga información sobre cómo enviar mensajes en el huso horario del destinatario.
page-status-flag: nunca activado
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: programar mensajes
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Envío de mensajes en el huso horario del destinatario{#sending-messages-at-the-recipient-s-time-zone}

Al administrar una campaña en la que la fecha y la hora son importantes, puede programar un envío que tenga en cuenta la hora local de cada destinatario: recibirán notificaciones por correo electrónico, SMS o push en el momento que programaste, en su propio huso horario.

>[!NOTE]
>
>Para utilizar esta funcionalidad, asegúrese de que todos los perfiles dirigidos por la entrega tengan una zona horaria especificada en la sección de sus propiedades **[!UICONTROL Address]** . Para obtener más información sobre el acceso a las propiedades de perfil, consulte esta [sección](../../audiences/using/editing-profiles.md).

Para enviar una entrega en el huso horario del destinatario, también puede utilizar la **[!UICONTROL Scheduler]** actividad en un flujo de trabajo. Para obtener más información, consulte [esta página](../../automating/using/scheduler.md).

En el siguiente ejemplo, queremos enviar un código promocional que sólo sea válido en San Valentín a todos los clientes de todo el mundo. Para disponer de tiempo suficiente para utilizarlo durante el día, todos los clientes deben recibir su mensaje el 14 de febrero a las 8:00 AM, según sus husos horarios.

1. En la **[!UICONTROL Marketing activities]** ficha, empiece a crear su entrega, en nuestro caso un correo electrónico. Para obtener más información sobre la creación de envíos, consulte esta [sección](../../channels/using/creating-an-email.md).
1. Después de diseñar el correo electrónico de San Valentín, haga clic en **[!UICONTROL Create]** para acceder al tablero de entrega. For more on email designing, refer to this [page](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. En el tablero de envío, seleccione el **[!UICONTROL Schedule]** bloque.

   ![](assets/send-time_opt_valentine_2.png)

1. Seleccione la **[!UICONTROL Messages to be sent automatically on the date]** opción especificada a continuación. Luego en el **[!UICONTROL Start sending from]** campo, establezca la fecha de contacto, en nuestro caso 14 de febrero a las 8:00 AM para que cada destinatario lo reciba en el Día de San Valentín.

   ![](assets/send-time_opt_valentine.png)

1. En el **[!UICONTROL Time zone of the contact date]** campo, seleccione la zona horaria en la que debe enviarse el envío de forma predeterminada.

   Si un perfil **[!UICONTROL Time zone]** se deja como **[!UICONTROL Default]**, los destinatarios recibirán la entrega en función del huso horario seleccionado aquí.

1. En el menú **[!UICONTROL Optimize the sending time per recipient]** desplegable, elija **[!UICONTROL Send at the recipient's time zone]**. Esto permite a los destinatarios recibir el correo electrónico del día de San Valentín el 14 de febrero, según su zona horaria.

   ![](assets/send-time_opt_valentine_3.png)

1. Después de confirmar la programación de la entrega, haga clic en el **[!UICONTROL Prepare]** botón y luego en **[!UICONTROL Confirm]** la entrega.

   Asegúrese de confirmar el envío con al menos 24 horas de anticipación. De lo contrario, según su ubicación, algunos destinatarios podrían recibir la entrega antes del evento del día de San Valentín.

   ![](assets/send-time_opt_valentine_4.png)

Independientemente de su ubicación, todos los destinatarios recibirán el mensaje el 14 de febrero a las 8:00 AM, hora local.

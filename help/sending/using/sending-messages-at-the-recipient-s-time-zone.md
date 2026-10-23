---
title: Envío de mensajes en el huso horario del destinatario
description: Aprenda a enviar mensajes en el huso horario del destinatario.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Proofs
role: User
level: Intermediate
exl-id: 48f222bd-9c2f-4eeb-a12b-bbfc62119024
TQID: 'https://experienceleague.adobe.com/0ZBuZihQqaowNG6y5gzkh5Vpz86e6pjmTRd5bNDPGxg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: 458b98fa-9d41-55f3-9c8e-3aeb5c95457a
    internal-label: Proofs
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 69%
---
# Envío de mensajes en el huso horario del destinatario{#sending-messages-at-the-recipient-s-time-zone}

Al administrar una campaña en la que la fecha y la hora son importantes, puede programar una entrega que tenga en cuenta la hora local de cada destinatario: recibirán notificaciones push, por correo electrónico o SMS en el momento que usted programe, en su propio huso horario.

>[!NOTE]
>
>Para utilizar esta funcionalidad, asegúrese de que todos los perfiles a los que se dirige su entrega tengan un huso horario especificado en la sección **[!UICONTROL Address]** de sus propiedades. Para obtener más información sobre el acceso a las propiedades del perfil, consulte esta [sección](../../audiences/using/editing-profiles.md).

Para enviar una entrega en el huso horario del destinatario, también puede utilizar la actividad **[!UICONTROL Scheduler]** en un flujo de trabajo. Para obtener más información, consulte [esta página](../../automating/using/scheduler.md).

En el siguiente ejemplo, queremos enviar un código promocional que solo sea válido en San Valentín a todos los clientes en todo el mundo. Para disponer de tiempo suficiente para utilizarlo durante el día, todos los clientes deben recibir su mensaje el 14 de febrero a las 8:00 a. m., según sus husos horarios.

1. En la pestaña **[!UICONTROL Marketing activities]**, inicie la creación de su envío, en nuestro caso un correo electrónico. Para obtener más información sobre la creación de envíos, consulte esta [sección](../../channels/using/creating-an-email.md).
1. Después de diseñar el correo electrónico de San Valentín, haga clic en **[!UICONTROL Create]** para acceder al panel de control de entregas. Para obtener más información sobre el diseño de correo electrónico, consulte esta [página](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. En el panel de control de entregas, seleccione el bloque **[!UICONTROL Schedule]**.

   ![](assets/send-time_opt_valentine_2.png)

1. Seleccione la opción **[!UICONTROL Messages to be sent automatically on the date]** especificada a continuación. Luego, en el campo **[!UICONTROL Start sending from]**, establezca la fecha de contacto, en nuestro caso el 14 de febrero a las 8:00 a.m. para que cada destinatario lo reciba en el día de San Valentín.

   ![](assets/send-time_opt_valentine.png)

1. En el campo **[!UICONTROL Time zone of the contact date]**, seleccione el huso horario en el que debe enviarse el envío de forma predeterminada.

   Si el **[!UICONTROL Time zone]** de un perfil se queda como **[!UICONTROL Default]**, los destinatarios recibirán el envío según el huso horario elegido aquí.

1. En el menú desplegable **[!UICONTROL Optimize the sending time per recipient]**, elija **[!UICONTROL Send at the recipient's time zone]**. Esto permite a los destinatarios recibir el correo electrónico del día de San Valentín el 14 de febrero, dependiendo de su huso horario.

   ![](assets/send-time_opt_valentine_3.png)

1. Después de confirmar la programación de su envío, haga clic en el botón **[!UICONTROL Prepare]** y luego **[!UICONTROL Confirm]** su envío.

   Asegúrese de confirmar el envío con al menos 24 horas de anticipación. De lo contrario, según su ubicación, algunos destinatarios podrían recibir la entrega antes del evento del día de San Valentín.

   ![](assets/send-time_opt_valentine_4.png)

Independientemente de dónde se encuentren, todos los destinatarios recibirán el mensaje el 14 de febrero a las 8:00 a. m., en su hora local.

---
solution: Campaign Standard
product: campaign
title: Optimización del tiempo de envío
description: Aprenda a configurar el tiempo de envío y mejorar la velocidad de apertura de los mensajes.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Optimización del tiempo de envío
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 97%

---


# Optimización del tiempo de envío{#optimizing-the-sending-time}

Para mejorar la velocidad de apertura de los mensajes, puede definir manualmente una hora de envío por destinatario. Cada perfil recibe el mensaje en la fecha y hora especificadas, siempre que sea posible.

La definición de una hora de envío se puede realizar en el nivel de envío o mediante un flujo de trabajo.

En el caso de los mensajes de correo electrónico, según la carga del servidor y la cantidad de reintentos, se realiza el mejor esfuerzo para enviar el mensaje en la fecha y hora programadas para cada destinatario.

* Los reintentos dependen del proveedor de Internet y de su reputación. Es posible que el mensaje no se acepte en el primer intento y que se realicen varios reintentos. Consulte [Lista de los parámetros de canal de correo electrónico](../../administration/using/configuring-email-channel.md).
* Los retrasos en la recepción del correo electrónico pueden deberse a un ancho de banda insuficiente.

Puede comprobar cuándo se ha enviado el mensaje a cada destinatario en los [registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs).

Hay varias opciones disponibles:

* **[!UICONTROL No optimization]**: los mensajes se envían según la hora del usuario.

   Por ejemplo, si su zona horaria es GMT+1 y especifica 9:00 AM en el campo **[!UICONTROL Start sending from]**, un destinatario ubicado en el huso horario GMT+3 recibe el mensaje a las 11:00 AM, hora local para ese destinatario.

* **[!UICONTROL Send at the recipient's time zone]**: todos los destinatarios reciben el mensaje teniendo en cuenta su huso horario.

   Por ejemplo, si escribe 9:00 AM en el campo **[!UICONTROL Start sending from]**, un destinatario ubicado en el huso horario GMT+3 recibe el mensaje a las 9:00 AM, hora local para ese destinatario.

   Consulte [Envío de mensajes en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: cada destinatario recibe el mensaje en la fecha y hora configuradas por la fórmula especificada.

   Consulte [Cálculo de la fecha de envío](../../sending/using/computing-the-sending-date.md).


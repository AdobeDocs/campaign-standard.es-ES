---
title: Optimización del tiempo de envío
description: Aprenda a configurar el tiempo de envío y mejorar la velocidad de apertura de los mensajes.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 74%

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

  Por ejemplo, si su zona horaria es GMT+1 y especifica 9:00 AM en el campo **[!UICONTROL Start sending from]**, un destinatario ubicado en el huso horario GMT+3 recibirá el mensaje a las 11:00 AM, hora local para ese destinatario.

* **[!UICONTROL Send at the recipient's time zone]**: todos los destinatarios reciben el mensaje teniendo en cuenta su huso horario.

  Por ejemplo, si escribe 9:00 AM en el campo **[!UICONTROL Start sending from]**, un destinatario ubicado en el huso horario GMT+3 recibirá el mensaje a las 9:00 AM, hora local para ese destinatario.

  Consulte [Envío de mensajes en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: cada destinatario recibe el mensaje en la fecha y hora configuradas por la fórmula especificada.

  Consulte [Cálculo de la fecha de envío](../../sending/using/computing-the-sending-date.md).

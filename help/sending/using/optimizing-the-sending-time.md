---
title: Optimización del tiempo de envío
description: Obtenga información sobre cómo configurar el tiempo de envío y mejorar la velocidad de apertura de los mensajes.
page-status-flag: nunca activado
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: programar mensajes
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Optimización del tiempo de envío{#optimizing-the-sending-time}

Para mejorar la velocidad de apertura de los mensajes, puede definir manualmente una hora de envío por destinatario. Cada perfil recibirá el mensaje en la fecha y hora especificadas, siempre que sea posible.

La definición de una hora de envío se puede realizar en el nivel de entrega o mediante un flujo de trabajo.

En el caso de los mensajes de correo electrónico, según la carga del servidor y la cantidad de reintentos, se hará el mejor esfuerzo para enviar el mensaje en la fecha y hora programadas para cada destinatario.

* Los reintentos dependen del proveedor de Internet y de su reputación. Es posible que el mensaje no se acepte en el primer intento y que se realicen varios reintentos. Consulte [Lista de parámetros](../../administration/using/configuring-email-channel.md)de canal de correo electrónico.
* Los retrasos en la recepción del correo electrónico pueden deberse a un ancho de banda insuficiente.

Puede ver cuándo se envió el mensaje a cada destinatario en los registros [de](../../sending/using/monitoring-a-delivery.md#sending-logs)envío.

Hay varias opciones disponibles:

* **[!UICONTROL No optimization]**:: Los mensajes se envían a la hora del usuario.

   Por ejemplo, si su zona horaria es GMT+1 y especifica 9:00 AM en el **[!UICONTROL Start sending from]** campo, un destinatario ubicado en la zona horaria GMT+3 recibirá el mensaje a las 11:00 AM, hora local, para ese destinatario.

* **[!UICONTROL Send at the recipient's time zone]**:: Todos los destinatarios recibirán el mensaje teniendo en cuenta su huso horario.

   Por ejemplo, si escribe 9:00 AM en el **[!UICONTROL Start sending from]** campo, un destinatario ubicado en la zona horaria GMT+3 recibirá el mensaje a las 9:00 AM, hora local, para ese destinatario.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**:: Cada destinatario recibirá el mensaje en la fecha y hora configuradas por la fórmula especificada.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).


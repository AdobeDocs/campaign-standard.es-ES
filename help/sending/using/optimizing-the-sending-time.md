---
title: Optimización del tiempo de envío
seo-title: Optimización del tiempo de envío
description: Optimización del tiempo de envío
seo-description: Descubra cómo configurar el tiempo de envío y mejorar la velocidad abierta de los mensajes.
page-status-flag: no activado nunca
uuid: c 2 c 13934-9819-4 e 18-b 5 c 7-60915 c 907 f 37
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355 f 6-9003-41 b 9-9981-ea 787419 fbf 5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

Para mejorar la velocidad abierta de los mensajes, puede definir manualmente un tiempo de envío por destinatario. Cada perfil recibirá el mensaje en la fecha y hora especificadas, siempre que sea posible.

La definición de un tiempo de envío puede realizarse en el nivel de entrega o mediante un flujo de trabajo.

Para los correos electrónicos, según la carga del servidor y la cantidad de reintentos, se realizará un esfuerzo óptimo para enviar el mensaje en la fecha y la hora programadas para cada destinatario.

* Los reintentos dependen del proveedor de Internet y de su reputación. Es posible que el mensaje no se acepte en el primer intento y que se realicen varios reintentos. See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* Los retrasos en la recepción del correo electrónico pueden producirse debido a un ancho de banda insuficiente.

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Hay varias opciones disponibles:

* **[!UICONTROL No optimization]**: Los mensajes se envían a la hora del usuario.

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**: Todos los destinatarios recibirán el mensaje teniendo en cuenta su zona horaria.

   For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 9:00 AM local time for that recipient.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Cada destinatario recibirá el mensaje en la fecha y la hora configuradas por la fórmula especificada.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).


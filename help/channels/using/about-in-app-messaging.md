---
title: Acerca de la mensajería en la aplicación
description: Mostrar mensaje o alerta dentro de la aplicación móvil con mensajería en la aplicación.
page-status-flag: nunca activado
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: mensajería en la aplicación
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: entrega,activadores,devolución
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de la mensajería en la aplicación{#about-in-app-messaging}

La mensajería en la aplicación es un canal de mensajería que permite mostrar un mensaje cuando el usuario está activo en la aplicación móvil. Este tipo de mensaje es gratuito para las notificaciones push que se envían al centro de notificaciones del teléfono de los usuarios. For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

Este canal requiere que las aplicaciones móviles se integren con el SDK de la plataforma Adobe Experience. Estas aplicaciones deben activarse en Adobe Experience Platform Launch antes de estar disponibles en Adobe Campaign para envíos en la aplicación.

![](assets/launch_campaign.png)

Para empezar a enviar mensajes en la aplicación en aplicaciones móviles que utilicen el SDK de la plataforma de experiencia, debe cumplir los siguientes requisitos previos:

1. En Adobe Campaign, asegúrese de tener acceso al **[!UICONTROL In-App]** canal. Si no puede acceder a estos canales, póngase en contacto con el equipo de cuentas.

1. Para aprovechar los casos de uso móvil en Adobe Campaign Standard con una aplicación de SDK de Experience Cloud, se debe crear una aplicación móvil en Adobe Experience Platform Launch y configurarla en Adobe Campaign Standard. Para obtener la guía paso a paso, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. Una vez configurado, ahora puede preparar el mensaje en la aplicación. Para obtener más información, consulte [esta página](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. A continuación, puede decidir enviar un mensaje [](../../channels/using/customizing-an-in-app-message.md) en la aplicación o [personalizar un tipo](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)de mensaje de notificación local.

1. La entrega ya está lista para enviarse. Para obtener más información, consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenido relacionado:**

* [Informe en la aplicación](../../reporting/using/in-app-report.md)
* [Preguntas más frecuentes sobre push y en la aplicación](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Casos de uso móvil admitidos en Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)

---
title: Acerca de la mensajería en la aplicación
seo-title: Acerca de la mensajería en la aplicación
description: Acerca de la mensajería en la aplicación
seo-description: Mostrar mensaje o alerta dentro de la aplicación móvil con mensajería en la aplicación.
page-status-flag: no activado nunca
uuid: 6784 cdfc -6 db 9-41 dd -9 fbb -2 e 756 a 5 bcb 5 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajería en la aplicación
discoiquuid: a 4168 cfb -22 bf -4 ab 3-b 9 d 8-6 e 76 e 1 bdc 055
context-tags: entrega, activadores, atrás
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 90b478d1d58b67e763b8b6685c12530a5b5ee9c3

---


# About In-App messaging{#about-in-app-messaging}

La mensajería en la aplicación es un canal de mensajes que permite mostrar un mensaje cuando el usuario está activo dentro de la aplicación móvil. Este tipo de mensaje es gratuito para las notificaciones push que se envían al centro de notificaciones del teléfono de los usuarios. For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

Este canal requiere que las aplicaciones móviles se integren con el SDK de Adobe Experience Platform. Estas aplicaciones deben activarse en Adobe Experience Platform Launch antes de estar disponibles en Adobe Campaign para los envíos desde la propia aplicación.

![](assets/launch_campaign.png)

Para empezar a enviar mensajes en la aplicación en aplicaciones móviles aprovechando el SDK de Experience Platform, debe cumplir los requisitos previos siguientes:

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. Si no puede acceder a estos canales, póngase en contacto con el equipo de su cuenta.
1. En Launch Platform Launch, cree la aplicación móvil creando una propiedad móvil e instrumentando su aplicación móvil con el SDK de la plataforma de Experience Platform.

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**Contenido relacionado:**

* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md)
* [Personalización de un tipo de mensaje de notificación local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [Envío de un mensaje en la aplicación dentro de un flujo de trabajo](../../automating/using/in-app-delivery.md)
* [Preguntas más frecuentes sobre Push y en la aplicación](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
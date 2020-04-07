---
title: Acerca de las notificaciones push
description: Descubrir las principales características del canal de notificación push en Adobe Campaign.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

---


# Acerca de las notificaciones push{#about-push-notifications}

>[!CAUTION]
>
>La implementación de notificaciones Push debe ser realizada por usuarios expertos. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. La notificación Push es una función opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.

Adobe Campaign le permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android.

Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK de la plataforma de experiencia. Para obtener más información sobre esto, consulte [Configuración de una aplicación móvil mediante los SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)de la plataforma Adobe Experience.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Este recurso debe ampliarse para recopilar los datos que se van a enviar desde el dispositivo móvil al Adobe Campaign. Para ello, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conocer los pasos detallados.

Hay dos tipos de notificaciones push disponibles en Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** las notificaciones de tipo le permiten enviar mensajes estándar basados en texto con contenido adicional (sonido, distintivo, vínculo profundo, etc.) que puede definir en la **[!UICONTROL Advanced options]** sección.

   Estos tipos de notificación le permiten agregar un título y un mensaje en los que puede utilizar campos de personalización. Para poder personalizar el mensaje, asegúrese de seleccionar la **[!UICONTROL Send push on profiles]** plantilla.

* **[!UICONTROL Silent push]** las notificaciones de tipo se utilizan para notificar la aplicación de forma silenciosa sin ningún mensaje ni contenido para el usuario final. Un caso de uso típico para este tipo de mensaje sería hacer que la aplicación sepa que hay contenido disponible en el servidor que se va a descargar.

Se pueden configurar algunas configuraciones específicas para definir el comportamiento de las notificaciones. Para obtener más información, consulte [esta sección](../../channels/using/customizing-a-push-notification.md).

Como usuario experto, para definir estas configuraciones específicas, consulte las [notas técnicas](https://helpx.adobe.com/es/campaign/kb/acs-article-list.html)de la aplicación móvil.

>[!NOTE]
>
>Las leyes relativas a la privacidad difieren según el país. Algunos países requieren que se informe a los usuarios de los tipos de datos recopilados por las aplicaciones móviles. Por favor, revisa las leyes relativas a las aplicaciones móviles en tu país. Asegúrese de que las notificaciones push enviadas a aplicaciones móviles cumplen los requisitos y condiciones especificados por Apple (servicio de notificaciones push de Apple) y Google (mensajería de Google Cloud o mensajería de Firebase Cloud).

**Contenido relacionado:**

* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creación de una notificación push multilingüe](../../channels/using/creating-a-multilingual-push-notification.md)
* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Guía de Campaign Standard Mobile](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html)

## Requisitos previos {#prerequisites}

>[!NOTE]
>Para aprovechar la función de notificación push desde la Campaña, debe proporcionar un certificado push válido en formato .pem sin contraseñas.
Si tiene un certificado p12 válido, puede convertirlo fácilmente en un archivo .pem con recursos en línea.

Antes de enviar las notificaciones push, debe:

1. En Adobe Campaign, asegúrese de tener acceso al **[!UICONTROL Push notification]** canal. Si no puede acceder a estos canales, póngase en contacto con el equipo de su cuenta.

1. Compruebe que el usuario tiene los permisos necesarios en Adobe Campaign Standard y Experience Platform Launch.

1. En Experience Platform Launch, cree una propiedad móvil. Para obtener más información, consulte [Configuración de una propiedad](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)móvil.

1. En Experience Platform Launch, instale la **[!UICONTROL Adobe Campaign Standard]** extensión.

1. En Adobe Campaign Standard, configure la propiedad móvil que ha creado en Experience Platform Launch. Para obtener más información, consulte [Configuración de la aplicación Experience Platform Launch en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Añada la configuración específica del canal a la configuración de la aplicación móvil. Para obtener más información, consulte Configuración de aplicaciones específicas para [Canales en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

1. Para admitir implementaciones de casos de uso móvil, consulte las instrucciones detalladas sobre extensiones, reglas de Experience Platform Launch e implementación de SDK en casos de uso de [Mobile admitidos en Adobe Campaign Standard mediante los SDK](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)de la plataforma Adobe Experience.
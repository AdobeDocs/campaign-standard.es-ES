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
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 6%

---


# Acerca de las notificaciones push{#about-push-notifications}

>[!CAUTION]
>
>La implementación de notificaciones Push debe ser realizada por usuarios expertos. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. La notificación Push es una función opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.

Adobe Campaign le permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android.

Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK de Experience Platform. Para obtener más información sobre esto, consulte [Configuración de una aplicación móvil mediante SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)de Adobe Experience Platform.

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

1. Añada la configuración específica del canal a la configuración de la aplicación móvil. Para obtener más información, consulte Configuración de aplicaciones específicas para [Canales en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Para admitir implementaciones de casos de uso móvil, consulte las instrucciones detalladas sobre extensiones, reglas de Experience Platform Launch e implementación de SDK en casos de uso de [Mobile admitidos en Adobe Campaign Standard mediante los SDK](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)de Adobe Experience Platform.

## Preguntas más frecuentes sobre notificaciones Push {#push-faq}

### ¿Cuáles serían algunas recomendaciones de recursos útiles para obtener más información sobre el canal push? {#resource-push}

Consulte los siguientes recursos:

* [Tutoriales de vídeo](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentación del producto](../../channels/using/about-push-notifications.md)
* Configurar mediante la [documentación del SDK de AEP](../../administration/using/configuring-a-mobile-application.md)
* [Página de comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### ¿Qué tengo que hacer para adquirir un token push en Campaña? {#push-token-acquisition}

Asegúrese de que el equipo de aprovisionamiento ha completado el aprovisionamiento de canal push en Adobe Campaign Standard. Implemente la API setPushIdentifier desde el SDK. Para obtener más información, consulte [esta página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### Una vez que tengo el token push y el ECID en Campaña, ¿qué más necesito para enviar una notificación Push? {#sending-push}

Los clientes deben proporcionar un certificado Push válido en formato .pem para poder enviar una notificación Push. No necesita una contraseña para este certificado.

### ¿Qué sucede si tengo un certificado .p12 en lugar del certificado .pem? {#certificates}

Puede convertir un certificado .p12 en un certificado .pem ejecutando el comando a continuación en terminal. También hay varios recursos en línea disponibles para las instrucciones de conversión.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### ¿Cómo sé si la carga del certificado se ha realizado correctamente? {#certificate-upload}

Verá el siguiente mensaje.

![](assets/faq_2.png)

### ¿Puedo cargar los certificados de producción y de Simulador para pruebas al mismo tiempo para la aplicación iOS (N/D para Android)? {#prod-sandbox-certificate}

No, las aplicaciones funcionarán en el simulador de pruebas o en el modo de producción y no se podrán cambiar a la otra (es decir, el simulador de pruebas a la aplicación de producción) una vez configuradas. Le recomendamos que pruebe la aplicación en el modo de simulación de pruebas primero y, a continuación, en la transición al modo de producción.

Para cambiar al modo de producción, tendrá que crear otra aplicación. Asegúrese también de no marcar la casilla de verificación del simulador para pruebas y de cargar un certificado de producción.

### ¿Puedo cargar las credenciales de iOS y Android al mismo tiempo? {#ios-android-credentials}

Sí, Campaña admite ambas plataformas al mismo tiempo y permite cargar las credenciales para ambas.

### He cargado correctamente los certificados Push, pero no se envían mensajes Push. {#push-certificates-upload}

Asegúrese de que los certificados push son válidos probándolos [aquí](https://pushtry.com/).

### Puedo enviar notificaciones push correctamente desde pushtry.com pero no a través de la Campaña. {#push-not-sending}

Asegúrese de seguir las instrucciones de carga útil Push que se proporcionan [aquí](../../administration/using/push-payload.md).

Tenga en cuenta que para Android, la Campaña solo admite la carga útil de datos, no la carga útil de notificación

### He configurado una aplicación en la sección Administración de Adobe Campaign Standard, pero la aplicación móvil no está disponible en las propiedades de Envío. {#mobile-app-unavailable}

Una aplicación debe tener un certificado Push válido cargado también antes de que esté disponible en las propiedades de envío.

### He probado todas las instrucciones de esta página y sin embargo no puedo enviar push desde la Campaña. {#push-troubleshoot}

Abra un ticket de atención al cliente.

### Las notificaciones push se envían desde la Campaña, pero el archivo multimedia no se muestra.{#media-file-unavailable}

Los desarrolladores de aplicaciones móviles deben gestionar la compatibilidad con los archivos multimedia en la aplicación. A veces, el ancho de banda de la red también puede impedir que se procese un archivo multimedia. Consulte esta [página](../../administration/using/image-push-notification.md) para obtener más información sobre punteros.

### ¿Qué tengo que hacer para habilitar el sistema de informes push en la Campaña? {#push-reporting-enable}

Siga estos pasos:

* Configure un postback de seguimiento push. Instructions can be found [here](../../administration/using/configuring-a-mobile-application.md).
* Implementar la API trackAction desde Mobile Core. Refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) for more information.

Encontrará instrucciones más detalladas en esta [página](../../administration/using/push-tracking.md).

### ¿Qué informes están disponibles para el canal push? {#push-report-available}

Hay disponible un informe listo para usar en Adobe Campaign para el canal push. Refer to this [documentation](../../reporting/using/push-notification-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#push-notification-delivery) para comprender cómo se calculan las métricas push.

### ¿Se admiten vínculos profundos en los mensajes push y en la aplicación? {#deeplink-push}

Sí, los vínculos profundos son compatibles con los mensajes push. Los vínculos profundos deben incluir:

* idioma que indica que el seguimiento de envíos debe deshabilitarse para que funcionen los vínculos profundos.
* Appsflyer con Branch como socios que pueden realizar el seguimiento de vínculos profundos. Para obtener más información sobre la integración de ramas y Adobes Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
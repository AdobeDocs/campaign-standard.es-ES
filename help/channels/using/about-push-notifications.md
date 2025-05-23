---
title: Acerca de las notificaciones push
description: Descubra las principales características del canal de notificación push en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 39%

---

# Acerca de las notificaciones push{#about-push-notifications}

>[!CAUTION]
>
>La implementación de notificaciones push la deben realizar usuarios expertos. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. Las notificaciones push son una función opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.

Adobe Campaign permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android.

Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK de Experience Platform. Para obtener más información sobre esto, consulte [Configuración de una aplicación móvil mediante el uso de SDK de Adobe Experience Platform](../../administration/using/configuring-a-mobile-application.md).

En Adobe Campaign, los datos de atributos de perfil móviles enviados desde dispositivos móviles se almacenan en el recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que le permite definir los datos que desea recopilar de los suscriptores de las aplicaciones.

Este recurso debe ampliarse para recopilar los datos que se van a enviar desde el dispositivo móvil a Adobe Campaign. Para ello, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conocer los pasos detallados.

En Adobe Campaign, hay disponibles dos tipos de notificaciones push:

* Las notificaciones del tipo **[!UICONTROL Alert/Message/Badge]** le permiten enviar mensajes estándares basados en texto con contenido adicional (sonidos, distintivos, vínculos profundos, etc.) que puede definir en la sección **[!UICONTROL Advanced options]**.

  Estos tipos de notificación le permiten añadir un título y un mensaje en los que puede utilizar campos de personalización. Para poder personalizar el mensaje, asegúrese de seleccionar la plantilla **[!UICONTROL Send push on profiles]**.

* Las notificaciones del tipo **[!UICONTROL Silent push]** se utilizan para notificar a la aplicación de forma silenciosa sin ningún mensaje ni contenido para el usuario final. Un caso de uso típico de este tipo de mensaje sería hacer que la aplicación sepa que hay contenido disponible en el servidor que se va a descargar.

Se pueden configurar algunos ajustes específicos para definir el comportamiento de las notificaciones. Para obtener más información, consulte [esta sección](../../channels/using/customizing-a-push-notification.md).

>[!NOTE]
>
>Las leyes relativas a la privacidad difieren según el país. Algunos países obligan a que se informe a los usuarios de los tipos de datos que recopilan las aplicaciones móviles. Consulte las leyes de su país relativas a aplicaciones móviles. Asegúrese de que las notificaciones push enviadas aplicaciones móviles cumplen los requisitos previos y las condiciones especificadas por Apple (Apple Push Notification Service) y Google (Google Cloud Messaging o Firebase Cloud Messaging).

**Contenido relacionado:**

* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creación de una notificación push multilingüe](../../channels/using/creating-a-multilingual-push-notification.md)
* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Guía de Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Requisitos previos {#prerequisites}

>[!NOTE]
>Para aprovechar la función de notificación push de Campaign, debe proporcionar un certificado push válido en formato .pem sin contraseñas.
>
>Si tiene un certificado p12 válido, puede convertirlo fácilmente a un archivo .pem con recursos en línea.

Antes de enviar las notificaciones push, debe hacer lo siguiente:

1. En Adobe Campaign, asegúrese de que puede acceder al canal **[!UICONTROL Push notification]**. Si no puede acceder a estos canales, póngase en contacto con el equipo de su cuenta.

1. Compruebe que el usuario tiene los permisos necesarios en Adobe Campaign Standard y en Adobe Experience Platform.

1. En la IU de recopilación de datos, cree una propiedad móvil. Para obtener más información, consulte [Configuración de una propiedad móvil](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. En la IU de recopilación de datos , instale la extensión **[!UICONTROL Adobe Campaign Standard]**.

1. En Adobe Campaign Standard, configure la propiedad móvil que ha creado en la IU de recopilación de datos. Para obtener más información, consulte [Configuración de la aplicación de etiquetas en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Añada la configuración específica del canal a la configuración de la aplicación móvil. Para obtener más información, consulte [Configuración de aplicaciones específicas del canal en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Para admitir implementaciones de casos de uso móvil, consulte las instrucciones detalladas sobre extensiones, reglas de etiquetas e implementación del SDK en [Casos de uso móvil admitidos en Adobe Campaign Standard mediante el uso de los SDK para Adobe Experience Platform](../../administration/using/configuring-rules-launch.md).

## Preguntas frecuentes sobre notificaciones push {#push-faq}

### ¿Cuáles serían algunas recomendaciones de recursos útiles para obtener más información sobre el canal push? {#resource-push}

Consulte los siguientes recursos:

* [Tutorials de vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html?lang=es)
* [Documentación del producto](../../channels/using/about-push-notifications.md)
* Configurar mediante el SDK de AEP [documentación](../../administration/using/configuring-a-mobile-application.md)
* [Página de la comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=es)

### ¿Qué tengo que hacer para adquirir un token push en Campaign? {#push-token-acquisition}

Asegúrese de que el equipo de aprovisionamiento haya completado el aprovisionamiento del canal push en Adobe Campaign Standard. Implemente la API setPushIdentifier desde el SDK. Para obtener más información, consulte esta [página](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging).

### Una vez que tenga el token push y el ECID en Campaign, ¿qué más necesito para enviar una notificación push? {#sending-push}

Los clientes deben proporcionar un certificado Push válido en formato .pem para enviar una notificación Push. No necesita una contraseña para este certificado.

### ¿Qué sucede si tengo un certificado .p12 en lugar del .pem? {#certificates}

Puede convertir un certificado .p12 en un certificado .pem ejecutando el siguiente comando en terminal. También hay varios recursos en línea disponibles para las instrucciones de conversión.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### ¿Cómo sé si la carga del certificado se ha realizado correctamente? {#certificate-upload}

Verá el siguiente mensaje.

![](assets/faq_2.png)

### ¿Puedo cargar certificados de producción y de zona protegida al mismo tiempo para la aplicación de iOS (N/D para Android)? {#prod-sandbox-certificate}

No, las aplicaciones funcionarán en modo de simulación de pruebas o de producción y no se podrán cambiar a la otra (de simulación de pruebas a aplicación de producción) una vez configuradas. Le recomendamos que pruebe la aplicación en modo de entorno limitado primero y luego realice la transición al modo de producción.

Para cambiar al modo de producción, debe crear otra aplicación. Asegúrese también de no marcar la casilla de verificación de la zona protegida y cargar un certificado de producción.

### ¿Puedo cargar credenciales de iOS y de Android al mismo tiempo? {#ios-android-credentials}

Sí, Campaign admite ambas plataformas al mismo tiempo y le permite cargar credenciales para ambas plataformas.

### He cargado correctamente certificados push, pero no se envían mensajes push. {#push-certificates-upload}

Asegúrese de que los certificados de inserción sean válidos probándolos [aquí](https://pushtry.com/).

### Puedo enviar notificaciones push correctamente desde pushtry.com, pero no a través de Campaign. {#push-not-sending}

Asegúrese de seguir las instrucciones de carga push proporcionadas [aquí](../../administration/using/push-payload.md).

Tenga en cuenta que para Android, Campaign solo admite la carga útil de datos, no de notificaciones

### He configurado una aplicación en la sección Administración de Adobe Campaign Standard, pero la aplicación móvil no está disponible en las propiedades de entrega. {#mobile-app-unavailable}

Una aplicación también debe tener un certificado push válido cargado antes de que pueda estar disponible en las propiedades de entrega.

### He probado todas las instrucciones de esta página y, sin embargo, no puedo enviar notificaciones push desde Campaign. {#push-troubleshoot}

Abra un ticket de atención al cliente.

### Las notificaciones push se envían desde Campaign, pero el archivo de medios no se muestra.{#media-file-unavailable}

Los desarrolladores de aplicaciones móviles deben gestionar la compatibilidad con archivos multimedia en la aplicación. A veces, el ancho de banda de la red también puede impedir que se procese un archivo multimedia. Consulte esta [página](../../administration/using/image-push-notification.md) para obtener punteros adicionales.

### ¿Qué tengo que hacer para habilitar la creación de informes push en Campaign? {#push-reporting-enable}

Siga estos pasos:

* Configure un postback de seguimiento push. Encontrará instrucciones [aquí](../../administration/using/configuring-a-mobile-application.md).
* Implemente la API trackAction desde Mobile Core. Consulte esta [página](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/) para obtener más información.

Encontrará instrucciones más detalladas en esta [página](../../administration/using/push-tracking.md).

### ¿Qué informes están disponibles para el canal push? {#push-report-available}

Hay disponible un informe listo para usar en el canal push de Adobe Campaign. Consulte esta [documentación](../../reporting/using/push-notification-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#push-notification-delivery) para comprender cómo se calcula cada métrica push.

### ¿Se admiten los vínculos profundos en los mensajes push y en la aplicación? {#deeplink-push}

Sí, los vínculos profundos son compatibles con los mensajes push. Los vínculos profundos deben incluir:

* Idioma que indica que es necesario deshabilitar el seguimiento de envíos para que funcionen los vínculos profundos.
* Folleto de aplicaciones con Branch como socios que pueden realizar el seguimiento de vínculos profundos. Para obtener más información sobre la integración de ramas y Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

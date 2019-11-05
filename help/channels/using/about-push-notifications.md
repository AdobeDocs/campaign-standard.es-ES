---
title: Acerca de las notificaciones push
description: Descubra las principales características del canal de notificaciones push en Adobe Campaign.
page-status-flag: nunca activado
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de las notificaciones push{#about-push-notifications}

>[!CAUTION]
>
>La implementación de notificaciones Push debe ser realizada por usuarios expertos. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. La notificación Push es una función opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.

Adobe Campaign permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android.

Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK V4 de Experience Cloud Mobile o del SDK de la plataforma de experiencia. Para obtener más información sobre esto, consulte [Configuración de una aplicación móvil mediante SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) y [Configuración de una aplicación móvil mediante SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)de la plataforma Adobe Experience.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Este recurso debe ampliarse para recopilar los datos que se van a enviar desde el dispositivo móvil a Adobe Campaign. Para ello, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conocer los pasos detallados.

Adobe Campaign dispone de dos tipos de notificaciones push:

* **[!UICONTROL Alert/Message/Badge]** las notificaciones de tipo le permiten enviar mensajes estándar basados en texto con contenido adicional (sonido, distintivo, vínculo profundo, etc.) que puede definir en la **[!UICONTROL Advanced options]** sección.

   Estos tipos de notificación le permiten agregar un título y un mensaje en los que puede utilizar campos de personalización. Para poder personalizar el mensaje, asegúrese de seleccionar la **[!UICONTROL Send push on profiles]** plantilla.

* **[!UICONTROL Silent push]** las notificaciones de tipo se utilizan para notificar la aplicación de forma silenciosa sin ningún mensaje ni contenido para el usuario final. Un caso de uso típico para este tipo de mensaje sería hacer que la aplicación sepa que hay contenido disponible en el servidor que se va a descargar.

Se pueden configurar algunas configuraciones específicas para definir el comportamiento de las notificaciones. Para obtener más información, consulte [esta sección](../../channels/using/customizing-a-push-notification.md).

Como usuario experto, para definir estas configuraciones específicas, consulte las [notas técnicas](https://helpx.adobe.com/campaign/kb/acs-article-list.html)de la aplicación móvil.

>[!NOTE]
>
>Las leyes relativas a la privacidad difieren según el país. Algunos países requieren que se informe a los usuarios de los tipos de datos recopilados por las aplicaciones móviles. Por favor, revisa las leyes relativas a las aplicaciones móviles en tu país. Asegúrese de que las notificaciones push enviadas a aplicaciones móviles cumplen los requisitos y condiciones especificados por Apple (servicio de notificaciones push de Apple) y Google (mensajería de Google Cloud o mensajería de Firebase Cloud).

**Contenido relacionado:**

* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creación de una notificación push multilingüe](../../channels/using/creating-a-multilingual-push-notification.md)
* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Preguntas más frecuentes sobre push y en la aplicación](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Requisitos previos {#prerequisites}

>[!NOTE]
>Para aprovechar la función de notificación push de Campaign, debe proporcionar un certificado push válido en formato .pem sin contraseñas.
Si tiene un certificado p12 válido, puede convertirlo fácilmente en un archivo .pem con recursos en línea.

En primer lugar, para poder empezar a enviar notificaciones push, debe configurar la aplicación móvil con SDK V4. También puede configurar la aplicación móvil con los SDK de la plataforma de experiencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Antes de enviar las notificaciones push, debe:

1. Asegúrese de tener acceso al canal en Adobe Campaign **[!UICONTROL Mobile app]** .
1. Configure la aplicación móvil en:

   * Espacio de trabajo de Adobe Campaign
   * Interfaz de Adobe Mobile Services

1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado de la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Experience Cloud Mobile en la aplicación móvil.

1. Defina los datos que desea recopilar de los suscriptores de la aplicación. Los suscriptores de la aplicación móvil que tienen un perfil en la base de datos de Adobe Campaign se concilian según los criterios definidos.

Después de configurar la aplicación móvil, ahora puede empezar a preparar y enviar los mensajes en la aplicación. Para obtener más información sobre esto, consulte [Preparación y envío de una notificación](../../channels/using/preparing-and-sending-a-push-notification.md)push.

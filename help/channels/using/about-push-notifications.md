---
title: Acerca de las notificaciones Push
seo-title: Acerca de las notificaciones Push
description: Acerca de las notificaciones Push
seo-description: Descubrir las principales especificidades del canal de notificaciones Push en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 961 aaeb 5-6948-4 fd 2-b 8 d 7-de 4510 c 10566
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: notificaciones push
discoiquuid: 23 b 4212 e-e 878-4922-be 20-50 fb 7 fa 88 ae 8
context-tags: Mobileapp, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>La implementación de notificaciones Push debe realizarla usuarios expertos. Si necesita recibir ayuda, póngase en contacto con su ejecutivo de cuentas de Adobe o con el socio de servicios profesionales. La notificación Push es una función opcional. Verifique su contrato de licencia y comuníquese con el ejecutivo de cuentas para activarlo.

Adobe Campaign permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android.

Estos mensajes se reciben en aplicaciones móviles que se configuren en Adobe Campaign, aprovechando el SDK Mobile Cloud Mobile SDK V 4 o Experience Platform SDK. For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Este recurso debe ampliarse para recopilar datos que se pretenden enviar desde el dispositivo móvil a Adobe Campaign. To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Hay dos tipos de notificaciones Push disponibles en Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** las notificaciones de tipo le permiten enviar mensajes estándar basados en texto con contenido adicional (sonido, distintivo, vínculo profundo, etc.) that you can define in the **[!UICONTROL Advanced options]** section.

   Estos tipos de notificación le permiten agregar un título y un mensaje en el que puede utilizar campos de personalización. To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** las notificaciones de tipo se utilizan para notificar de manera silenciosa a la aplicación sin ningún mensaje ni contenido para el usuario final. Un caso de uso típico para este tipo de mensaje sería hacer que la aplicación tenga en cuenta que hay contenido disponible en el servidor para descargar.

Algunas configuraciones específicas pueden configurarse para definir el comportamiento de las notificaciones. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>Las leyes relativas a la privacidad difieren por país. Algunos países requieren que se informe a los usuarios de los tipos de datos recopilados por aplicaciones móviles. Verifique las leyes correspondientes a las aplicaciones móviles de su país. Asegúrese de que las notificaciones push enviadas a aplicaciones móviles cumplan los requisitos y condiciones especificados por Apple (servicio Apple Push Notification) y Google (Google Cloud Messaging o Mensajería de Firebase Cloud Messaging).

**Contenido relacionado:**

* [Preparación y envío de una notificación Push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creación de una notificación push multilingües](../../channels/using/creating-a-multilingual-push-notification.md)
* [Envío de una notificación Push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)
* [Preguntas más frecuentes sobre Push y en la aplicación](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>Para aprovechar la función de notificación push de Campaign, debe proporcionar un certificado push válido en formato. pem sin contraseña.
Si tiene un certificado p 12 válido, puede convertirlo fácilmente en un archivo. pem con recursos en línea.

Primero, para poder enviar notificaciones push, debe configurar su aplicación móvil mediante SDK V 4. También puede configurar su aplicación móvil mediante SDK de plataforma de experiencias. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Antes de enviar las notificaciones Push, debe:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configure la aplicación móvil en:

   * Adobe Campaign
   * Interfaz de Adobe Mobile Services

1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado desde la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Mobile Cloud Mobile en su aplicación móvil.

1. Defina los datos que desee recopilar de los suscriptores de la aplicación. Los suscriptores de la aplicación móvil que tienen un perfil en la base de datos de Adobe Campaign se reconcilian según los criterios definidos.

Después de configurar la aplicación móvil, puede empezar a preparar y enviar los mensajes en la aplicación. For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

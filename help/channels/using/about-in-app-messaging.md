---
title: Acerca de la mensajería en la aplicación
description: Mostrar mensaje o alerta dentro de la aplicación móvil con mensajería en la aplicación.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
TQID: https://experienceleague.adobe.com/olwPmGMR2gMySu7Nx65g2bPvaxN6kjiRD94FyHxhg3A
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 85%

---

# Acerca de la mensajería en la aplicación{#about-in-app-messaging}

La mensajería en la aplicación es un canal de mensajería que le permite mostrar un mensaje cuando el usuario está activo en la aplicación móvil. Este tipo de mensaje es gratuito para las notificaciones push que se envían al centro de notificaciones del teléfono de los usuarios. Para obtener más información sobre el canal de notificaciones push, consulte esta [sección](../../channels/using/about-push-notifications.md).

Este canal requiere que las aplicaciones móviles se integren con el SDK de Adobe Experience Platform. Estas aplicaciones deben activarse en la interfaz de usuario de la recopilación de datos antes de estar disponibles en Adobe Campaign para entregas en la aplicación.

![](assets/launch_campaign.png)

Para empezar a enviar mensajes en la aplicación en aplicaciones móviles que utilicen el SDK de Experience Platform, debe cumplir los siguientes requisitos previos:

1. En Adobe Campaign, asegúrese de que puede acceder al canal **[!UICONTROL In-App]**. Si no puede acceder a estos canales, póngase en contacto con el equipo de su cuenta.

1. Para aprovechar los casos de uso móvil en Adobe Campaign Standard con una aplicación para SDK de Experience Cloud, se debe crear una aplicación móvil en la interfaz de usuario de recopilación de datos y configurarla en Adobe Campaign Standard. Para obtener la guía paso a paso, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

1. Una vez configurada, ahora puede preparar su mensaje en la aplicación. Para obtener más información, consulte [esta página](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Entonces, puede decidir enviar un [mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md) o [personalizar un tipo de mensaje de notificación local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Su envío está ahora listo para ejecutarse. Para obtener más información, consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenido relacionado:**

* [Informe en la aplicación](../../reporting/using/in-app-report.md)
* [Casos de uso móvil admitidos en Adobe Campaign Standard](../../administration/using/configuring-rules-launch.md)
* [Guía de Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Gestión de campos de perfil móvil con datos personales y confidenciales {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

En Adobe Campaign, los datos de atributos de perfil móviles enviados desde dispositivos móviles se almacenan en el recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que le permite definir los datos que desea recopilar de los suscriptores de las aplicaciones.

Este recurso debe ampliarse para recopilar los datos que se van a enviar desde el dispositivo móvil a Adobe Campaign. Para ello, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conocer los pasos detallados.

Para habilitar la personalización de los mensajes en la aplicación de forma más segura, es necesario configurar los campos de perfil móvil de este recurso. En **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, al crear los nuevos campos de perfiles móviles, marque **[!UICONTROL Personal and Sensitive]** para que no estén disponibles durante la personalización de mensajes en la aplicación.

>[!NOTE]
>
>Si tiene una implementación existente con la extensión de recursos personalizada en esta tabla, le recomendamos que etiquete los campos correctamente antes de utilizarlos para personalizar los mensajes en la aplicación.

![](assets/in_app_personal_data_2.png)

Una vez que su recurso personalizado de **[!UICONTROL Subscriptions to an application]** ha sido configurado y publicado, puede empezar a preparar la entrega en la aplicación con la plantilla **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Solo los campos no personales y no confidenciales estarán disponibles en el recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** para su personalización.

Si necesita personalizar con los campos **Personal y confidencial**, recomendamos utilizar la plantilla **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** que tiene un mecanismo de seguridad adicional para garantizar que los datos PII de los usuarios sigan siendo seguros.

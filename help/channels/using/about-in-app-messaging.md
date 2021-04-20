---
solution: Campaign Standard
product: campaign
title: Acerca de la mensajería en la aplicación
description: Mostrar mensaje o alerta dentro de la aplicación móvil con mensajería en la aplicación.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: Business Practitioner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 29%

---


# Acerca de la mensajería en la aplicación{#about-in-app-messaging}

La mensajería en la aplicación es un canal de mensajería que le permite mostrar un mensaje cuando el usuario está activo en la aplicación móvil. Este tipo de mensaje es gratuito para las notificaciones push que se envían al centro de notificaciones del teléfono de los usuarios. Para obtener más información sobre el canal de notificaciones push, consulte esta [sección](../../channels/using/about-push-notifications.md).

Este canal requiere que las aplicaciones móviles se integren con el SDK de Adobe Experience Platform. Estas aplicaciones deben activarse en Adobe Experience Platform Launch antes de estar disponibles en Adobe Campaign para entregas en la aplicación.

![](assets/launch_campaign.png)

Para empezar a enviar mensajes en la aplicación en aplicaciones móviles que utilicen el SDK de Experience Platform, debe cumplir los siguientes requisitos previos:

1. En Adobe Campaign, asegúrese de que puede acceder al canal **[!UICONTROL In-App]**. Si no puede acceder a estos canales, póngase en contacto con el equipo de su cuenta.

1. Para aprovechar los casos de uso móvil en Adobe Campaign Standard con una aplicación de SDK de Experience Cloud, se debe crear una aplicación móvil en Adobe Experience Platform Launch y configurarla en Adobe Campaign Standard. Para obtener la guía paso a paso, consulte esta [página](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

1. Una vez configurada, ahora puede preparar su mensaje en la aplicación. Para obtener más información, consulte [esta página](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Entonces, puede decidir enviar un [mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md) o [personalizar un tipo de mensaje de notificación local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Su envío está ahora listo para ejecutarse. Para obtener más información, consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenido relacionado:**

* [Informe en la aplicación](../../reporting/using/in-app-report.md)
* [Casos de uso móvil admitidos en Adobe Campaign Standard](https://helpx.adobe.com/es/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [Guía de Campaign Standard Mobile](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html)

## Preguntas frecuentes en la aplicación {#in-app-faq}

### ¿Cuáles serían algunas recomendaciones útiles sobre recursos para obtener más información sobre el canal en la aplicación en Adobe Campaign Standard? {#resources-inapp}

Consulte los siguientes recursos:

* [Tutoriales en vídeo](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Publicación en el blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Página de comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### ¿Cuál es el propósito de las API de extensiones de Campaign setLinkageField y resetLinkageField? {#extensions-apis}

Dado que el SDK extrae los mensajes en la aplicación de Campaign, queremos proporcionar un mecanismo seguro para garantizar que los mensajes en la aplicación que contienen datos PII no caigan en manos malintencionadas. Como tal, tenemos el siguiente mecanismo para garantizar la entrega segura de mensajes al dispositivo:

* Los clientes marcan los campos de perfil móvil (tabla appSubscriberRcp) como Personal y confidencial si desean garantizar que esta información en particular se proporcione de forma segura.
* Los campos marcados como tales solo se pueden usar en la plantilla de perfil (no en la plantilla appSubscriber ni en la plantilla Broadcast) que tiene un mecanismo de seguridad adicional integrado.
* Los mensajes creados con la plantilla Perfil solo se pueden servir cuando el usuario ha iniciado sesión en la aplicación.
* Para facilitar este protocolo de enlace seguro, los desarrolladores de aplicaciones móviles deben pasar detalles de autenticación adicionales mediante la API setLinkageField . Tenga en cuenta que el campo de vinculación son los que se identifican como vínculo entre Perfil móvil y Perfil CRM al ampliar la tabla appSubscriberRcp .
* Deben vaciar los mensajes en la aplicación almacenados en el dispositivo y los campos resetLinkagefields cuando el usuario cierre la sesión de la aplicación mediante resetLinkageField. Esto garantiza que si un usuario diferente inicia sesión en la aplicación, no vea los mensajes destinados al usuario anterior.
* Consulte [API del SDK móvil](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) para implementar este mecanismo de seguridad en el lado del cliente.

### ¿Qué tengo que hacer para habilitar los informes en la aplicación en Campaign? {#enable-inapp-reporting}

Debe configurar el postback del seguimiento en la aplicación. Las instrucciones se encuentran [aquí](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback).

Para implementar el seguimiento de notificaciones locales, consulte esta [página](../../administration/using/local-tracking.md).

### ¿Qué informes están disponibles para el canal en la aplicación? {#report-inapp}

Hay disponible un informe listo para usar en Adobe Campaign para el canal en la aplicación. Consulte esta [documentación](../../reporting/using/in-app-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#in-app-delivery) para comprender cómo se calculan las métricas en la aplicación.

### ¿Admite variantes de contenido multilingües para In-App de forma similar a la push? {#multilingual-inapp}

Ahora no hay plantillas multilingües disponibles para la mensajería en la aplicación.

Sin embargo, si el objetivo es enviar un mensaje en la aplicación en un idioma distinto del inglés, el contenido se puede pegar directamente en los cuadros de texto disponibles.

![](assets/faq_inapp.png)

### ¿Se pueden añadir campos de personalización de Campaign a HTML personalizado? {#custom-html-inapp}

No, aún no es compatible.

### He configurado un mensaje de alerta, pero no se muestra en el dispositivo. {#alert-message}

Para los mensajes de alerta, se requiere al menos un botón de rechazo (principal o secundario deben tener eliminación de acción). De lo contrario, es posible guardar el mensaje, pero no se recibirá.

### Si las notificaciones locales no se reproducen los sonidos personalizados de iOS; ¿se reproducirá el sonido predeterminado? {#local-notification-sound}

Para el sonido personalizado en iOS, debe proporcionar un nombre de archivo con extensión al crear una notificación local (por ejemplo, sound.caf). Si no se proporciona esta extensión, se utiliza el sonido predeterminado.

### ¿Los vínculos profundos son compatibles con los mensajes en la aplicación? {#inapp-deeplinks}

Sí, los vínculos profundos son compatibles con los mensajes en la aplicación. Los vínculos profundos deben incluir:

* idioma que indica que el seguimiento de envíos debe deshabilitarse para que funcionen los vínculos profundos.
* Appsflyer con Branch como socios que pueden hacer el seguimiento de vínculos profundos. Para obtener más información sobre la integración de Rama y Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

### ¿Se puede activar un mensaje en la aplicación cuando el usuario inicia la aplicación desde una notificación push? {#inapp-push-trigger}

Sí, estos mensajes también se denominan mensajes de cadena de margaritas. Siga el proceso a continuación:

1. Crear un mensaje en la aplicación.

1. Defina un evento personalizado y selecciónelo como un déclencheur de evento para este IAM, por ejemplo: &quot;Déclencheur desde vista previa de otoño Push&quot;.

1. Al crear el mensaje push, defina una variable personalizada cuyo valor se pueda configurar como un evento utilizado para almacenar en déclencheur IAM, por ejemplo Clave = &quot;inappkey&quot; y valor = &quot;Déclencheur de la vista previa de otoño Push&quot;.

1. En el código de la aplicación móvil, implemente el déclencheur de evento de la siguiente manera:

   ![](assets/faq_inapp_2.png)

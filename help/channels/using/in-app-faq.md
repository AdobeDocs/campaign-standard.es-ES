---
title: Preguntas frecuentes en la aplicación
description: Preguntas más frecuentes sobre la mensajería en la aplicación
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
source-git-commit: df7fce6f2fd98688e5a1fb5bc84603e6b3df5cd4
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---


# Preguntas frecuentes en la aplicación {#in-app-faq}

## ¿Cuáles serían algunas recomendaciones útiles sobre recursos para obtener más información sobre el canal en la aplicación en Adobe Campaign Standard? {#resources-inapp}

Consulte los siguientes recursos:

* [Tutoriales en vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Publicación en el blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Página de comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## ¿Cuál es el propósito de las API de extensiones de Campaign setLinkageField y resetLinkageField? {#extensions-apis}

Dado que el SDK extrae los mensajes en la aplicación de Campaign, queremos proporcionar un mecanismo seguro para garantizar que los mensajes en la aplicación que contienen datos PII no caigan en manos malintencionadas. Como tal, tenemos el siguiente mecanismo para garantizar la entrega segura de mensajes al dispositivo:

* Los clientes marcan los campos de perfil móvil (tabla appSubscriberRcp) como Personal y confidencial si desean garantizar que esta información en particular se proporcione de forma segura.
* Los campos marcados como tales solo se pueden usar en la plantilla de perfil (no en la plantilla appSubscriber ni en la plantilla Broadcast) que tiene un mecanismo de seguridad adicional integrado.
* Los mensajes creados con la plantilla Perfil solo se pueden servir cuando el usuario ha iniciado sesión en la aplicación.
* Para facilitar este protocolo de enlace seguro, los desarrolladores de aplicaciones móviles deben pasar detalles de autenticación adicionales mediante la API setLinkageField . Tenga en cuenta que el campo de vinculación son los que se identifican como vínculo entre Perfil móvil y Perfil CRM al ampliar la tabla appSubscriberRcp .
* Deben vaciar los mensajes en la aplicación almacenados en el dispositivo y los campos resetLinkagefields cuando el usuario cierre la sesión de la aplicación mediante resetLinkageField. Esto garantiza que si un usuario diferente inicia sesión en la aplicación, no vea los mensajes destinados al usuario anterior.
* Consulte [API del SDK móvil](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) para implementar este mecanismo de seguridad en el lado del cliente.

## ¿Qué tengo que hacer para habilitar los informes en la aplicación en Campaign? {#enable-inapp-reporting}

Debe configurar el postback del seguimiento en la aplicación. Las instrucciones se encuentran [aquí](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

Para implementar el seguimiento de notificaciones locales, consulte esta [página](../../administration/using/local-tracking.md).

## ¿Qué informes están disponibles para el canal en la aplicación? {#report-inapp}

Hay disponible un informe listo para usar en Adobe Campaign para el canal en la aplicación. Consulte esta [documentación](../../reporting/using/in-app-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#in-app-delivery) para comprender cómo se calculan las métricas en la aplicación.

## ¿Admite variantes de contenido multilingües para In-App de forma similar a la push? {#multilingual-inapp}

Ahora no hay plantillas multilingües disponibles para la mensajería en la aplicación.

Sin embargo, si el objetivo es enviar un mensaje en la aplicación en un idioma distinto del inglés, el contenido se puede pegar directamente en los cuadros de texto disponibles.

![](assets/faq_inapp.png)

## ¿Se pueden añadir los campos de personalización de Campaign al HTML personalizado? {#custom-html-inapp}

No, aún no es compatible.

## He configurado un mensaje de alerta, pero no se muestra en el dispositivo. {#alert-message}

Para los mensajes de alerta, se requiere al menos un botón de rechazo (principal o secundario deben tener eliminación de acción). De lo contrario, es posible guardar el mensaje, pero no se recibirá.

## Si las notificaciones locales no se reproduce el sonido personalizado de iOS; ¿se reproducirá el sonido predeterminado? {#local-notification-sound}

Para el sonido personalizado en iOS, debe proporcionar un nombre de archivo con extensión al crear una notificación local (por ejemplo, sound.caf). Si no se proporciona esta extensión, se utiliza el sonido predeterminado.

## ¿Los vínculos profundos son compatibles con los mensajes en la aplicación? {#inapp-deeplinks}

Sí, los vínculos profundos son compatibles con los mensajes en la aplicación. Los vínculos profundos deben incluir:

* idioma que indica que el seguimiento de envíos debe deshabilitarse para que funcionen los vínculos profundos.
* Appsflyer con Branch como socios que pueden hacer el seguimiento de vínculos profundos. Para obtener más información sobre la integración de Rama y Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## ¿Se puede activar un mensaje en la aplicación cuando el usuario inicia la aplicación desde una notificación push? {#inapp-push-trigger}

Sí, estos mensajes también se denominan mensajes de cadena de margaritas. Siga el proceso a continuación:

1. Crear un mensaje en la aplicación.

1. Defina un evento personalizado y selecciónelo como un déclencheur de evento para este IAM, por ejemplo: &quot;Déclencheur desde vista previa de otoño Push&quot;.

1. Al crear el mensaje push, defina una variable personalizada cuyo valor se pueda configurar como un evento utilizado para almacenar en déclencheur IAM, por ejemplo Clave = &quot;inappkey&quot; y valor = &quot;Déclencheur de la vista previa de otoño Push&quot;.

1. En el código de la aplicación móvil, implemente el déclencheur de evento de la siguiente manera:

   ![](assets/faq_inapp_2.png)

---
title: Preguntas frecuentes en la aplicación
description: Preguntas frecuentes sobre la mensajería en la aplicación
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---

# Preguntas frecuentes en la aplicación {#in-app-faq}

## ¿Cuáles serían algunos recursos y recomendaciones útiles para obtener más información sobre el canal en la aplicación en Adobe Campaign Standard? {#resources-inapp}

Consulte los siguientes recursos:

* [Tutorials de vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Publicación de blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Página de comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## ¿Cuál es el propósito de las API de extensiones de Campaign setLinkageField y resetLinkageField? {#extensions-apis}

Dado que el SDK extrae los mensajes en la aplicación de Campaign, queremos proporcionar un mecanismo seguro para garantizar que los mensajes en la aplicación que contienen datos PII no caigan en manos malintencionadas. Como tal, contamos con el siguiente mecanismo para garantizar la entrega segura de mensajes al dispositivo:

* Los clientes marcan los campos de campos de perfil móvil (tabla appSubscriberRcp) como Personales y confidenciales si desean garantizar que esta información en particular se entregue de forma segura.
* Los campos marcados como tales solo se pueden usar en la plantilla Perfil (no en la plantilla appSubscriber o la plantilla Broadcast) que tenga integrado un mecanismo de seguridad adicional.
* Los mensajes creados con la plantilla de perfil solo se pueden entregar cuando el usuario ha iniciado sesión en la aplicación.
* Para facilitar este protocolo de enlace seguro, los desarrolladores de aplicaciones móviles deben pasar detalles de autenticación adicionales mediante la API setLinkageField. Tenga en cuenta que los campos de vinculación son los que se identifican como el vínculo entre el perfil móvil y el perfil CRM al ampliar la tabla appSubscriberRcp.
* Deben vaciar los mensajes en la aplicación almacenados en el dispositivo y restablecer los campos de vinculación cuando el usuario cierre la sesión de la aplicación mediante resetLinkageField. Esto garantiza que, si un usuario diferente inicia sesión en la aplicación, no verá los mensajes destinados al usuario anterior.
* Consulte [API de SDK móvil](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) para implementar este mecanismo de seguridad del lado del cliente.

## ¿Qué tengo que hacer para habilitar la creación de informes en la aplicación en Campaign? {#enable-inapp-reporting}

Debe configurar el postback de seguimiento en la aplicación. Se pueden encontrar las instrucciones [aquí](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

Para implementar el seguimiento de notificaciones locales, consulte esto [página](../../administration/using/local-tracking.md).

## ¿Qué informes están disponibles para el canal en la aplicación? {#report-inapp}

Hay disponible un informe predeterminado en Adobe Campaign para el canal en la aplicación. Consulte esta sección [documentación](../../reporting/using/in-app-report.md).

Ver esto [página](../../reporting/using/indicator-calculation.md#in-app-delivery) para comprender cómo se calcula cada métrica en la aplicación.

## ¿Admite variantes de contenido multilingüe para aplicaciones similares a push? {#multilingual-inapp}

Ahora no hay plantillas multilingües disponibles para la mensajería en la aplicación.

Sin embargo, si el objetivo es enviar un mensaje en la aplicación en un idioma distinto del inglés, el contenido se puede pegar directamente en los cuadros de texto disponibles.

![](assets/faq_inapp.png)

## ¿Se pueden añadir campos de personalización de Campaign al HTML personalizado? {#custom-html-inapp}

No, aún no es compatible.

## He configurado un mensaje de alerta, pero no aparece en el dispositivo. {#alert-message}

Para los mensajes de alerta, se requiere al menos un botón de descarte (el principal o el secundario deben tener acciones de descarte). De lo contrario, es posible guardar el mensaje, pero no se recibirá.

## Si el sonido personalizado de iOS de notificaciones locales no se reproduce, ¿se reproducirá el sonido predeterminado en su lugar? {#local-notification-sound}

Para el sonido personalizado en iOS, debe proporcionar un nombre de archivo con la extensión al crear una notificación local (por ejemplo, sound.caf). Si no se proporciona esta extensión, se utilizará el sonido predeterminado.

## ¿Se admiten los vínculos profundos en los mensajes en la aplicación? {#inapp-deeplinks}

Sí, los vínculos profundos son compatibles con los mensajes en la aplicación. Los vínculos profundos deben incluir:

* idioma que indica que el seguimiento de la entrega debe deshabilitarse para que funcionen los vínculos profundos.
* Folleto de aplicaciones con Branch como socios que pueden realizar el seguimiento de vínculos profundos. Para obtener más información sobre la integración de Rama y Adobe Campaign Standard, consulte esta sección [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## ¿Se puede activar un mensaje en la aplicación cuando el usuario inicia la aplicación desde una notificación push? {#inapp-push-trigger}

Sí, estos mensajes también se denominan mensajes en cadena. Siga el proceso a continuación:

1. Cree un mensaje en la aplicación.

1. Defina un evento personalizado y selecciónelo como déclencheur de evento para este IAM, por ejemplo, &quot;Déclencheur de la vista previa de otoño push&quot;.

1. Al crear el mensaje push, defina una variable personalizada cuyo valor pueda configurarse como evento utilizado para almacenar en déclencheur IAM, por ejemplo, Key = &quot;inappkey&quot; y value = &quot;Déclencheur de push de previsualización de otoño&quot;.

1. En el código de la aplicación móvil, implemente el déclencheur de eventos de la siguiente manera:

   ![](assets/faq_inapp_2.png)

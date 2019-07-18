---
title: Personalización de una notificación Push
seo-title: Personalización de una notificación Push
description: Personalización de una notificación Push
seo-description: Aprenda a personalizar las notificaciones Push con varias opciones avanzadas.
page-status-flag: no activado nunca
uuid: 8 cf 74 cad-b 1 ba -4 aad -83 bd -7289 cb 22 d 5 f 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: notificaciones push
discoiquuid: dc 944 c 85-2059-46 df-b 396-676 fe 3617 dd 1
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Customizing a push notification{#customizing-a-push-notification}

Para perfeccionar la notificación Push, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas al diseñar una notificación Push.

As an expert user, to configure mobile applications in Adobe Campaign, refer to the following technote [Understanding Campaign Standard Push Notifications Payload Structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

![](assets/push_notif_advanced.png)

**Contenido relacionado:**

* [Informe de notificaciones Push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación Push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)

## Play a sound {#play-a-sound}

The function **[!UICONTROL Play a sound]** gives the application the ability to play sounds on your device with the delivery of a push notification, when the app isn't running.

Un sonido alertará a los usuarios de una notificación Push, lo que le dará más visibilidad. Para incluir un sonido en la aplicación móvil:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. In the **[!UICONTROL Play a sound]** field, enter the filename of the sound file, without the extension, to be played by the mobile device when the notification is received.

   For more information on supported media formats, refer to [Apple](https://support.apple.com/kb/PH16864?locale=en_US) and [Android](https://developer.android.com/guide/topics/media/media-formats.html) documentations.

   ![](assets/push_notif_advanced_7.png)

1. El archivo de sonido se reproduce al enviar la notificación si el archivo se define en el paquete de la aplicación móvil. De lo contrario, se reproduce el sonido predeterminado del dispositivo.

A continuación, el usuario recibirá la notificación push y el sonido solo si el teléfono no está silenciado.

## Refresh the badge value {#refresh-the-badge-value}

Se utiliza un distintivo para mostrar directamente en el icono de la aplicación el número de información nueva sin leer. El valor de distintivo desaparecerá cuando el usuario abra o lee el nuevo contenido de la aplicación.

Cuando se recibe una notificación en un dispositivo, se puede actualizar o agregar un valor de distintivo para la aplicación relacionada. Para enviar un valor de distintivo desde Servidor:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. El valor de distintivo debe ser un número entero y se puede actualizar de diferentes maneras:

   * To refresh the badge, enter 0 in the **[!UICONTROL Value of the badge]** field. Esto eliminará el distintivo del icono de la aplicación.
   * To add a badge value, enter any number in the **[!UICONTROL Value of the badge]** field. Este número aparecerá automáticamente en el distintivo en cuanto el usuario reciba la notificación push.
   * Si el campo está vacío o no contiene un entero, el valor de la marca no cambiará.
   Here, we entered 1 in the **[!UICONTROL Value of the badge]** field to let the users know that they have a new information in their application.

   ![](assets/push_notif_advanced_8.png)

1. Después de enviar el mensaje, los usuarios recibirán la notificación Push y su aplicación mostrará automáticamente el nuevo valor de distintivo.

   ![](assets/push_notif_advanced_1.png)

## Add a deeplink {#add-a-deeplink}

Un vínculo profundo permite llevar a los usuarios directamente al contenido ubicado dentro de la aplicación (en lugar de abrir una página de explorador Web).

Un vínculo profundo puede incluir datos de personalización para una experiencia dentro de la aplicación personalizada. Por ejemplo, los primeros nombres de los destinatarios se rellenan automáticamente en la página a la que la dirige la aplicación.

Para agregar un vínculo profundo en una notificación push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the link in the **[!UICONTROL Add a deeplink]** field.

   ![](assets/push_notif_advanced_3.png)

1. Después de enviar el mensaje, los usuarios recibirán la notificación Push y accederán a la página específica de la aplicación interactuando con la notificación, por ejemplo, haciendo clic o haciendo clic en el botón de llamada a acción.

   ![](assets/push_notif_advanced_4.png)

## Define an action {#define-an-action}

Puede agregar un ID de categoría si está disponible en la aplicación móvil y, a continuación, mostrar los botones de acción. Estas notificaciones proporcionan al usuario una manera más rápida de realizar diferentes tareas en respuesta a una notificación sin abrir o navegar en la aplicación.

El cuadro de diálogo que aparece en el teléfono del usuario requiere la decisión de continuar. Cuando el usuario selecciona una de las acciones, el sistema notifica a la aplicación para que pueda realizar tareas asociadas.

Para agregar una categoría en una notificación Push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter a predefined category name in the **[!UICONTROL Category]** field to display actionable buttons when the push notification is received.

   El desarrollador de aplicaciones móviles debe definir el ID de categoría y el comportamiento esperado de los botones en la aplicación. For more on this, refer to the [Apple Developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (**Configuring Categories and Actionable Notifications** section) or the [Android Developer documentation](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. Después de enviar la notificación Push, los usuarios la recibirán y tienen que actuar con los botones procesables previamente configurados.

   ![](assets/push_notif_actionable_buttons.png)

Según la acción del usuario, se notificará a la aplicación para que pueda realizar cualquier tarea asociada.

## Add custom fields {#add-custom-fields}

Los campos personalizados permiten pasar datos personalizados en la carga útil en forma de pares de valor clave. Esta opción se puede utilizar para pasar datos adicionales a la aplicación más allá de las claves predefinidas.

Para ello:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. In the **[!UICONTROL Custom fields]** category, click the **[!UICONTROL Add an element]** button.
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   ![](assets/push_notif_advanced_10.png)

1. La gestión y el propósito de los campos personalizados es completamente hasta la aplicación móvil. En la notificación Push siguiente, la aplicación ha utilizado campos personalizados para mostrar etiquetas de botón para la notificación Push.

   ![](assets/push_notif_actionable_buttons.png)

## Add rich media content {#add-rich-media-content}

El contenido de medios enriquecidos permite tener una mejor participación de los usuarios, lo que significa que el usuario se pondrá más inclinado a abrir la notificación Push.

Puede incluir una imagen, gif, audio o archivo de vídeo que se reproducirá o mostrará en la propia notificación. Los usuarios de la aplicación no tendrán que abrir la aplicación para verlo.

Para incluir medios enriquecidos en la notificación Push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the URL of your file in the **[!UICONTROL Rich media content URL]** field for each format: iOS and Android.

   Para iOS 10 o superior, puede insertar archivos de imagen, gif, audio y vídeo. Para versiones iOS anteriores, la notificación Push se mostrará sin contenido enriquecido. For detailed steps on how to display an image from an Adobe Campaign push notification on an iOS device, refer to this [page](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   En Android, solo se pueden incluir imágenes.

   ![](assets/push_notif_advanced_6.png)

1. Después de enviar el mensaje, el usuario recibirá su notificación Push y podrá ver el contenido de medios enriquecidos.

   ![](assets/push_notif_advanced_2.png)

## Change the notification behavior for iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

For iOS 10 or higher, two additional options are available in the **[!UICONTROL Advanced options]** section of push notifications: **[!UICONTROL Mutable content]** and **[!UICONTROL Content available]**.

When the **[!UICONTROL Mutable content]** option is checked and/or a Rich media content URL is added, the mutable-content flag will be sent in the push payload and will allow the push notification content to be modified by a notification service application extension provided in iOS SDK. For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

Luego puede aprovechar las extensiones de aplicaciones móviles para modificar aún más el contenido o la presentación de las notificaciones push que llegan desde Adobe Campaign. Por ejemplo, los usuarios pueden aprovechar esta opción para:

* Descifrar datos que se han entregado en un formato cifrado
* Descargar imágenes u otros archivos multimedia y agregarlos como archivos adjuntos a una notificación
* Cambiar el texto del cuerpo o del título de una notificación
* Agregar un identificador de subproceso a una notificación

When **[!UICONTROL Content available]** is checked, the content available flag will be sent in the push payload to ensure that the app is woken up as soon as it receives the push notification, meaning that the app will be able to access the payload data. Esto funciona incluso si la aplicación se ejecuta en segundo plano y sin necesidad de interacción del usuario (p. ej., tocar en notificación Push). Sin embargo, esto no se aplica si la aplicación no se está ejecutando. For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Change the notification behavior for Android {#change-the-notification-behavior-for-android}

For Android, you can enter the URL of your file in the **Rich media content URL** field. Con la versión iOS, para Android solo se pueden incluir imágenes, no gif, archivos de audio o vídeo.

The **[!UICONTROL High priority]** checkbox allows you to set up a high or normal priority for your push notifications. For more information on message priority, refer to the [Google developer documentation](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)


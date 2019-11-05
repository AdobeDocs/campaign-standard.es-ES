---
title: Personalización de una notificación push
description: Descubra cómo personalizar las notificaciones push con varias opciones avanzadas.
page-status-flag: nunca activado
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: entrega,mobileAppContent,retroceso
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Personalización de una notificación push{#customizing-a-push-notification}

Para ajustar la notificación push, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña una notificación push.

Como usuario experto, para configurar aplicaciones móviles en Adobe Campaign, consulte la siguiente nota técnica [Explicación de la estructura](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)de carga útil de notificaciones push estándar de campaña.

![](assets/push_notif_advanced.png)

**Contenido relacionado:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)

## Reproducir un sonido {#play-a-sound}

La función **[!UICONTROL Play a sound]** permite a la aplicación reproducir sonidos en el dispositivo con la entrega de una notificación push, cuando la aplicación no se está ejecutando.

Un sonido alertará a los usuarios de una notificación push, lo que le dará más visibilidad. Para incluir un sonido en la aplicación móvil:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. En el **[!UICONTROL Play a sound]** campo, introduzca el nombre de archivo del archivo de sonido, sin la extensión, que se reproducirá en el dispositivo móvil cuando se reciba la notificación.

   Para obtener más información sobre los formatos de medios admitidos, consulte las documentaciones de [Apple](https://support.apple.com/kb/PH16864?locale=en_US) y [Android](https://developer.android.com/guide/topics/media/media-formats.html) .

   ![](assets/push_notif_advanced_7.png)

1. El archivo de sonido se reproduce al enviar la notificación si el archivo está definido en el paquete de la aplicación móvil. De lo contrario, se reproduce el sonido predeterminado del dispositivo.

El usuario recibirá la notificación push y el sonido sólo si su teléfono no está silenciado.

## Actualizar el valor del distintivo {#refresh-the-badge-value}

Un distintivo se utiliza para mostrar directamente en el icono de la aplicación el número de información nueva no leída. El valor del distintivo desaparecerá en cuanto el usuario abra o lea el nuevo contenido de la aplicación.

Cuando se recibe una notificación en un dispositivo, puede actualizar o agregar un valor de distintivo para la aplicación relacionada. Para enviar un valor de distintivo desde el servidor:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. El valor del distintivo debe ser un número entero y puede actualizarse de diferentes maneras:

   * Para actualizar el distintivo, escriba 0 en el **[!UICONTROL Value of the badge]** campo. Esto eliminará el distintivo del icono de la aplicación.
   * Para agregar un valor de distintivo, introduzca cualquier número en el **[!UICONTROL Value of the badge]** campo. Este número aparecerá automáticamente en el distintivo en cuanto el usuario reciba la notificación push.
   * Si el campo está vacío o no contiene un entero, el valor del distintivo no cambiará.
   Aquí, ingresamos 1 en el **[!UICONTROL Value of the badge]** campo para informar a los usuarios que tienen una nueva información en su aplicación.

   ![](assets/push_notif_advanced_8.png)

1. Después de enviar el mensaje, los usuarios recibirán la notificación push y su aplicación mostrará automáticamente el nuevo valor de distintivo.

   ![](assets/push_notif_advanced_1.png)

## Agregar un vínculo profundo {#add-a-deeplink}

Un vínculo profundo le permite llevar a los usuarios directamente al contenido ubicado dentro de la aplicación (en lugar de abrir una página del explorador Web).

Un vínculo profundo puede incluir datos de personalización para una experiencia personalizada en la aplicación. Por ejemplo, los nombres de los destinatarios se rellenan automáticamente en la página a la que la aplicación los dirige.

Para agregar un vínculo profundo en una notificación push:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. Escriba el vínculo en el **[!UICONTROL Add a deeplink]** campo.

   ![](assets/push_notif_advanced_3.png)

1. Después de enviar el mensaje, los usuarios recibirán la notificación push y accederán a la página específica de la aplicación interactuando con la notificación, por ejemplo tocando o haciendo clic en el botón de llamada a acción.

   ![](assets/push_notif_advanced_4.png)

## Definir una acción {#define-an-action}

Puede agregar un ID de categoría si está disponible en la aplicación móvil y, a continuación, mostrar los botones de acción. Estas notificaciones proporcionan al usuario una forma más rápida de realizar distintas tareas en respuesta a una notificación sin necesidad de abrir ni navegar en la aplicación.

El cuadro de diálogo que aparece en el teléfono del usuario requiere una decisión para continuar. Cuando el usuario selecciona una de las acciones, el sistema notifica a la aplicación para que pueda realizar cualquier tarea asociada.

Para agregar una categoría en una notificación push:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. Introduzca un nombre de categoría predefinido en el **[!UICONTROL Category]** campo para mostrar los botones procesables cuando se reciba la notificación push.

   El desarrollador de aplicaciones móviles debe definir el ID de categoría y el comportamiento esperado de los botones en la aplicación. Para obtener más información sobre este tema, consulte la documentación [para desarrolladores de](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) Apple (sección **Configuración de categorías y notificaciones** procesables) o la documentación [para desarrolladores de](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)Android.

   ![](assets/push_notif_advanced_9.png)

1. Después de enviar la notificación push, los usuarios la reciben y deben actuar con los botones procesables configurados previamente.

   ![](assets/push_notif_actionable_buttons.png)

Según la acción del usuario, se notificará a la aplicación para que pueda realizar cualquier tarea asociada.

## Agregar una fecha de caducidad {#add-expiration-date}

>[!NOTE]
>
>Estos cambios solo se aplican a partir de la versión de Campaign Standard 19.4.

La configuración de una fecha de caducidad en la notificación push le permite establecer una fecha de caducidad específica en la que Apple ([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns)) o Android ([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options)) ya no enviarán el mensaje.

Para agregar una fecha de caducidad a la notificación push:

1. Marque la **[!UICONTROL Expire message]** opción.

   >[!NOTE]
   >
   >Al seleccionar la **[!UICONTROL Expire message]** opción, la duración se establece automáticamente en 0. Si no cambia el valor, APNS y FCM intentarán enviar el mensaje inmediatamente. Si falla, el mensaje no se volverá a enviar.

1. En el **[!UICONTROL Duration]** campo, seleccione la validez de la notificación push.

   ![](assets/push_expiration.png)

1. Después de enviar la notificación push, si el usuario no la recibió de inmediato debido a que el teléfono no estaba encendido o no tenía señal, la notificación push se enviará dentro del intervalo de fecha de caducidad.

Tenga en cuenta que si la notificación push no se envió antes de la fecha de caducidad, se descartará.

## Agregar campos personalizados {#add-custom-fields}

Los campos personalizados permiten pasar datos personalizados en la carga útil en forma de par de valor clave. Esta opción se puede utilizar para pasar datos adicionales a la aplicación más allá de las claves predefinidas.

Para ello:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. En la **[!UICONTROL Custom fields]** categoría, haga clic en el **[!UICONTROL Add an element]** botón.
1. Introduzca **[!UICONTROL Keys]** el valor **[!UICONTROL Values]** asociado a cada clave.

   ![](assets/push_notif_advanced_10.png)

1. El manejo y el propósito de los campos personalizados dependen totalmente de la aplicación móvil. En la notificación push siguiente, la aplicación ha utilizado campos personalizados para mostrar etiquetas de botón para la notificación push.

   ![](assets/push_notif_actionable_buttons.png)

## Adición de contenido multimedia enriquecido {#add-rich-media-content}

El contenido de medios enriquecidos le permite tener una mejor participación del usuario, lo que significa que el usuario estará más inclinado a abrir la notificación push.

Puede incluir un archivo de imagen, gif, audio o vídeo que se reproducirá o mostrará en la propia notificación. Los usuarios de la aplicación no tendrán que abrir la aplicación para verla.

Para incluir medios enriquecidos en la notificación push:

1. Abra la notificación push y acceda a la **[!UICONTROL Advanced options]** sección.
1. Introduzca la dirección URL del archivo en el **[!UICONTROL Rich media content URL]** campo de cada formato: iOS y Android.

   Para iOS 10 o superior, puede insertar archivos de imagen, gif, audio y vídeo. Para versiones anteriores de iOS, la notificación push se mostrará sin contenido enriquecido. Para ver los pasos detallados sobre cómo mostrar una imagen desde una notificación push de Adobe Campaign en un dispositivo iOS, consulte esta [página](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   Para Android, solo puede incluir imágenes.

   ![](assets/push_notif_advanced_6.png)

1. Después de enviar el mensaje, el usuario recibirá la notificación push y podrá ver el contenido multimedia enriquecido.

   ![](assets/push_notif_advanced_2.png)

## Cambiar el comportamiento de notificación para iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

Para iOS 10 o superior, hay dos opciones adicionales disponibles en la sección **[!UICONTROL Advanced options]** de notificaciones push: **[!UICONTROL Mutable content]** y **[!UICONTROL Content available]**.

Cuando se selecciona la **[!UICONTROL Mutable content]** opción y/o se agrega una URL de contenido de medios enriquecidos, el indicador de contenido mutable se envía en la carga útil push y permite que el contenido de la notificación push se modifique con una extensión de aplicación de servicio de notificación proporcionada en el SDK de iOS. Para obtener más información sobre esto, consulte la documentación [para desarrolladores de](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)Apple.

A continuación, puede aprovechar las extensiones de la aplicación móvil para modificar aún más el contenido o la presentación de las notificaciones push entrantes enviadas desde Adobe Campaign. Por ejemplo, los usuarios pueden aprovechar esta opción para:

* Descifrar datos que se entregaron en formato cifrado
* Descargar imágenes u otros archivos multimedia y agregarlos como datos adjuntos a una notificación
* Cambiar el texto del cuerpo o del título de una notificación
* Agregar un identificador de subproceso a una notificación

Cuando **[!UICONTROL Content available]** se selecciona, el indicador de contenido disponible se envía en la carga útil push para garantizar que la aplicación se activa en cuanto recibe la notificación push, lo que significa que la aplicación podrá acceder a los datos de carga útil. Esto funciona incluso si la aplicación se está ejecutando en segundo plano y sin necesidad de interacción del usuario (p. ej., al tocar la notificación Push); sin embargo, esto no se aplica si la aplicación no se está ejecutando. For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Cambiar el comportamiento de notificación para Android {#change-the-notification-behavior-for-android}

Para Android, puede introducir la URL del archivo en el campo URL **de contenido de medios** enriquecidos. Mientras que con la versión de iOS, para Android solo puede incluir imágenes y no archivos gif, de audio o de vídeo.

La **[!UICONTROL High priority]** casilla de verificación permite configurar una prioridad alta o normal para las notificaciones push. Para obtener más información sobre la prioridad de los mensajes, consulte la documentación [para desarrolladores de](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)Google.

![](assets/push_notif_advanced_11.png)


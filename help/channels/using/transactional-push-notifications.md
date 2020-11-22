---
solution: Campaign Standard
product: campaign
title: Notificaciones push transaccionales
description: Obtenga información sobre cómo crear y publicar una notificación push transaccional.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# Notificaciones push transaccionales{#transactional-push-notifications}

Puede utilizar Adobe Campaign para enviar notificaciones push transaccionales en dispositivos móviles iOS y Android. Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK para móviles de Experience Cloud.

>[!NOTE]
>
>El canal push es opcional. Compruebe el acuerdo de licencia. Para obtener más información sobre las notificaciones push estándar, consulte Notificaciones [](../../channels/using/about-push-notifications.md)push.

Puede enviar dos tipos de notificaciones push de transacciones:

* Notificaciones push transaccionales dirigidas a un evento.
* Notificaciones push transaccionales dirigidas a perfiles de la base de datos de Adobe Campaign.

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de seguridad **[!UICONTROL Administrators (all units)]**.

## Notificaciones push transaccionales dirigidas a un evento {#transactional-push-notifications-targeting-an-event}

Puede enviar una notificación push de transacción anónima a todos los usuarios que hayan adhesión para recibir notificaciones desde la aplicación móvil.

En este caso, solo se utilizan los datos contenidos en el propio evento para definir el destinatario de envío. No se aprovecha ningún dato de la base de datos de perfil integrada de Adobe Campaign.

### Envío de una notificación push transaccional dirigida a un evento {#sending-a-transactional-push-notification-targeting-an-----------event}

Por ejemplo, una compañía de aerolíneas desea invitar a los usuarios de su aplicación móvil a que procedan a la puerta de embarque correspondiente.

La compañía enviará una notificación push transaccional por usuario (identificada con un token de registro), mediante una aplicación móvil, a través de un solo dispositivo.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   Puede insertar campos de personalización para agregar elementos que definió al crear el evento.

   ![](assets/message-center_push_content.png)

   Para buscar estos campos, haga clic en el lápiz situado junto a un elemento, haga clic en **[!UICONTROL Insert personalization field]** y seleccione **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obtener más información sobre la edición de contenido de una notificación push, consulte [Creación de una notificación](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

1. Mediante la API de Adobe Campaign Standard REST, envíe un evento a un token de registro (ABCDEF123456789), mediante una aplicación móvil (WeFlight), en Android (gcm), que contenga los datos de embarque.

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte Integración [del](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)sitio.

Si existe el token de registro, el usuario correspondiente recibe una notificación push transaccional que incluye el siguiente contenido:

&quot;Hola Jane Green, el embarque acaba de empezar! Proceda a la Puerta B18.&quot;

## Notificaciones push transaccionales dirigidas a un perfil {#transactional-push-notifications-targeting-a-profile}

Puede enviar una notificación push transaccional a los perfiles de Adobe Campaign que se hayan suscrito a la aplicación móvil. Este envío puede contener campos de [personalización](../../designing/using/personalization.md#inserting-a-personalization-field) , como el nombre del destinatario.

En este caso, el evento debe contener algunos campos que permitan la reconciliación con un perfil de la base de datos de Adobe Campaign.

Al destinar perfiles, se envía una notificación push transaccional por aplicación móvil y por dispositivo. Por ejemplo, si un usuario de Adobe Campaign se ha suscrito a dos aplicaciones, este usuario recibirá dos notificaciones. Si un usuario se ha suscrito a la misma aplicación con dos dispositivos diferentes, este usuario recibirá una notificación en cada dispositivo.

Las aplicaciones móviles a las que se ha suscrito un perfil se muestran en la **[!UICONTROL Mobile App Subscriptions]** ficha de este perfil. Para acceder a esta ficha, seleccione un perfil y haga clic en el **[!UICONTROL Edit profile properties]** botón de la derecha.

![](assets/push_notif_subscriptions.png)

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Perfiles](../../audiences/using/creating-profiles.md).

### Envío de una notificación push transaccional dirigida a un perfil {#sending-a-transactional-push-notification-targeting-a-----------profile}

Por ejemplo, una compañía de aerolíneas desea enviar una última llamada para el embarque a todos los usuarios de Adobe Campaign que se hayan suscrito a su aplicación móvil.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   A diferencia de las configuraciones basadas en eventos en tiempo real, usted tiene acceso directo a toda la información de perfil para personalizar su mensaje. Consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).

   Para obtener más información sobre la edición de contenido de notificaciones push. Consulte [Creación de una notificación](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Mediante la API de Adobe Campaign Standard REST, envíe un evento a un perfil.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte Integración [del](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)sitio.

   >[!NOTE]
   >
   >No hay campos de token de registro, aplicación y plataforma push. En este ejemplo, la reconciliación se realiza con el campo de correo electrónico.

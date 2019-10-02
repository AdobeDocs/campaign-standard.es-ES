---
title: Notificaciones push transaccionales
seo-title: Notificaciones push transaccionales
description: Notificaciones push transaccionales
seo-description: Obtenga información sobre cómo crear y publicar una notificación push transaccional.
page-status-flag: nunca activado
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: transaccional-mensajería
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d9357481a567cb0d11eea43211abf08a6dcb07d6

---


# Notificaciones push transaccionales{#transactional-push-notifications}

Puede utilizar Adobe Campaign para enviar notificaciones push transaccionales en dispositivos móviles iOS y Android. Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK de Experience Cloud Mobile.

>[!NOTE]
>
>El canal push es opcional. Compruebe el acuerdo de licencia. Para obtener más información sobre las notificaciones push estándar, consulte Notificaciones [](../../channels/using/about-push-notifications.md)push.

Puede enviar dos tipos de notificaciones push de transacciones:

* Notificaciones push transaccionales dirigidas a un evento.
* Notificaciones push transaccionales con perfiles de objetivo de la base de datos de Adobe Campaign.

Una vez creado y publicado un evento (el abandono del carro de compras explicado en [esta sección](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), la notificación push de transacción correspondiente se crea automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar una notificación](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) push transaccional.

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración o aparecer en el grupo de seguridad **[!UICONTROL Message Center agents]** (mcExec).

## Notificaciones push transaccionales dirigidas a un evento {#transactional-push-notifications-targeting-an-event}

Puede enviar una notificación push de transacción anónima a todos los usuarios que hayan elegido recibir notificaciones desde la aplicación móvil.

En este caso, solo se utilizan los datos contenidos en el propio evento para definir el objetivo de entrega. No se aprovecha ningún dato de la base de datos de perfiles integrados de Adobe Campaign.

### Envío de una notificación push transaccional dirigida a un evento {#sending-a-transactional-push-notification-targeting-an-----------event}

Por ejemplo, una empresa de aerolíneas desea invitar a sus usuarios de aplicaciones móviles a que procedan a la puerta de embarque correspondiente.

La empresa enviará una notificación push transaccional por usuario (identificada con un token de registro), utilizando una aplicación móvil, a través de un solo dispositivo.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.

   ![](assets/message-center_push_message.png)

1. Haga clic en el **[!UICONTROL Content]** bloque para modificar el título y el cuerpo del mensaje.

   Puede insertar campos de personalización para agregar elementos que definió al crear el evento.

   ![](assets/message-center_push_content.png)

   Para buscar estos campos, haga clic en el lápiz situado junto a un elemento, haga clic en **[!UICONTROL Insert personalization field]** y seleccione **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obtener más información sobre la edición de contenido de una notificación push, consulte [Creación de una notificación](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transaccional.
1. Mediante la API REST de Adobe Campaign Standard, envíe un evento a un token de registro (ABCDEF123456789), mediante una aplicación móvil (WeFlight), en Android (gcm), que contenga los datos de embarque.

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

"Hola Jane Green, el embarque acaba de empezar! Proceda a la Puerta B18."

## Notificaciones push transaccionales dirigidas a un perfil {#transactional-push-notifications-targeting-a-profile}

Puede enviar una notificación push de transacción a los perfiles de Adobe Campaign que se hayan suscrito a su aplicación móvil. Esta entrega puede contener campos de [personalización](../../designing/using/personalization.md#inserting-a-personalization-field) , como el nombre del destinatario.

En este caso, el evento debe contener algunos campos que permitan la reconciliación con un perfil de la base de datos de Adobe Campaign.

Al destinar perfiles, se envía una notificación push transaccional por aplicación móvil y por dispositivo. Por ejemplo, si un usuario de Adobe Campaign se ha suscrito a dos aplicaciones, este usuario recibirá dos notificaciones. Si un usuario se ha suscrito a la misma aplicación con dos dispositivos diferentes, recibirá una notificación en cada dispositivo.

Las aplicaciones móviles a las que se ha suscrito un perfil se muestran en la **[!UICONTROL Mobile App Subscriptions]** ficha de este perfil. Para acceder a esta ficha, seleccione un perfil y haga clic en el **[!UICONTROL Edit profile properties]** botón de la derecha.

![](assets/push_notif_subscriptions.png)

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Perfiles](../../audiences/using/creating-profiles.md).

### Envío de una notificación push transaccional dirigida a un perfil {#sending-a-transactional-push-notification-targeting-a-----------profile}

Por ejemplo, una empresa de aerolíneas desea enviar una última llamada de embarque a todos los usuarios de Adobe Campaign que se hayan suscrito a su aplicación móvil.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.

   <!--![](assets/message-center_push_message_profile.png)-->

1. Haga clic en el **[!UICONTROL Content]** bloque para modificar el título y el cuerpo del mensaje.

   A diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar su mensaje. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

   <!--![](assets/message-center_push_content_profile.png)-->

   Para obtener más información sobre la edición de contenido de notificaciones push. Consulte [Creación de una notificación](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transaccional.
1. Mediante la API REST de Adobe Campaign Standard, envíe un evento a un perfil.

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


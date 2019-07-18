---
title: Notificaciones push transaccionales
seo-title: Notificaciones push transaccionales
description: Notificaciones push transaccionales
seo-description: Obtenga información sobre cómo crear y publicar una notificación push de transacción.
page-status-flag: no activado nunca
uuid: ef 31 c 1 b 6-9 ef 8-42 e 3-b 49 d -72 f 9 eac 8 ea 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajes transaccionales
discoiquuid: e 645 d 4 b 9-001 f -47 d 9-8 a 0 f-b 4696 c 75 c 5 d 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Transactional push notifications{#transactional-push-notifications}

Puede utilizar Adobe Campaign para enviar notificaciones push transaccionales en dispositivos móviles iOS y Android. Estos mensajes se reciben en aplicaciones móviles que configuró en Adobe Campaign aprovechando el SDK de Mobile Cloud Mobile.

>[!NOTE]
>
>El canal push es opcional. Verifique su contrato de licencia. For more information on standard push notifications, see [Push notifications](../../channels/using/about-push-notifications.md).

Puede enviar dos tipos de notificaciones push transaccionales:

* Notificaciones push transaccionales dirigidas a un evento.
* Notificaciones push transaccionales de segmentación de perfiles desde la base de datos de Adobe Campaign.

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que el evento active enviar un mensaje de transacción, debe personalizar el mensaje, luego probarlo y publicarlo.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Transactional push notifications targeting an event {#transactional-push-notifications-targeting-an-event}

Puede enviar una notificación push de transacción anónima a todos los usuarios que hayan elegido recibir notificaciones desde su aplicación móvil.

En este caso, solo los datos contenidos en el evento propiamente dicho se utilizan para definir el objetivo de entrega. No se aprovechan los datos de la base de datos de perfil integrada de Adobe Campaign.

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

Por ejemplo, una empresa de aerolíneas desea invitar a los usuarios de la aplicación móvil a dirigirse a la portada relevante para ingresar.

La empresa enviará una notificación push de transacción por usuario (identificada con un distintivo de registro) usando una aplicación móvil a través de un único dispositivo.

1. Vaya al mensaje de transacción creado para editarlo. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   Puede insertar campos de personalización para agregar elementos que definió al crear el evento.

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Guarde los cambios y publique el mensaje. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Mediante la API REST de Adobe Campaign Standard, envíe un evento a un distintivo de registro (ABCDEF 123456789) usando una aplicación móvil (weflight), en Android (gcm), que contenga los datos de embarque.

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

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Si el distintivo de registro existe, el usuario correspondiente recibe una notificación push transaccional que incluye el siguiente contenido:

" Hello Jane Green, la internada acaba de empezar! Vaya a Gate B 18. "

## Transactional push notifications targeting a profile {#transactional-push-notifications-targeting-a-profile}

Puede enviar una notificación push de transacción a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil. This delivery can contain [personalization](../../designing/using/inserting-a-personalization-field.md) fields, such as the recipient's first name.

En este caso, el evento debe contener campos que permitan la reconciliación con un perfil de la base de datos de Adobe Campaign.

Al destinar perfiles, se envía una notificación push transaccional por aplicación móvil y por dispositivo. Por ejemplo, si un usuario de Adobe Campaign se ha suscrito a dos aplicaciones, este usuario recibirá dos notificaciones. Si un usuario se ha suscrito a la misma aplicación con dos dispositivos diferentes, este usuario recibirá una notificación en cada dispositivo.

The mobile applications a profile has subscribed to are listed in the **[!UICONTROL Mobile App Subscriptions]** tab of this profile. To access this tab, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right.

![](assets/push_notif_subscriptions.png)

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/creating-profiles.md).

### Sending a transactional push notification targeting a profile {#sending-a-transactional-push-notification-targeting-a-----------profile}

Por ejemplo, una empresa de aerolíneas desea enviar una última llamada para ingresar a todos los usuarios de Adobe Campaign que hayan suscrito a su aplicación móvil.

1. Vaya al mensaje de transacción creado para editarlo. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message_profile.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   A diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar el mensaje. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/message-center_push_content_profile.png)

   Para obtener más información sobre cómo editar un contenido de notificaciones Push. See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Guarde los cambios y publique el mensaje. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
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

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >No hay ningún campo de registro, aplicación ni plataforma push. En este ejemplo, la reconciliación se realiza con el campo de correo electrónico.


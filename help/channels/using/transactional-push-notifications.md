---
title: Notificaciones push transaccionales
description: Obtenga información sobre cómo enviar notificaciones push transaccionales con Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 4%

---

# Notificaciones push transaccionales{#transactional-push-notifications}

Puede utilizar Adobe Campaign para enviar notificaciones push transaccionales en dispositivos móviles iOS y Android. Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK de Experience Cloud Mobile.

>[!NOTE]
>
>El canal push es opcional. Compruebe el acuerdo de licencia. Para obtener más información sobre las notificaciones push estándar, consulte [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md).

Para poder enviar notificaciones push transaccionales, debe configurar Adobe Campaign en consecuencia. Consulte [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md).

Puede enviar dos tipos de notificaciones push transaccionales:

* [Notificaciones push transaccionales dirigidas a un evento](#transactional-push-notifications-targeting-an-event)
* [Perfiles de segmentación de notificaciones push transaccionales](#transactional-push-notifications-targeting-a-profile) de la base de datos de Adobe Campaign

## Notificaciones push transaccionales dirigidas a un evento {#transactional-push-notifications-targeting-an-event}

Puede utilizar Adobe Campaign para enviar **notificaciones push transaccionales anónimas a todos los usuarios** que han elegido recibir notificaciones de su aplicación móvil.

En este caso, solo **los datos contenidos en el propio evento se utilizan para definir el destinatario del envío**. No se aprovechan los datos de la base de datos de perfiles integrada de Adobe Campaign.

### Configuración de una notificación push transaccional basada en eventos {#configuring-event-based-transactional-push-notification}

Para enviar una notificación push transaccional a todos los usuarios que se han suscrito para recibir notificaciones de su aplicación móvil, primero debe crear y configurar un evento dirigido a los datos contenidos en el propio evento.

>[!NOTE]
>
>Puede seguir personalizando el contenido de una notificación push transaccional basada en eventos mediante [atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (datos del evento) y [enriquecimiento de eventos](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (datos de la base de datos de Campaign). Consulte [el ejemplo siguiente](#sending-event-based-transactional-push-notification).

El evento debe contener los tres elementos siguientes:

* A **token de registro**, que es el ID de usuario de una aplicación móvil y un dispositivo. Es posible que no se corresponda con ningún perfil de la base de datos de Adobe Campaign.
* A **nombre de aplicación móvil** (uno para todos los dispositivos: Android y iOS). Este es el ID de la aplicación móvil configurada en Adobe Campaign que se utilizará para recibir notificaciones push en los dispositivos de los usuarios. Para obtener más información, consulte [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md).
* A **plataforma push** (gcm para Android o apns para iOS).

Para configurar el evento, siga los pasos a continuación:

1. Al crear la configuración de evento, seleccione **[!UICONTROL Push notification]** y el canal **[!UICONTROL Real-time event]** dimensión objetivo (consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Añada campos al evento. Esto le permitirá personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). En este ejemplo, defina los campos &quot;gateNumber&quot;, &quot;lastname&quot; y &quot;firstname&quot;.
1. También puede enriquecer el contenido del mensaje. Para ello, añada campos de la tabla que vinculó a la configuración de evento (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [Previsualización y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Al previsualizar el evento, la API de REST contiene los atributos &quot;registrationToken&quot;, &quot;application&quot; y &quot;pushPlatform&quot; que se utilizan para realizar el envío.

   ![](assets/message-center_push_api.png)

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Ahora puede modificar y publicar el mensaje que acaba de crear (consulte [esta sección](#sending-event-based-transactional-push-notification)).

1. Integre el evento en su sitio web (consulte [Integración del activador del evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Envío de una notificación push transaccional basada en eventos {#sending-event-based-transactional-push-notification}

Por ejemplo, una compañía aérea desea invitar a los usuarios de su aplicación móvil a dirigirse a la puerta correspondiente para abordar.

La empresa enviará una notificación push transaccional por usuario (identificado con un token de registro), utilizando una aplicación móvil, a través de un solo dispositivo.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Acceso a mensajes transaccionales](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Haga clic en **[!UICONTROL Content]** para modificar el título y el cuerpo del mensaje.

1. Puede insertar campos de personalización para añadir elementos que definió al crear el evento (consulte [Definición de los atributos del evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Para buscar estos campos, haga clic en el lápiz situado junto a un elemento y haga clic en **[!UICONTROL Insert personalization field]** y seleccione **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obtener más información sobre la edición de contenido de notificaciones push, consulte [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. También puede enriquecer el contenido del mensaje transaccional si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Con la API de REST de Adobe Campaign Standard, envíe un evento a un token de registro (ABCDEF123456789) mediante una aplicación móvil (WeFlight) en Android (gcm) que contenga los datos de embarque:

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

   Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte [Integración del activador del evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

Si existe el token de registro, el usuario correspondiente recibe una notificación push transaccional que incluye el siguiente contenido:

*&quot;Hola Jane Green, el embarque acaba de empezar! Por favor, diríjase a la puerta B18&quot;.*

## Notificaciones push transaccionales dirigidas a un perfil {#transactional-push-notifications-targeting-a-profile}

Puede enviar una notificación push transaccional **a los perfiles de Adobe Campaign que se han suscrito a su aplicación móvil**. Esta entrega puede contener [campos de personalización](../../designing/using/personalization.md#inserting-a-personalization-field), como el nombre del destinatario, recuperado directamente de la base de datos de Adobe Campaign.

En este caso, el evento debe contener algunos campos **permitir la reconciliación con un perfil de la base de datos de Adobe Campaign**.

Al segmentar perfiles, se envía una notificación push transaccional por aplicación móvil y por dispositivo. Por ejemplo, si un usuario de Adobe Campaign se ha suscrito a dos aplicaciones, este usuario recibe dos notificaciones. Si un usuario se ha suscrito a la misma aplicación con dos dispositivos diferentes, este usuario recibirá una notificación en cada dispositivo.

Las aplicaciones móviles a las que se ha suscrito un perfil se enumeran en la **[!UICONTROL Mobile App Subscriptions]** de este perfil. Para acceder a esta pestaña, seleccione un perfil y haga clic en **[!UICONTROL Edit profile properties]** botón a la derecha.

![](assets/push_notif_subscriptions.png)

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Acerca de los perfiles](../../audiences/using/about-profiles.md).

### Configuración de una notificación push transaccional basada en perfiles {#configuring-profile-based-transactional-push-notification}

Para enviar una notificación push transaccional a los perfiles de Adobe Campaign que se han suscrito a su aplicación móvil, primero debe crear y configurar un evento dirigido a la base de datos de Adobe Campaign.

1. Al crear la configuración de evento, seleccione **[!UICONTROL Push notification]** y el canal **[!UICONTROL Profile]** dimensión objetivo (consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   De forma predeterminada, la notificación push transaccional se envía a todas las aplicaciones móviles a las que se han suscrito los destinatarios. Para enviar la notificación push a una aplicación móvil específica, selecciónela en la lista. Las demás aplicaciones móviles se segmentarán con el mensaje, pero se excluirán del envío.

   ![](assets/message-center_push_appfilter.png)

1. Añada campos al evento si desea personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Debe añadir al menos un campo para crear un enriquecimiento. No es necesario crear otros campos, como **Nombre** y **Apellidos** al igual que podrá utilizar campos de personalización de la base de datos de Adobe Campaign.

1. Cree un enriquecimiento para vincular el evento a la **[!UICONTROL Profile]** recurso (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) y seleccione este enriquecimiento como **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Este paso es obligatorio para eventos basados en perfiles.

1. [Previsualización y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Al obtener una vista previa del evento, la API de REST no contiene un atributo que especifique el token de registro, el nombre de la aplicación y la plataforma push, ya que se recuperarán del **[!UICONTROL Profile]** recurso.

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Ahora puede modificar y publicar el mensaje que acaba de crear (consulte [esta sección](#sending-profile-based-transactional-push-notification)).

1. Integre el evento en su sitio web (consulte [Integración del activador del evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Envío de una notificación push transaccional basada en perfiles {#sending-profile-based-transactional-push-notification}

Por ejemplo, una compañía aérea quiere enviar una última llamada para el embarque a todos los usuarios de Adobe Campaign que se hayan suscrito a su aplicación móvil.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Acceso a mensajes transaccionales](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Haga clic en **[!UICONTROL Content]** para modificar el título y el cuerpo del mensaje.

   A diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar su mensaje. Consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).

   Para obtener más información sobre la edición de contenido de notificaciones push, consulte [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Con la API de REST de Adobe Campaign Standard, envíe un evento a un perfil:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte [Integración del activador del evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

El usuario correspondiente recibe una notificación push transaccional que incluye todos los elementos de personalización recuperados de la base de datos de Adobe Campaign.

>[!NOTE]
>
>No hay campos de token de registro, aplicación y plataforma push. En este ejemplo, la reconciliación se realiza con el campo de correo electrónico.

## Modificación de la asignación de destino en una notificación push transaccional {#change-target-mapping}

Las notificaciones push transaccionales utilizan un específico [asignación de destino](../../administration/using/target-mappings-in-campaign.md) que contiene la configuración técnica necesaria para realizar este tipo de envíos.

Para cambiar esta asignación de destino, siga los pasos a continuación:

1. En la lista de mensaje transaccional, seleccione una notificación push.

1. En el panel del mensaje, haga clic en **[!UICONTROL Edit properties]** botón.

   ![](assets/message-center_push_edit.png)

1. Expanda el **[!UICONTROL Advanced parameters]** sección.

1. Haga clic en **[!UICONTROL Select a 'Target mapping' element]**.

   ![](assets/message-center_push_target-mapping.png)

1. Seleccione una asignación de destino de la lista.

   >[!NOTE]
   >
   >Para obtener un tiempo y un rendimiento óptimos de preparación de envíos al enviar **basado en perfiles** notificaciones push transaccionales, utilice el **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** asignación de destino.

   ![](assets/message-center_push_target-mapping_change.png)

1. Confirme el cambio y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

   >[!IMPORTANT]
   >
   >Debe volver a publicar el mensaje para que el cambio sea efectivo; de lo contrario, se seguirá utilizando la asignación de destino anterior.



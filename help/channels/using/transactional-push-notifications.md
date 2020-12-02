---
solution: Campaign Standard
product: campaign
title: Notificaciones push transaccionales
description: Aprenda a crear y publicar una notificación push transaccional         notificación.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 8%

---


# Notificaciones push transaccionales{#transactional-push-notifications}

Puede utilizar Adobe Campaign para enviar notificaciones push transaccionales en dispositivos móviles iOS y Android. Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK para móviles de Experience Cloud.

>[!NOTE]
>
>El canal push es opcional. Compruebe el acuerdo de licencia. Para obtener más información sobre las notificaciones push estándar, consulte [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md).

Para poder enviar notificaciones push transaccionales, debe configurar Adobe Campaign en consecuencia. Consulte [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md).

Puede enviar dos tipos de notificaciones push de transacciones:

* [Notificaciones push transaccionales dirigidas a un evento](#transactional-push-notifications-targeting-an-event)
* [Notificaciones push transaccionales ](#transactional-push-notifications-targeting-a-profile) perfiles de objetivo de la base de datos de Adobe Campaign

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de seguridad **[!UICONTROL Administrators (all units)]**. Para obtener más información sobre esto, consulte [Administración de usuarios](../../administration/using/users-management.md#functional-administrators).

## Notificaciones push transaccionales dirigidas a un evento {#transactional-push-notifications-targeting-an-event}

Puede utilizar Adobe Campaign para enviar **notificaciones push de transacciones anónimas a todos los usuarios** que hayan adhesión para recibir notificaciones de su aplicación móvil.

En este caso, sólo **los datos contenidos en el propio evento se utilizan para definir el destinatario de envío**. No se aprovecha ningún dato de la base de datos de perfil integrada de Adobe Campaign.

### Configuración de una notificación push transaccional basada en eventos {#configuring-event-based-transactional-push-notification}

Para enviar una notificación push de transacción a todos los usuarios que hayan adhesión para recibir notificaciones desde la aplicación móvil, primero debe crear y configurar un evento que dirija los datos contenidos en el propio evento.

>[!NOTE]
>
>Aún puede personalizar el contenido de una notificación push de transacciones basada en evento mediante [atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (datos del evento) y [enriquecimiento de evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (datos de la base de datos de Campañas). Consulte [el ejemplo siguiente](#sending-event-based-transactional-push-notification).

El evento debe contener los tres elementos siguientes:

* Un **token de registro**, que es el ID de usuario para una aplicación móvil y un dispositivo. Puede que no corresponda a ningún perfil de la base de datos de Adobe Campaign.
* Un **nombre de aplicación móvil** (uno para todos los dispositivos: Android e iOS). ID de la aplicación móvil configurada en Adobe Campaign que se utilizará para recibir notificaciones push en los dispositivos de los usuarios. Para obtener más información sobre esto, consulte [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md).
* Una **plataforma push** (&quot;gcm&quot; para Android o &quot;apns&quot; para iOS).

Para configurar el evento, siga los pasos a continuación:

1. Al crear la configuración de evento, seleccione el canal **[!UICONTROL Mobile application]** y la dimensión de segmentación **[!UICONTROL Real-time event]** (consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Añada los campos al evento. Esto le permitirá personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). En este ejemplo, defina los campos &quot;gateNumber&quot;, &quot;lastname&quot; y &quot;firstname&quot;.
1. Enriquecer el contenido de mensaje transaccional si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign.

1. [Previsualización y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Al obtener una vista previa del evento, la API de REST contiene los atributos &quot;registrationToken&quot;, &quot;application&quot; y &quot;pushPlatform&quot; que se utilizarán para el destinatario del envío.

   ![](assets/message-center_push_api.png)

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Ahora puede modificar y publicar el mensaje que acaba de crear (consulte [esta sección](#sending-event-based-transactional-push-notification)).

1. Integre el evento en su sitio web (consulte Integración del activador de evento(../../channels/using/getting-started-with-transactional-msg.md#integration-evento-desencadenador)).

### Envío de una notificación push transaccional basada en eventos {#sending-event-based-transactional-push-notification}

Por ejemplo, una compañía de aerolíneas desea invitar a los usuarios de su aplicación móvil a que procedan a la puerta de embarque correspondiente.

La compañía enviará una notificación push transaccional por usuario (identificada con un token de registro), mediante una aplicación móvil, a través de un solo dispositivo.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Acceso a mensajes transaccionales](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Haga clic en el bloque **[!UICONTROL Content]** para modificar el título y el cuerpo del mensaje.

1. Puede insertar campos de personalización para agregar elementos que definió al crear el evento (consulte [Definición de atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Para encontrar estos campos, haga clic en el lápiz situado junto a un elemento, haga clic en **[!UICONTROL Insert personalization field]** y seleccione **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obtener más información sobre la edición de contenido de una notificación push, consulte [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. También puede enriquecer el contenido de mensaje transaccional si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Mediante la API de Adobe Campaign Standard REST, envíe un evento a un token de registro (ABCDEF123456789), mediante una aplicación móvil (WeFlight), en Android (gcm), que contenga los datos de embarque:

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

   Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte Integración del activador de eventos (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-desencadenador).

Si existe el token de registro, el usuario correspondiente recibe una notificación push transaccional que incluye el siguiente contenido:

*&quot;Hola Jane Green, el embarque acaba de empezar! Vaya a la Puerta B18.&quot;*

## Notificaciones push transaccionales dirigidas a un perfil {#transactional-push-notifications-targeting-a-profile}

Puede enviar una notificación push transaccional **a los perfiles de Adobe Campaign que se hayan suscrito a su aplicación móvil**. Este envío puede contener [campos de personalización](../../designing/using/personalization.md#inserting-a-personalization-field), como el nombre del destinatario, recuperados directamente de la base de datos de Adobe Campaign.

En este caso, el evento debe contener algunos campos **que permitan la reconciliación con un perfil de la base de datos de Adobe Campaign**.

Al destinar perfiles, se envía una notificación push transaccional por aplicación móvil y por dispositivo. Por ejemplo, si un usuario de Adobe Campaign se ha suscrito a dos aplicaciones, este usuario recibirá dos notificaciones. Si un usuario se ha suscrito a la misma aplicación con dos dispositivos diferentes, este usuario recibirá una notificación en cada dispositivo.

Las aplicaciones móviles a las que se ha suscrito un perfil se enumeran en la ficha **[!UICONTROL Mobile App Subscriptions]** de este perfil. Para acceder a esta ficha, seleccione un perfil y haga clic en el botón **[!UICONTROL Edit profile properties]** de la derecha.

![](assets/push_notif_subscriptions.png)

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Acerca de los perfiles](../../audiences/using/about-profiles.md).

### Configuración de una notificación push transaccional basada en perfiles {#configuring-profile-based-transactional-push-notification}

Para enviar una notificación push de transacción a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil, primero debe crear y configurar un evento que segmente la base de datos de Adobe Campaign.

1. Al crear la configuración de evento, seleccione el canal **[!UICONTROL Mobile application]** y la dimensión de segmentación **[!UICONTROL Profile]** (consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   De forma predeterminada, la notificación push de transacción se enviará a todas las aplicaciones móviles a las que se hayan suscrito los destinatarios. Para enviar la notificación push a una aplicación móvil específica, selecciónela en la lista. Las demás aplicaciones móviles serán segmentadas por el mensaje pero se excluirán del envío.

   ![](assets/message-center_push_appfilter.png)

1. Añada los campos al evento si desea personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Debe agregar al menos un campo para crear un enriquecimiento. No es necesario crear otros campos, como **Nombre** y **Apellido**, ya que podrá utilizar campos de personalización de la base de datos de Adobe Campaign.

1. Cree un enriquecimiento para vincular el evento al recurso **[!UICONTROL Profile]** (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)). La creación de un enriquecimiento es obligatoria cuando se utiliza una dimensión de segmentación **[!UICONTROL Profile]**.
1. [Previsualización y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Al obtener una vista previa del evento, la API de REST no contiene ningún atributo que especifique el token de registro, el nombre de la aplicación y la plataforma push, ya que se recuperarán del recurso **[!UICONTROL Profile]**.

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Ahora puede modificar y publicar el mensaje que acaba de crear (consulte [esta sección](#sending-profile-based-transactional-push-notification)).

1. Integre el evento en su sitio web (consulte Integración del activador de evento(../../channels/using/getting-started-with-transactional-msg.md#integration-evento-desencadenador)).

### Envío de una notificación push transaccional basada en perfiles {#sending-profile-based-transactional-push-notification}

Por ejemplo, una compañía de aerolíneas desea enviar una última llamada para el embarque a todos los usuarios de Adobe Campaign que se hayan suscrito a su aplicación móvil.

1. Vaya al mensaje transaccional que se creó para editarlo. Consulte [Acceso a mensajes transaccionales](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Haga clic en el bloque **[!UICONTROL Content]** para modificar el título y el cuerpo del mensaje.

   A diferencia de las configuraciones basadas en eventos en tiempo real, usted tiene acceso directo a toda la información de perfil para personalizar su mensaje. Consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).

   Para obtener más información sobre la edición de contenido de una notificación push, consulte [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Mediante la API de Adobe Campaign Standard REST, envíe un evento a un perfil:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Para obtener más información sobre la integración del activador de un evento en un sistema externo, consulte Integración del activador de eventos (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-desencadenador).

El usuario correspondiente recibe una notificación push de transacción que incluye todos los elementos de personalización recuperados de la base de datos de Adobe Campaign.

>[!NOTE]
>
>No hay campos de token de registro, aplicación y plataforma push. En este ejemplo, la reconciliación se realiza con el campo de correo electrónico.

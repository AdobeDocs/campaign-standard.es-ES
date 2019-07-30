---
title: Configuración de mensajes transaccionales
seo-title: Configuración de mensajes transaccionales
description: Configuración de mensajes transaccionales
seo-description: Descubra cómo configurar mensajes transaccionales.
page-status-flag: no activado nunca
uuid: 4 caeadbe-f 4 a 7-43 ce -986 d-e 99 fa 9 ca 0 d 0 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: configurar canales
discoiquuid: 3 f 968556-e 774-43 dc-a 0 b 8-7188 d 7665 fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e2f947cce39ce08f233292d34cb4440aa48a2b5

---


# Configuring transactional messaging{#configuring-transactional-messaging}

Para enviar un mensaje de transacción con Adobe Campaign, primero debe describir la estructura de los datos del evento.

Event configuration must be performed by an **administrator** by following the steps below:

La configuración puede variar según el tipo de mensaje transaccional que desee enviar. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

Una vez publicada el evento, se crea automáticamente el correspondiente mensaje transaccional. For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

Comience creando el evento correspondiente a sus necesidades.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** El campo es obligatorio y debe comenzar con el prefijo "EVT". If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >El ID no debe exceder los 64 caracteres, incluido el prefijo EVT.

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >Solo se puede usar un canal para cada configuración de evento. Una vez creado el evento, no podrá cambiar el canal.

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   Los mensajes transaccionales basados en eventos se dirigen a los datos contenidos en el mismo evento, mientras que los mensajes transaccionales basados en perfiles se dirigen a los datos contenidos en la base de datos de Adobe Campaign. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

In the **[!UICONTROL Fields]** section, define the attributes that will be integrated into the event content and will then be able to be used to personalize the transactional message.

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. Esto sólo se aplica a mensajes transaccionales de eventos. Una vez publicada el evento, los pasos para editar el contenido de un mensaje transaccional multilingüe son los mismos que para un correo electrónico estándar multilingüe. See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

Puede agregar al contenido del evento una colección de elementos, cada elemento que incluya varios atributos.

Esta colección se puede utilizar en un correo electrónico de transacción para agregar listas de productos al contenido del mensaje, por ejemplo una lista de productos, con el precio, el número de referencia, la cantidad, etc. para cada producto de la lista.

1. In the **[!UICONTROL Collections]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_collection_create.png)

1. Agregue una etiqueta y un ID para la colección.
1. Agregue todos los campos que desee mostrar en el mensaje de transacción para cada producto de la lista.

   En este ejemplo, agregamos los campos siguientes:

   ![](assets/message-center_collection_fields.png)

Una vez que el evento y el mensaje se publican, podrá utilizar esta colección en su mensaje de transacción.

Esta es la vista previa de la API para este ejemplo:

![](assets/message-center_collection_api-preview.png)

**Temas relacionados:**

* [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [Uso de listados de productos en un mensaje de transacción](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriching the transactional message content {#enriching-the-transactional-message-content}

El aumento del contenido de mensajes transaccionales con información de la base de datos de Adobe Campaign permite personalizar los mensajes. Desde el último nombre o ID de CRM de cada destinatario, por ejemplo, puede recuperar datos como su dirección o fecha de nacimiento o cualquier otro campo personalizado agregado en la tabla Perfil para personalizar la información que se les envía.

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

Esta información también se puede almacenar en nuevos recursos. In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. In the **[!UICONTROL Enrichment]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_addenrichment.png)

1. Seleccione el recurso con el que desea vincular el mensaje. In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. In the **[!UICONTROL Targeting enrichment]** section, select the enrichment that will be used as the message target during the delivery execution. In this example, select **[!UICONTROL Profile]**. La selección de una enriquecimiento de objetivo es obligatoria para los eventos basados en perfiles.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**Temas relacionados:**

* [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).
* [Personalización de un mensaje de transacción](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Previewing and publishing the event {#previewing-and-publishing-the-event}

Antes de poder utilizar el evento, debe previsualizarlo y publicarlo.

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. Una vez publicada el evento, este botón también permite ver una vista previa de la API en producción. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La API de REST varía según el canal seleccionado y la dimensión de objetivo seleccionada. For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. Para ver los registros de publicaciones, seleccione la ficha correspondiente.

   ![](assets/message-center_logs.png)

   También puede consultar las publicaciones anteriores seleccionando la ficha.

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que este evento active el envío de un mensaje de transacción, debe modificar y publicar el mensaje que acaba de crear. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Puede acceder al mensaje de transacción que se creó directamente desde el vínculo situado en el área izquierda.

![](assets/message-center_messagegeneration.png)

También debe integrar este evento desencadenador en el sitio Web. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

The **[!UICONTROL Unpublish]** button lets you cancel the publication of the event, which deletes from the REST API the resource corresponding to the event that you previously created. Ahora, incluso si el evento se activa a través del sitio web, los mensajes correspondientes no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si ya ha publicado el mensaje transaccional correspondiente, también se cancelará la publicación de mensaje de transacción. See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

Una vez creado un evento, tendrá que integrar el activador de este evento en el sitio web.

In the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart. Para ello, el desarrollador web de su sitio web debe utilizar la API de REST de Adobe Campaign Standard.

See the [REST API Documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Transactional event specific configurations {#transactional-event-specific-configurations}

La configuración del evento transaccional puede variar según el tipo de mensaje de transacción que desee enviar (evento o perfil) y el canal que se va a utilizar.

Las secciones siguientes detallan qué configuración específica debe configurarse según el mensaje transaccional deseado. For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

Para enviar un mensaje transaccional basado en eventos, primero debe crear y configurar un evento para los datos contenidos en el mismo evento.

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Los mensajes transaccionales basados en eventos deben utilizar solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización de contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje de transacción mediante la información de la base de datos de Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene un atributo que especifica la dirección de correo electrónico o el teléfono móvil según el canal seleccionado.

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

Para enviar un mensaje de transacción basado en perfiles, primero debe crear y configurar los datos de segmentación de eventos contenidos en la base de datos de Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). Debe agregar al menos un campo para crear un enriquecimiento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

Para poder enviar notificaciones push transaccionales, debe configurar Adobe Campaign en consecuencia. See [Push configuration](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Para enviar una notificación push de transacción anónima a todos los usuarios que han elegido recibir notificaciones desde su aplicación móvil, primero debe crear y configurar un evento para los datos contenidos en el mismo evento. Los pasos correspondientes se presentan a continuación.

El evento debe contener los tres elementos siguientes:

* A **registration token**, which is the user ID for one mobile application and one device. Puede no corresponderse con ningún perfil de la base de datos de Adobe Campaign.
* A **mobile application name** (one for all devices - Android and iOS). Es el ID de la aplicación móvil configurada en Adobe Campaign que se utilizará para recibir notificaciones push en los dispositivos de los usuarios. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* A **push platform** ("gcm" for Android or "apns" for iOS).

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Los mensajes transaccionales basados en eventos deben utilizar solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización de contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje de transacción mediante la información de la base de datos de Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene los atributos "registrationtoken", "application" y "pushplatform" que se utilizarán para dirigir la entrega.

   ![](assets/message-center_push_api.png)

   Una vez publicada el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

Para enviar una notificación push de transacción a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil, primero debe crear y configurar un evento para la base de datos de Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   De forma predeterminada, la notificación push transaccional se enviará a todas las aplicaciones móviles a las que se suscribieron los destinatarios. Para enviar la notificación Push a una aplicación móvil específica, selecciónela en la lista. El mensaje será dirigido a otras aplicaciones móviles, pero se excluirá del envío.

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Debe agregar al menos un campo para crear un enriquecimiento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   Una vez publicada el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

Un mensaje de seguimiento es una plantilla de envío de marketing predefinida que se puede utilizar en un flujo de trabajo para enviar mensajes a los destinatarios de un mensaje de transacción específico. For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. Utilice la misma configuración de evento que creó para enviar un mensaje transaccional de evento. See [Event-based transactional messages](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional y una plantilla de envío de seguimiento vinculada al nuevo evento. For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

En este ejemplo, queremos configurar un evento para enviar mensajes de confirmación después de cada compra en nuestro sitio web con los siguientes requisitos previos:

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. De esta forma, podrá recuperar información de este recurso para enriquecer el contenido del mensaje.

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Defina los atributos que estarán disponibles para personalizar el mensaje transaccional. In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).


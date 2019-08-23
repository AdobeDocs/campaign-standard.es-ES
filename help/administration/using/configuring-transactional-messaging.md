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
source-git-commit: 8800562922e68d33cca93cd838c294198b630684

---


# Configuración de mensajes transaccionales{#configuring-transactional-messaging}

Para enviar un mensaje de transacción con Adobe Campaign, primero debe describir la estructura de los datos del evento.

La configuración del evento debe realizarla un **administrador** siguiendo los pasos a continuación:

La configuración puede variar según el tipo de mensaje transaccional que desee enviar. Para obtener más información sobre esto, consulte Configuraciones específicas del evento [Transaccional.](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

Una vez publicada el evento, se crea automáticamente el correspondiente mensaje transaccional. Para obtener más información sobre los mensajes transaccionales, consulte [esta página](../../channels/using/about-transactional-messaging.md).

## Creación de un evento {#creating-an-event}

Comience creando el evento correspondiente a sus necesidades.

1. Haga clic en **[!UICONTROL Adobe Campaign]** el logotipo, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Haga clic en **[!UICONTROL Create]** el botón.
1. Proporcione a **[!UICONTROL Label]** y un **[!UICONTROL ID]** evento. **[!UICONTROL ID]** El campo es obligatorio y debe comenzar con el prefijo "EVT". Si no utiliza este prefijo, se agrega automáticamente una vez que se hace clic **[!UICONTROL Create]** en él.

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >El ID no debe exceder los 64 caracteres, incluido el prefijo EVT.

1. Seleccione el canal que se utilizará para enviar los mensajes transaccionales **[!UICONTROL Email]** o **[!UICONTROL Mobile (SMS)]****[!UICONTROL Mobile application]** (notificación push).

   >[!NOTE]
   >
   >Solo se puede usar un canal para cada configuración de evento. Una vez creado el evento, no podrá cambiar el canal.

1. Seleccione la dimensión de objetivo correspondiente a la configuración de evento deseada y haga clic **[!UICONTROL Create]** en.

   Los mensajes transaccionales basados en eventos se dirigen a los datos contenidos en el mismo evento, mientras que los mensajes transaccionales basados en perfiles se dirigen a los datos contenidos en la base de datos de Adobe Campaign. Para obtener más información sobre esto, consulte Configuraciones específicas del evento [Transaccional](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Definición de los atributos de evento {#defining-the-event-attributes}

En **[!UICONTROL Fields]** la sección, defina los atributos que se integrarán en el contenido del evento y luego podrá utilizarse para personalizar el mensaje transaccional.

Los pasos para agregar y modificar campos son los mismos que para los recursos [personalizados](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Si desea crear un mensaje transaccional multilingüe, defina un atributo de evento adicional con **[!UICONTROL AC_language]** el ID. Esto sólo se aplica a mensajes transaccionales de eventos. Una vez publicada el evento, los pasos para editar el contenido de un mensaje transaccional multilingüe son los mismos que para un correo electrónico estándar multilingüe. Consulte [Creación de un correo electrónico](../../channels/using/creating-a-multilingual-email.md)multilingües.

## Definición de colecciones de datos {#defining-data-collections}

Puede agregar al contenido del evento una colección de elementos, cada elemento que incluya varios atributos.

Esta colección se puede utilizar en un correo electrónico de transacción para agregar listas de productos al contenido del mensaje, por ejemplo una lista de productos, con el precio, el número de referencia, la cantidad, etc. para cada producto de la lista.

1. En **[!UICONTROL Collections]** la sección, haga clic en **[!UICONTROL Create element]** el botón.

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

## Enriquecimiento del contenido de mensajes transaccionales {#enriching-the-transactional-message-content}

El aumento del contenido de mensajes transaccionales con información de la base de datos de Adobe Campaign permite personalizar los mensajes. Desde el último nombre o ID de CRM de cada destinatario, por ejemplo, puede recuperar datos como su dirección o fecha de nacimiento o cualquier otro campo personalizado agregado en la tabla Perfil para personalizar la información que se les envía.

Es posible enriquecer el contenido de mensajes transaccionales con información de recursos ampliados **[!UICONTROL Profile]** o **[!UICONTROL Service]** recursos.

Esta información también se puede almacenar en nuevos recursos. En ese caso, el recurso debe estar vinculado al **[!UICONTROL Profile]** o **[!UICONTROL Service]** recursos directamente o a través de otra tabla. Por ejemplo, en la siguiente configuración, es posible enriquecer el contenido de mensajes transaccionales con información del **[!UICONTROL Product]** recurso como la categoría del producto o el ID, si **[!UICONTROL Product]** el recurso está vinculado al **[!UICONTROL Profile]** recurso.

![](assets/message-center_usecaseschema.png)

Para obtener más información sobre la creación y publicación de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. En **[!UICONTROL Enrichment]** la sección, haga clic en **[!UICONTROL Create element]** el botón.

   ![](assets/message-center_addenrichment.png)

1. Seleccione el recurso con el que desea vincular el mensaje. En este caso, elija **[!UICONTROL Profile]** el recurso.

   ![](assets/message-center_new-enrichment.png)

1. Utilice **[!UICONTROL Create element]** el botón para vincular un campo del recurso seleccionado a uno de los campos que agregó anteriormente al evento (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. En este ejemplo, conciliamos los **[!UICONTROL Last name]** campos y **[!UICONTROL First name]** los campos con los campos correspondientes del **[!UICONTROL Profile]** recurso.

   ![](assets/message-center_enrichment-join-fields.png)

1. En la **[!UICONTROL Targeting enrichment]** sección, seleccione la característica que se utilizará como destino del mensaje durante la ejecución de la entrega. En este ejemplo, seleccione **[!UICONTROL Profile]**. La selección de una enriquecimiento de objetivo es obligatoria para los eventos basados en perfiles.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Una vez que el evento y el mensaje se publican, el vínculo con **[!UICONTROL Profile]** el recurso le permitirá enriquecer el contenido del mensaje de transacción.

**Temas relacionados:**

* [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).
* [Personalización de un mensaje de transacción](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Vista previa y publicación del evento {#previewing-and-publishing-the-event}

Antes de poder utilizar el evento, debe previsualizarlo y publicarlo.

1. Haga clic en **[!UICONTROL API preview]** el botón para ver una simulación de la API de REST que utilizará el desarrollador del sitio web antes de publicarla. Una vez publicada el evento, este botón también permite ver una vista previa de la API en producción. Consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La API de REST varía según el canal seleccionado y la dimensión de objetivo seleccionada. Para obtener más detalles sobre las diversas configuraciones, consulte Configuraciones específicas del evento [Transaccional](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Haga clic en **[!UICONTROL Publish]** para iniciar la publicación.

   ![](assets/message-center_pub.png)

1. Para ver los registros de publicaciones, seleccione la ficha correspondiente.

   ![](assets/message-center_logs.png)

   También puede consultar las publicaciones anteriores seleccionando la ficha.

>[!NOTE]
>
>Cada vez que modifique el evento, debe hacer clic **[!UICONTROL Publish]** de nuevo para generar la API de REST actualizada que utilizará el desarrollador del sitio web.

Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que este evento active el envío de un mensaje de transacción, debe modificar y publicar el mensaje que acaba de crear. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

Puede acceder al mensaje de transacción que se creó directamente desde el vínculo situado en el área izquierda.

![](assets/message-center_messagegeneration.png)

También debe integrar este evento desencadenador en el sitio Web. Consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Cancelación de la publicación de un evento {#unpublishing-an-event}

El **[!UICONTROL Unpublish]** botón permite cancelar la publicación del evento, que elimina de la API de REST el recurso correspondiente al evento que ha creado anteriormente. Ahora, incluso si el evento se activa a través del sitio web, los mensajes correspondientes no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si ya ha publicado el mensaje transaccional correspondiente, también se cancelará la publicación de mensaje de transacción. Consulte [Cancelación de la publicación de un mensaje de transacción](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Haga clic en **[!UICONTROL Publish]** el botón para generar una nueva API de REST.

## Integración del activador del evento en un sitio web {#integrating-the-triggering-of-the-event-in-a-website}

Una vez creado un evento, tendrá que integrar el activador de este evento en el sitio web.

En el ejemplo descrito en la sección [del principio](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) operativo de mensajes transaccionales, desea que se active el evento "Abandono del carro de compras" cada vez que uno de los clientes abandone el sitio Web antes de comprar los productos en su carro de compras. Para ello, el desarrollador web de su sitio web debe utilizar la API de REST de Adobe Campaign Standard.

Consulte la Documentación de API [de REST](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Configuraciones específicas del evento transaccional {#transactional-event-specific-configurations}

La configuración del evento transaccional puede variar según el tipo de mensaje de transacción que desee enviar (evento o perfil) y el canal que se va a utilizar.

Las secciones siguientes detallan qué configuración específica debe configurarse según el mensaje transaccional deseado. Para obtener más información sobre los pasos generales para configurar un evento, consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Mensajes transaccionales basados en eventos {#event-based-transactional-messages}

Para enviar un mensaje transaccional basado en eventos, primero debe crear y configurar un evento para los datos contenidos en el mismo evento.
Para obtener más información, consulte [Interacción con mensajes transaccionales](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Al crear la configuración del evento, seleccione la dimensión **[!UICONTROL Real-time event]** de objetivo (consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Agregue campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enriquezca el contenido de mensajes transaccionales si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Los mensajes transaccionales basados en eventos deben utilizar solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización de contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje de transacción mediante la información de la base de datos de Adobe Campaign.

1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene un atributo que especifica la dirección de correo electrónico o el teléfono móvil según el canal seleccionado.

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que el evento active enviar un mensaje de transacción, debe modificar y publicar el mensaje que acaba de crear, consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

1. Integre el evento en el sitio web (consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Mensajes transaccionales basados en perfiles {#profile-based-transactional-messages}

Para enviar un mensaje de transacción basado en perfiles, primero debe crear y configurar los datos de segmentación de eventos contenidos en la base de datos de Adobe Campaign.

1. Al crear la configuración del evento, seleccione la dimensión **[!UICONTROL Profile event]** de objetivo (consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Agregue campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). Debe agregar al menos un campo para crear un enriquecimiento. No es necesario crear otros campos como **Nombre** y **Apellido** , ya que podrá utilizar campos de personalización desde la base de datos de Adobe Campaign.
1. Cree una enriquecimiento para vincular el evento al **[!UICONTROL Profile]** recurso (consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). La creación de un enriquecimiento es obligatoria al usar una dimensión **[!UICONTROL Profile]** de objetivo.
1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST no contiene ningún atributo que especifique la dirección de correo electrónico o el teléfono móvil, ya que se recuperará del **[!UICONTROL Profile]** recurso.

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que el evento active enviar un mensaje de transacción, debe modificar y publicar el mensaje que acaba de crear, consulte [Envío de un mensaje transaccional de perfil](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integre el evento en el sitio web (consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Notificaciones push transaccionales basadas en eventos {#event-based-transactional-push-notifications}

Para poder enviar notificaciones push transaccionales, debe configurar Adobe Campaign en consecuencia. Consulte [Configuración push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Para enviar una notificación push de transacción anónima a todos los usuarios que han elegido recibir notificaciones desde su aplicación móvil, primero debe crear y configurar un evento para los datos contenidos en el mismo evento. Los pasos correspondientes se presentan a continuación.

El evento debe contener los tres elementos siguientes:

* Un distintivo **de registro**, que es el ID de usuario de una aplicación móvil y un dispositivo. Puede no corresponderse con ningún perfil de la base de datos de Adobe Campaign.
* Nombre de aplicación **móvil** (uno para todos los dispositivos - Android e iOS). Es el ID de la aplicación móvil configurada en Adobe Campaign que se utilizará para recibir notificaciones push en los dispositivos de los usuarios. Para obtener más información sobre esto, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Plataforma **push** ("gcm" para Android o "apns" para iOS).

1. Al crear la configuración del evento, seleccione **[!UICONTROL Mobile application]** el canal y la dimensión **[!UICONTROL Real-time event]** de objetivo (consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Agregue campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enriquezca el contenido de mensajes transaccionales si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Los mensajes transaccionales basados en eventos deben utilizar solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización de contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje de transacción mediante la información de la base de datos de Adobe Campaign.

1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene los atributos "registrationtoken", "application" y "pushplatform" que se utilizarán para dirigir la entrega.

   ![](assets/message-center_push_api.png)

   Una vez publicada el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Para modificar y publicar el mensaje que acaba de crear, consulte [Envío de una notificación push de transacción para un evento](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integre el evento en el sitio web (consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Notificaciones push transaccionales basadas en perfiles {#profile-based-transactional-push-notifications}

Para enviar una notificación push de transacción a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil, primero debe crear y configurar un evento para la base de datos de Adobe Campaign.

1. Al crear la configuración del evento, seleccione **[!UICONTROL Mobile application]** el canal y la dimensión **[!UICONTROL Profile]** de objetivo (consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   De forma predeterminada, la notificación push transaccional se enviará a todas las aplicaciones móviles a las que se suscribieron los destinatarios. Para enviar la notificación Push a una aplicación móvil específica, selecciónela en la lista. El mensaje será dirigido a otras aplicaciones móviles, pero se excluirá del envío.

   ![](assets/message-center_push_appfilter.png)

1. Agregue campos al evento, si desea personalizar el mensaje transaccional (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Debe agregar al menos un campo para crear un enriquecimiento. No es necesario crear otros campos como **Nombre** y **Apellido** , ya que podrá utilizar campos de personalización desde la base de datos de Adobe Campaign.

1. Cree una enriquecimiento para vincular el evento al **[!UICONTROL Profile]** recurso (consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). La creación de un enriquecimiento es obligatoria al usar una dimensión **[!UICONTROL Profile]** de objetivo.
1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST no contiene ningún atributo que especifique el distintivo de registro, el nombre de la aplicación y la plataforma push, ya que se recuperarán del **[!UICONTROL Profile]** recurso.

   Una vez publicada el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Para modificar y publicar el mensaje que se acaba de crear, consulte [Envío de una notificación push de transacción para un perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Integre el evento en el sitio web (consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuración de un evento para enviar un mensaje de seguimiento {#configuring-an-event-to-send-a-follow-up-message}

Un mensaje de seguimiento es una plantilla de envío de marketing predefinida que se puede utilizar en un flujo de trabajo para enviar mensajes a los destinatarios de un mensaje de transacción específico. Para obtener más información, consulte [Mensajes de seguimiento](../../channels/using/follow-up-messages.md).

1. Utilice la misma configuración de evento que creó para enviar un mensaje transaccional de evento. Consulte [Mensajes transaccionales basados en eventos](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. Al configurar el evento, marque **[!UICONTROL Create follow-up delivery template for this event]** la casilla antes de publicar el evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Una vez publicada el evento, se crea automáticamente un mensaje transaccional y una plantilla de envío de seguimiento vinculada al nuevo evento. Para obtener más información sobre el uso de mensajes de seguimiento, consulte [Envío de un mensaje de seguimiento](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Caso de uso: configurar un evento para enviar un mensaje de transacción {#use-case--configuring-an-event-to-send-a-transactional-message}

En este ejemplo, queremos configurar un evento para enviar mensajes de confirmación después de cada compra en nuestro sitio web con los siguientes requisitos previos:

Como queremos identificar a nuestro cliente mediante su ID de CRM, primero asegúrese de que **[!UICONTROL Profile]** el recurso se haya ampliado con este nuevo campo.

Del mismo modo, debe haberse creado y publicado un recurso personalizado que corresponda a las compras y debe estar vinculado al **[!UICONTROL Profile]** recurso. De esta forma, podrá recuperar información de este recurso para enriquecer el contenido del mensaje.

Para obtener más información sobre la creación y publicación de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Cree un evento nuevo usando **[!UICONTROL Email]** el canal y la dimensión **[!UICONTROL Profile]** de objetivo (consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Defina los atributos que estarán disponibles para personalizar el mensaje transaccional. En nuestro caso, agregue el "ID de CRM" y los campos "Identificador de producto" (consulte [Definición de los atributos de evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer el contenido del mensaje con información acerca de las compras anteriores del cliente, cree un enriquecimiento para el **[!UICONTROL Purchase]** recurso (consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Cree una condición de unión entre el campo «Identificador de producto» que se agregó anteriormente al mensaje y el campo correspondiente del **[!UICONTROL Purchase]** recurso.

   ![](assets/message-center_usecase3.png)

1. Vista previa y publicación del evento (Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integre el evento en el sitio web (consulte [Integración del activador del evento en un sitio web](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).


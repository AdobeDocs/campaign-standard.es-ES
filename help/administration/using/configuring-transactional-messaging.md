---
solution: Campaign Standard
product: campaign
title: Configuración de la mensajería transaccional
description: Obtenga información sobre cómo configurar los mensajes transaccionales.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '3169'
ht-degree: 7%

---


# Configuración de la mensajería transaccional{#configuring-transactional-messaging}

Para enviar un mensaje transaccional con Adobe Campaign, primero debe describir la estructura de los datos de evento.

La configuración de evento debe realizarla un [administrador](../../administration/using/users-management.md#functional-administrators) siguiendo los pasos a continuación.

>[!NOTE]
>
>La configuración puede variar según el tipo de mensaje transaccional que desee enviar. Para obtener más información sobre esto, consulte [Configuraciones específicas del evento transaccional](#transactional-event-specific-configurations).

Una vez publicado el evento:

* Se implementa la API que utilizará el desarrollador de su sitio web y ahora se pueden enviar los eventos transaccionales. Consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website).

* El mensaje transaccional correspondiente se crea automáticamente. Consulte [Introducción a la mensajería transaccional](../../channels/using/getting-started-with-transactional-msg.md).

## Creación de un evento {#creating-an-event}

Para empezar, cree el evento correspondiente a sus necesidades.

>[!IMPORTANT]
>
>Sólo los usuarios que tienen la función **[!UICONTROL Administration]** y forman parte de la **[!UICONTROL All]** [unidad organizativa](../../administration/using/organizational-units.md) tienen los derechos adecuados para crear una configuración de evento.

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Haga clic en el botón **[!UICONTROL Create]**.
1. Asigne un **[!UICONTROL Label]** y un **[!UICONTROL ID]** al evento. El campo **[!UICONTROL ID]** es obligatorio y debe comenzar con el prefijo &quot;EVT&quot;. Si no utiliza este prefijo, se agrega automáticamente una vez que haga clic en **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >El ID no debe superar los 64 caracteres, incluido el prefijo EVT.

1. Seleccione el canal que se utilizará para enviar sus mensajes transaccionales **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** (notificación push).

   >[!NOTE]
   >
   >Solo se puede utilizar un canal para cada configuración de evento. Una vez creado el evento, no se puede cambiar el canal.

1. Seleccione la dimensión de segmentación correspondiente a la configuración de evento deseada y haga clic en **[!UICONTROL Create]**.

   Los datos de destinatario de mensajes transaccionales basados en eventos contenidos en el propio evento, mientras que los datos de destinatario de mensajes transaccionales basados en perfiles contenidos en la base de datos de Adobe Campaign. Para obtener más información sobre esto, consulte [Configuraciones específicas del evento transaccional](#transactional-event-specific-configurations).

>[!NOTE]
>
>El número de eventos creados en tiempo real puede tener un impacto en la plataforma. Para garantizar un rendimiento óptimo, asegúrese de eliminar eventos en tiempo real que ya no necesite. Consulte [Eliminación de un evento](#deleting-an-event).

## Definición de atributos de evento {#defining-the-event-attributes}

En la sección **[!UICONTROL Fields]**, defina los atributos que se integrarán en el contenido de evento y que podrán utilizarse para personalizar el mensaje transaccional.

Los pasos para agregar y modificar campos son los mismos que para [recursos personalizados](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Si desea crear un mensaje transaccional multilingüe, defina un atributo de evento adicional con el **[!UICONTROL AC_language]** ID. Esto solo se aplica a los mensajes transaccionales de evento. Una vez publicado el evento, los pasos para editar el contenido de un mensaje transaccional multilingüe son los mismos que para un correo electrónico estándar multilingüe. Consulte [Creación de un correo electrónico multilingüe](../../channels/using/creating-a-multilingual-email.md).

## Definición de colecciones de datos {#defining-data-collections}

Puede agregar al contenido del evento una colección de elementos, cada elemento en sí, incluidos varios atributos.

Esta colección se puede utilizar en un correo electrónico transaccional para agregar [listados de productos](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message) al contenido del mensaje, por ejemplo una lista de productos con el precio, el número de referencia, la cantidad, etc. para cada producto de la lista.

1. En la sección **[!UICONTROL Collections]**, haga clic en el botón **[!UICONTROL Create element]**.

   ![](assets/message-center_collection_create.png)

1. Añada una etiqueta y un ID para la colección.
1. Añada todos los campos que desee mostrar en el mensaje transaccional para cada producto de la lista.

   En este ejemplo, se han añadido los campos siguientes:

   ![](assets/message-center_collection_fields.png)

1. La ficha **[!UICONTROL Enrichment]** permite enriquecer cada elemento de la colección. Esto le permitirá personalizar los elementos de la lista de productos correspondiente con información de la base de datos de Adobe Campaign o de otros recursos que haya creado.

>[!NOTE]
>
>Los pasos para enriquecer los elementos de una colección son los mismos que se describen en la sección [Enriquecimiento del evento](#enriching-the-transactional-message-content). Tenga en cuenta que enriquecer el evento no le permitirá enriquecer una colección: debe agregar un enriquecimiento a la propia colección en la sección **[!UICONTROL Collections]**.

Una vez que se publiquen el evento y el mensaje, podrá utilizar esta colección en su mensaje transaccional.

Esta es la previsualización de API para este ejemplo:

![](assets/message-center_collection_api-preview.png)

**Temas relacionados:**

* [Vista previa y publicación del evento](#previewing-and-publishing-the-event)
* [Uso de listas de productos en un mensaje transaccional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriquecimiento del evento {#enriching-the-transactional-message-content}

Puede enriquecer el contenido de mensaje transaccional con información de la base de datos de Adobe Campaign para personalizar sus mensajes. Por ejemplo, desde el apellido o el ID de CRM de cada uno de sus destinatarios, puede recuperar datos como su dirección o fecha de nacimiento o cualquier otro campo personalizado agregado en la tabla de Perfiles, para personalizar la información que se les envía.

Es posible enriquecer el contenido de mensaje transaccional con información de **[!UICONTROL Profile and services Ext API]** extendida. Para obtener más información, consulte [Ampliación de la API: Publicación de la extensión](../../developing/using/step-2--publish-the-extension.md)

Esta información también se puede almacenar en nuevos recursos. En ese caso, el recurso debe estar vinculado a los recursos **[!UICONTROL Profile]** o **[!UICONTROL Service]** directamente o a través de otra tabla. Por ejemplo: en la configuración siguiente, es posible enriquecer el contenido de mensaje transaccional con información del recurso **[!UICONTROL Product]** como la categoría del producto o la ID, si el recurso **[!UICONTROL Product]** está vinculado al recurso **[!UICONTROL Profile]**.

![](assets/message-center_usecaseschema.png)

Para obtener más información sobre la creación y publicación de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. En la sección **[!UICONTROL Enrichment]**, haga clic en el botón **[!UICONTROL Create element]**.

   ![](assets/message-center_addenrichment.png)

1. Seleccione el recurso con el que desea vincular el mensaje. En este caso, elija el recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_new-enrichment.png)

1. Utilice el botón **[!UICONTROL Create element]** para vincular un campo del recurso seleccionado a uno de los campos que agregó anteriormente al evento (consulte [Definición de atributos del evento](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. En este ejemplo, reconciliamos los campos **[!UICONTROL Last name]** y **[!UICONTROL First name]** con los campos correspondientes del recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_enrichment-join-fields.png)

   También puede enriquecer el contenido de mensaje transaccional mediante el recurso **[!UICONTROL Service]**. Para obtener más información sobre los servicios, consulte esta [sección](../../audiences/using/creating-a-service.md).

1. Si está creando o editando un evento basado en perfiles, en la sección **[!UICONTROL Targeting enrichment]**, seleccione el enriquecimiento que se utilizará como destinatario de mensajes durante la ejecución del envío.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >La selección de un enriquecimiento de objetivo basado en el **[!UICONTROL Profile]** recurso es obligatoria para eventos basados en perfiles.

Una vez que se publiquen el evento y el mensaje, este vínculo le permitirá enriquecer el contenido del mensaje transaccional.

**Temas relacionados:**

* [Vista previa y publicación del evento](#previewing-and-publishing-the-event).
* [Personalización de un mensaje transaccional](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Vista previa y publicación del evento {#previewing-and-publishing-the-event}

Antes de poder usar el evento, debe previsualización y publicarlo.

1. Haga clic en el botón **[!UICONTROL API preview]** para ver una simulación de la API de REST que utilizará el desarrollador de su sitio web antes de que se publique. Una vez publicado el evento, este botón también le permite ver una previsualización de la API en producción. Consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La API de REST varía según el canal seleccionado y la dimensión de segmentación seleccionada. Para obtener más información sobre las distintas configuraciones, consulte [Configuraciones específicas de evento transaccional](#transactional-event-specific-configurations).

1. Haga clic en **[!UICONTROL Publish]** para la publicación de inicio.

   ![](assets/message-center_pub.png)

   Se implementa la API que utilizará el desarrollador de su sitio web y ahora se pueden enviar los eventos transaccionales.

1. Puede vista de los registros de publicación en la ficha correspondiente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Cada vez que modifique el evento, debe volver a hacer clic en **[!UICONTROL Publish]** para generar la API REST actualizada que utilizará el desarrollador del sitio web.

   Una vez publicado el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento.

1. Puede acceder directamente a este mensaje transaccional a través del vínculo situado en el área izquierda.

   ![](assets/message-center_messagegeneration.png)

Para que el evento active el envío de un mensaje transaccional, debe modificar y publicar el mensaje que se acaba de crear. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

También debe integrar este evento de activación en su sitio web. Consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website).

Una vez que los inicios de Adobe Campaign reciben eventos relacionados con esta configuración de evento, el vínculo **[!UICONTROL Latest transactional events]** de la sección **[!UICONTROL History]** le permite acceder a los últimos eventos enviados por su servicio de terceros y procesados por Adobe Campaign.

![](assets/message-center_latest-events.png)

Los eventos (en formato JSON) se muestran de los más recientes a los más antiguos. Esta lista le permite comprobar datos como el contenido o el estado de un evento para fines de control y depuración.

### Cancelación de la publicación de un evento {#unpublishing-an-event}

El botón **[!UICONTROL Unpublish]** permite cancelar la publicación del evento, lo que elimina de la API de REST el recurso correspondiente al evento que creó anteriormente. Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si ya ha publicado el mensaje transaccional correspondiente, la publicación de mensaje transaccional también se cancela. Consulte [Cancelación de la publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Haga clic en el botón **[!UICONTROL Publish]** para generar una nueva API de REST.

### Proceso de publicación de mensajes transaccionales {#transactional-messaging-pub-process}

El gráfico siguiente ilustra el proceso de publicación de mensajes transaccionales.

![](assets/message-center_pub-process.png)

Para obtener más información sobre la publicación, pausa y cancelación de publicaciones de mensajes transaccionales, consulte [esta sección](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

### Eliminación de un evento {#deleting-an-event}

Una vez cancelada la publicación de un evento o si aún no se ha publicado un evento, puede eliminarlo de la lista de configuración de evento. Para ello:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Pase el ratón sobre la configuración de evento que desee y seleccione el botón **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Asegúrese de que la configuración de evento tiene el estado **[!UICONTROL Draft]**; de lo contrario, no podrá eliminarla. El estado **[!UICONTROL Draft]** se aplica a un evento que aún no se ha publicado o que ha estado [sin publicar](#unpublishing-an-event).

1. Haga clic en el botón **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Al eliminar una configuración de evento que se ha publicado y que ya se ha utilizado, también se eliminarán los mensajes transaccionales correspondientes y sus registros de seguimiento y envíos.

## Buscando eventos transaccionales {#searching-transactional-events}

Para acceder y buscar los eventos transaccionales ya creados, siga los pasos a continuación.

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Haga clic en el botón **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. Puede filtrar por **[!UICONTROL Publication status]**. Esto le permite mostrar únicamente los eventos publicados, por ejemplo.
1. También puede filtrar los eventos mediante **[!UICONTROL Last event received]**. Por ejemplo, si introduce 10, solo se mostrarán las configuraciones de evento con el último evento recibido hace 10 días o más. Esto le permite mostrar qué eventos han estado inactivos durante un período determinado.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >El valor predeterminado es 0. A continuación, se muestran todos los eventos.

## Integración de la activación del evento en un sitio Web {#integrating-the-triggering-of-the-event-in-a-website}

Una vez que haya creado un evento, deberá integrar el activador de este evento en su sitio web.

En el ejemplo descrito en la sección [evento operativo de mensajería transaccional](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle), desea que se active un &quot;abandono del carro de compras&quot; cada vez que uno de los clientes abandone el sitio Web antes de comprar los productos en el carro de compras. Para ello, el desarrollador web de su sitio web debe utilizar la API de Adobe Campaign Standard REST.

Consulte la [Documentación de API de REST](../../api/using/managing-transactional-messages.md).

## Configuraciones específicas del evento transaccional {#transactional-event-specific-configurations}

La configuración del evento transaccional puede variar según el tipo de mensaje transaccional que desee enviar (evento o perfil) y el canal que se utilizará.

Las siguientes secciones detallan qué configuración específica debe configurarse según el mensaje transaccional deseado. Para obtener más información sobre los pasos generales para configurar un evento, consulte [Creación de un evento](#creating-an-event).

### Mensajes transaccionales basados en eventos {#event-based-transactional-messages}

Para enviar un mensaje transaccional basado en eventos, primero debe crear y configurar un evento que dirija los datos contenidos en el propio evento.
Para obtener más información, consulte [Mensajería transaccional](https://helpx.adobe.com/es/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Al crear la configuración de evento, seleccione la dimensión de segmentación **[!UICONTROL Real-time event]** (consulte [Creación de un evento](#creating-an-event)).
1. Añada los campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](#defining-the-event-attributes)).
1. Enriquecer el contenido de mensaje transaccional si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del contenido de mensaje transaccional](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign.

1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene un atributo que especifica la dirección de correo electrónico o el teléfono móvil según el canal seleccionado.

   Una vez publicado el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que el evento active el envío de un mensaje transaccional, debe modificar y publicar el mensaje que se acaba de crear, consulte [mensajes transaccionales de Evento](../../channels/using/event-transactional-messages.md).

1. Integre el evento en su sitio Web (consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website)).

### Mensajes transaccionales basados en perfil {#profile-based-transactional-messages}

Para enviar un mensaje transaccional basado en perfil, primero debe crear y configurar los datos de objetivo de evento contenidos en la base de datos de Adobe Campaign.

1. Al crear la configuración de evento, seleccione la dimensión de segmentación **[!UICONTROL Profile event]** (consulte [Creación de un evento](#creating-an-event)).
1. Añada los campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](#defining-the-event-attributes)). Debe agregar al menos un campo para crear un enriquecimiento. No es necesario crear otros campos, como **Nombre** y **Apellido**, ya que podrá utilizar campos de personalización de la base de datos de Adobe Campaign.
1. Cree un enriquecimiento para vincular el evento al recurso **[!UICONTROL Profile]** (consulte [Enriquecimiento del contenido de mensaje transaccional](#enriching-the-transactional-message-content)). La creación de un enriquecimiento es obligatoria cuando se utiliza una dimensión de segmentación **[!UICONTROL Profile]**.
1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST no contiene un atributo que especifique la dirección de correo electrónico o el teléfono móvil, ya que se recuperará del recurso **[!UICONTROL Profile]**.

   Una vez publicado el evento, se crea automáticamente un mensaje transaccional vinculado al nuevo evento. Para que el evento active el envío de un mensaje transaccional, debe modificar y publicar el mensaje que se acaba de crear, consulte [Envío de un mensaje transaccional de perfil](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integre el evento en su sitio Web (consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website)).

### Notificaciones push transaccionales basadas en eventos {#event-based-transactional-push-notifications}

Para poder enviar notificaciones push transaccionales, debe configurar Adobe Campaign en consecuencia. Consulte [Configuración push](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html).

Para enviar una notificación push de transacción anónima a todos los usuarios que hayan adhesión para recibir notificaciones desde la aplicación móvil, primero debe crear y configurar un evento que dirija los datos contenidos en el propio evento. A continuación se presentan los pasos correspondientes.

El evento debe contener los tres elementos siguientes:

* Un **token de registro**, que es el ID de usuario para una aplicación móvil y un dispositivo. Puede que no corresponda a ningún perfil de la base de datos de Adobe Campaign.
* Un **nombre de aplicación móvil** (uno para todos los dispositivos: Android e iOS). ID de la aplicación móvil configurada en Adobe Campaign que se utilizará para recibir notificaciones push en los dispositivos de los usuarios. Para obtener más información, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Una **plataforma push** (&quot;gcm&quot; para Android o &quot;apns&quot; para iOS).

1. Al crear la configuración de evento, seleccione el canal **[!UICONTROL Mobile application]** y la dimensión de segmentación **[!UICONTROL Real-time event]** (consulte [Creación de un evento](#creating-an-event)).
1. Añada los campos al evento para poder personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](#defining-the-event-attributes)).
1. Enriquecer el contenido de mensaje transaccional si desea utilizar información adicional de la base de datos de Adobe Campaign (consulte [Enriquecimiento del contenido de mensaje transaccional](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign.

1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST contiene los atributos &quot;registrationToken&quot;, &quot;application&quot; y &quot;pushPlatform&quot; que se utilizarán para el destinatario del envío.

   ![](assets/message-center_push_api.png)

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Para modificar y publicar el mensaje que se acaba de crear, consulte [Envío de una notificación push transaccional dirigida a un evento](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integre el evento en su sitio Web (consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website)).

### Notificaciones push transaccionales basadas en perfiles {#profile-based-transactional-push-notifications}

Para enviar una notificación push de transacción a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil, primero debe crear y configurar un evento que segmente la base de datos de Adobe Campaign.

1. Al crear la configuración de evento, seleccione el canal **[!UICONTROL Mobile application]** y la dimensión de segmentación **[!UICONTROL Profile]** (consulte [Creación de un evento](#creating-an-event)).

   De forma predeterminada, la notificación push de transacción se enviará a todas las aplicaciones móviles a las que se hayan suscrito los destinatarios. Para enviar la notificación push a una aplicación móvil específica, selecciónela en la lista. Las demás aplicaciones móviles serán segmentadas por el mensaje pero se excluirán del envío.

   ![](assets/message-center_push_appfilter.png)

1. Añada los campos al evento si desea personalizar el mensaje transaccional (consulte [Definición de los atributos del evento](#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Debe agregar al menos un campo para crear un enriquecimiento. No es necesario crear otros campos, como **Nombre** y **Apellido**, ya que podrá utilizar campos de personalización de la base de datos de Adobe Campaign.

1. Cree un enriquecimiento para vincular el evento al recurso **[!UICONTROL Profile]** (consulte [Enriquecimiento del contenido de mensaje transaccional](#enriching-the-transactional-message-content)). La creación de un enriquecimiento es obligatoria cuando se utiliza una dimensión de segmentación **[!UICONTROL Profile]**.
1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).

   Al obtener una vista previa del evento, la API de REST no contiene ningún atributo que especifique el token de registro, el nombre de la aplicación y la plataforma push, ya que se recuperarán del recurso **[!UICONTROL Profile]**.

   Una vez publicado el evento, se crea automáticamente una notificación push transaccional vinculada al nuevo evento. Para modificar y publicar el mensaje que se acaba de crear, consulte [Envío de una notificación push transaccional dirigida a un perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Integre el evento en su sitio Web (consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website)).

### Configuración de un evento para enviar un mensaje de seguimiento {#configuring-an-event-to-send-a-follow-up-message}

Un mensaje de seguimiento es una Plantilla de envíos de marketing predefinida que se puede utilizar en un flujo de trabajo para enviar mensajes a los destinatarios de un mensaje transaccional específico. Para obtener más información sobre esto, consulte [Mensajes de seguimiento](../../channels/using/follow-up-messages.md).

1. Utilice la misma configuración de evento que creó para enviar un mensaje transaccional de evento. Consulte [mensajes transaccionales basados en Evento](#event-based-transactional-messages).
1. Al configurar el evento, marque la casilla **[!UICONTROL Create follow-up delivery template for this event]** antes de publicar el evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).

   Una vez publicado el evento, se crea automáticamente un mensaje transaccional y una Plantilla de envíos de seguimiento vinculada al nuevo evento. Para obtener más información sobre el uso de mensajes de seguimiento, consulte [Envío de un mensaje de seguimiento](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Caso de uso: configuración de un evento para enviar un mensaje transaccional {#use-case--configuring-an-event-to-send-a-transactional-message}

En este ejemplo, queremos configurar un evento para enviar mensajes de confirmación después de cada compra en nuestro sitio web con los siguientes requisitos previos:

Como queremos identificar a nuestro cliente mediante su ID de CRM, primero asegúrese de que el recurso **[!UICONTROL Profile]** se haya ampliado con este nuevo campo.

Del mismo modo, se debe crear y publicar un recurso personalizado correspondiente a las compras y vincularlo al recurso **[!UICONTROL Profile]**. De este modo, podrá recuperar información de este recurso para enriquecer el contenido del mensaje.

Para obtener más información sobre la creación y publicación de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Cree un nuevo evento con el canal **[!UICONTROL Email]** y la dimensión de segmentación **[!UICONTROL Profile]** (consulte [Creación de un evento](#creating-an-event)).
1. Defina los atributos que estarán disponibles para personalizar el mensaje transaccional. En nuestro caso, agregue los campos &quot;ID de CRM&quot; y &quot;Identificador de producto&quot; (consulte [Definición de atributos de evento](#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer el contenido del mensaje con información acerca de las compras anteriores del cliente, cree un enriquecimiento dirigido al **[!UICONTROL Purchase]** recurso (consulte [Enriquecimiento del contenido del mensaje transaccional](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Cree una condición de combinación entre el campo &quot;Identificador de producto&quot; que se agregó anteriormente al mensaje y el campo correspondiente del recurso **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Previsualización y publicación del evento (consulte [Vista previa y publicación del evento](#previewing-and-publishing-the-event)).
1. Integre el evento en su sitio Web (consulte [Integración del activador del evento en un sitio Web](#integrating-the-triggering-of-the-event-in-a-website)).


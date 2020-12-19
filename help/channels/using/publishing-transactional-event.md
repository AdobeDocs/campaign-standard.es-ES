---
solution: Campaign Standard
product: campaign
title: Publicación de un evento transaccional
description: Obtenga información sobre cómo previsualización, publicación, cancelación de publicación y eliminación de una configuración de evento transaccional.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 8%

---


# Publicación de un evento transaccional {#publishing-transactional-event}

Una vez que [la configuración](../../channels/using/configuring-transactional-event.md) ha finalizado, el evento está listo para publicarse. A continuación se describen los pasos para la previsualización, publicación, cancelación de la publicación y eliminación de un evento.

>[!IMPORTANT]
>
>Sólo [Los administradores funcionales](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->tienen los derechos adecuados para publicar configuraciones de evento.

En [esta sección](../../channels/using/publishing-transactional-message.md) encontrará un gráfico que ilustra todo el proceso de publicación de mensajes transaccionales, incluidas las configuraciones de evento de publicación y cancelación de publicación.

Una vez finalizada la publicación:
* El mensaje transaccional correspondiente se crea automáticamente. Consulte [Edición de mensajes transaccionales](../../channels/using/editing-transactional-message.md).
* Se implementa la API que utilizará el desarrollador de su sitio web y ahora se pueden enviar los eventos transaccionales. Consulte [Integración del activador de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Vista previa y publicación de un evento {#previewing-and-publishing-the-event}

Antes de poder usar el evento, debe previsualización y publicarlo.

1. Haga clic en el botón **[!UICONTROL API preview]** para ver una simulación de la API de REST que utilizará el desarrollador de su sitio web antes de que se publique.

   Una vez publicado el evento, este botón también le permite ver una previsualización de la API en producción. Consulte [Integración del activador de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La API de REST varía según el canal seleccionado y la dimensión de segmentación seleccionada. Para obtener más información sobre las distintas configuraciones, consulte [esta sección](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Haga clic en **[!UICONTROL Publish]** para la publicación de inicio.

   ![](assets/message-center_pub.png)

   Se implementa la API que utilizará el desarrollador de su sitio web y ahora se pueden enviar los eventos transaccionales.

1. Puede vista de los registros de publicación en la ficha correspondiente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Cada vez que modifique el evento, debe volver a hacer clic en **[!UICONTROL Publish]** para generar la API REST actualizada que utilizará el desarrollador del sitio web.

   Una vez publicado el evento, se crea automáticamente un [mensaje transaccional](../../channels/using/editing-transactional-message.md) vinculado al nuevo evento.

1. Puede acceder directamente a este mensaje transaccional a través del vínculo situado en el área izquierda.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >Para que el evento active el envío de un mensaje transaccional, debe modificar y publicar el mensaje que se acaba de crear. Consulte las secciones [Edición](../../channels/using/editing-transactional-message.md) y [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md). También debe [integrar este evento de activación](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) en su sitio Web.

1. Una vez que los inicios de Adobe Campaign reciban eventos relacionados con esta configuración de evento, puede hacer clic en el vínculo **[!UICONTROL Latest transactional events]** en la sección **[!UICONTROL History]** para acceder a los últimos eventos enviados por su servicio de terceros y procesados por Adobe Campaign.

![](assets/message-center_latest-events.png)

Los eventos (en formato JSON) se muestran de los más recientes a los más antiguos. Esta lista le permite comprobar datos como el contenido o el estado de un evento para fines de control y depuración.

## Cancelación de la publicación de un evento {#unpublishing-an-event}

El botón **[!UICONTROL Unpublish]** permite cancelar la publicación del evento, lo que elimina de la API de REST el recurso correspondiente al evento que creó anteriormente.

Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si ya ha publicado el mensaje transaccional correspondiente, la publicación de mensaje transaccional también se cancela. Consulte [Cancelación de la publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Haga clic en el botón **[!UICONTROL Publish]** para generar una nueva API de REST.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Eliminación de un evento {#deleting-an-event}

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

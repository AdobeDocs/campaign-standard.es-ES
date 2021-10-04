---
title: Publicación de un evento transaccional
description: Obtenga información sobre cómo previsualizar, publicar, cancelar la publicación y eliminar una configuración de evento transaccional.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# Publicación de un evento transaccional {#publishing-transactional-event}

Una vez [configurada](../../channels/using/configuring-transactional-event.md) completada, el evento está listo para publicarse. A continuación se describen los pasos para obtener una vista previa, publicar, cancelar la publicación y eliminar un evento.

>[!IMPORTANT]
>
>Solo los [administradores funcionales](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->tienen los derechos adecuados para publicar configuraciones de eventos.

En [esta sección](../../channels/using/publishing-transactional-message.md) hay disponible un gráfico que ilustra todo el proceso de publicación de mensajería transaccional, incluidas las configuraciones de evento de publicación y cancelación de publicación.

Una vez realizada la publicación:
* El mensaje transaccional correspondiente se crea automáticamente. Consulte [Edición de mensajes transaccionales](../../channels/using/editing-transactional-message.md).
* El desarrollador del sitio web implementa la API que utilizará y ahora se pueden enviar los eventos transaccionales. Consulte [Integrar el activador de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Vista previa y publicación de un evento {#previewing-and-publishing-the-event}

Antes de poder utilizar el evento, debe previsualizarlo y publicarlo.

1. Haga clic en el botón **[!UICONTROL API preview]** para ver una simulación de la API de REST que utilizará el desarrollador del sitio web antes de publicarse.

   Una vez publicado el evento, este botón también le permite ver una previsualización de la API en producción. Consulte [Integrar el activador de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La API de REST varía según el canal seleccionado y la dimensión de segmentación seleccionada. Para obtener más información sobre las distintas configuraciones, consulte [esta sección](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Haga clic en **[!UICONTROL Publish]** para iniciar la publicación.

   ![](assets/message-center_pub.png)

   El desarrollador del sitio web implementa la API que utilizará y ahora se pueden enviar los eventos transaccionales.

1. Puede ver los registros de publicación en la pestaña correspondiente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Cada vez que modifique el evento, debe hacer clic **[!UICONTROL Publish]** de nuevo para generar la API de REST actualizada que utilizará el desarrollador del sitio web.

   Una vez publicado el evento, se crea automáticamente un [mensaje transaccional](../../channels/using/editing-transactional-message.md) vinculado al nuevo evento.

1. Puede acceder directamente a este mensaje transaccional a través del vínculo ubicado en el área izquierda.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >Para que el evento pueda almacenar en déclencheur el envío de un mensaje transaccional, debe modificar y publicar el mensaje que acaba de crearse. Consulte las secciones [Edición](../../channels/using/editing-transactional-message.md) y [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md). También debe [integrar este evento de déclencheur](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) en su sitio web.

1. Una vez que Adobe Campaign empiece a recibir eventos relacionados con esta configuración de evento, puede hacer clic en el enlace **[!UICONTROL Latest transactional events]** en la sección **[!UICONTROL History]** para acceder a los últimos eventos enviados por su servicio de terceros y procesados por Adobe Campaign.

![](assets/message-center_latest-events.png)

Los eventos (en formato JSON) se enumeran de los más recientes a los más antiguos. Esta lista permite comprobar datos como el contenido o el estado de un evento para fines de control y depuración.

## Cancelación de la publicación de un evento {#unpublishing-an-event}

El botón **[!UICONTROL Unpublish]** permite cancelar la publicación del evento, que elimina de la API de REST el recurso correspondiente al evento que ha creado anteriormente.

Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si ya ha publicado el mensaje transaccional correspondiente, la publicación del mensaje transaccional también se cancela. Consulte [Cancelación de la publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Haga clic en el botón **[!UICONTROL Publish]** para generar una nueva API de REST.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Eliminación de un evento {#deleting-an-event}

Una vez que se ha cancelado la publicación de un evento o si aún no se ha publicado, puede eliminarlo de la lista de configuración de evento. Para ello, haga lo siguiente:

1. Haga clic en el logotipo **Adobe**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Pase el ratón sobre la configuración de evento de su elección y seleccione el botón **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Asegúrese de que la configuración de evento tenga el estado **[!UICONTROL Draft]** ; de lo contrario, no podrá eliminarlo. El estado **[!UICONTROL Draft]** se aplica a un evento que aún no se ha publicado o que ha sido [no publicado](#unpublishing-an-event).

1. Haga clic en el botón **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Al eliminar una configuración de evento que se ha publicado y que ya se ha utilizado, también se eliminarán los mensajes transaccionales correspondientes, así como sus registros de envío y seguimiento.

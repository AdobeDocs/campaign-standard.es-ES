---
title: Mensajes de seguimiento
description: Obtenga información sobre cómo crear, administrar y enviar un mensaje de seguimiento.
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# Mensajes de seguimiento {#follow-up-messages}

Un mensaje de seguimiento es una plantilla de envío de marketing predefinida que se puede utilizar en un flujo de trabajo para enviar otra comunicación a los destinatarios de un mensaje transaccional específico.

Vamos a reutilizar el ejemplo descrito en la [Principio operativo de mensajería transaccional](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) sección: se envía un correo electrónico de abandono del carro de compras a los usuarios del sitio web que agregaron productos al carro de compras, pero que abandonaron el sitio sin comprar.

Desea enviar un recordatorio descriptivo a todos los clientes que recibieron la notificación de abandono del carro de compras, pero que no la abrieron después de tres días. Recibirán un mensaje de seguimiento basado en los mismos datos que se utilizaron en el primer correo electrónico enviado.

## Configuración de un evento para enviar un mensaje de seguimiento {#configuring-an-event-to-send-a-follow-up-message}

Para enviar un mensaje de seguimiento, primero debe configurar en consecuencia el evento correspondiente al mensaje transaccional ya recibido.

1. Utilice la misma configuración de evento que creó para enviar un mensaje transaccional de evento. Consulte [Configuración de un evento transaccional](../../channels/using/configuring-transactional-event.md).
1. Al configurar el evento, consulte **[!UICONTROL Create follow-up delivery template for this event]** antes de publicar el evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. [Previsualización y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Una vez publicado el evento, se crea automáticamente un mensaje transaccional y una plantilla de envío de seguimiento vinculada al nuevo evento. Los pasos para enviar el mensaje de seguimiento se detallan en [esta sección](#sending-a-follow-up-message).

## Acceso a los mensajes de seguimiento {#accessing-the-follow-up-messages}

Para gestionar un evento en un flujo de trabajo, se requiere una plantilla de envíos. Sin embargo, al publicar el evento, la variable [mensaje transaccional](../../channels/using/editing-transactional-message.md) que se ha creado no puede utilizarse como plantilla. Por lo tanto, se debe crear una plantilla de envío de seguimiento específica diseñada para admitir este tipo de evento y utilizarla como plantilla en un flujo de trabajo.

Para acceder a esta plantilla:

1. Haga clic en **Adobe** en la esquina superior izquierda.
1. Seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Compruebe la **[!UICONTROL Follow-up messages]** en el panel izquierdo.

   ![](assets/message-center_follow-up-search.png)

Solo se muestran los mensajes de seguimiento.

>[!IMPORTANT]
>
>Solo los usuarios con [Administration](../../administration/using/users-management.md#functional-administrators) La función puede acceder y editar mensajes transaccionales.

## Envío de un mensaje de seguimiento {#sending-a-follow-up-message}

Una vez creada la plantilla de entrega de seguimiento, puede utilizarla en un flujo de trabajo para enviar un mensaje de seguimiento.

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. Acceda a la lista de actividad de marketing y cree un nuevo flujo de trabajo.

   Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Arrastrar y soltar una **[!UICONTROL Scheduler]** en el flujo de trabajo y ábralo. Establezca la frecuencia de ejecución en una vez al día.

   La actividad Planificador se presenta en la [Planificador](../../automating/using/scheduler.md) sección.

1. Arrastrar y soltar una **[!UICONTROL Query]** en el flujo de trabajo y ábralo.

   La actividad de consulta se presenta en la [Consulta](../../automating/using/query.md) sección.

1. Para ejecutar la consulta en un recurso que no sea el de perfil, vaya al **[!UICONTROL Properties]** y haga clic en la pestaña **[!UICONTROL Resource]** lista desplegable.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >De forma predeterminada, la actividad está preconfigurada para buscar perfiles.

1. Seleccione el evento al que desee destinarlo para que sólo tenga acceso a los datos de este evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vaya al de la actividad **[!UICONTROL Target]** , y arrastre y suelte el **[!UICONTROL Delivery logs (logs)]** de la paleta al espacio de trabajo.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Seleccionar **[!UICONTROL Exists]** para dirigirse a todos los clientes que recibieron el correo electrónico.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Mover el **[!UICONTROL Tracking logs (tracking)]** de la paleta al espacio de trabajo y seleccione **[!UICONTROL Does not exist]** para dirigirse a todos los clientes que no hayan abierto el correo electrónico.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Arrastre y suelte el evento al que está dirigiendo (**Abandono del carro** en este ejemplo) de la paleta al espacio de trabajo. A continuación, defina una regla para dirigir todos los mensajes enviados hace tres días.

   ![](assets/message-center_follow-up-created.png)

   Esto significa que todos los destinatarios que recibieron el mensaje transaccional tres días antes de la ejecución del flujo de trabajo y que aún no lo han abierto están segmentados.

   Clic **[!UICONTROL Confirm]** para guardar la consulta.

1. Arrastre y suelte un **Envío de correo electrónico** en el flujo de trabajo.

   La actividad Entregar correo electrónico se presenta en la [Envío de correo electrónico](../../automating/using/email-delivery.md) sección.

   ![](assets/message-center_follow-up-workflow.png)

   También puede utilizar un [Envío de SMS](../../automating/using/sms-delivery.md) o una [Entrega de notificaciones push](../../automating/using/push-notification-delivery.md) actividad. En este caso, asegúrese de seleccionar la variable **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** al crear la configuración de evento. Consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Abra el **Envío de correo electrónico** actividad. En el asistente de creación, marque la **[!UICONTROL Follow-up messages]** y seleccione la plantilla de envío de seguimiento que se creó después de publicar el evento.

   ![](assets/message-center_follow-up-template.png)

1. En el contenido del mensaje de seguimiento, puede aprovechar el contenido del evento añadiendo campos de personalización.

   ![](assets/message-center_follow-up-content.png)

1. Busque los campos que definió al crear el evento seleccionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Consulte [Personalizar un mensaje transaccional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Esto significa que puede aprovechar el mismo contenido, incluidos los datos enriquecidos, que se utilizó la primera vez que se envió el evento para crear un recordatorio personalizado y descriptivo.

1. Guarde la actividad e inicie el flujo de trabajo.

Una vez iniciado el flujo de trabajo, todos los clientes que recibieron la notificación de abandono del carro de compras hace tres días pero que no la abrieron recibirán un mensaje de seguimiento basado en los mismos datos.

>[!NOTE]
>
>Si seleccionó la **[!UICONTROL Profile]** dimensión de segmentación al crear la configuración de evento, el mensaje de seguimiento también utilizará la base de datos de marketing de Adobe Campaign. Consulte [Mensajes transaccionales de perfil ](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).

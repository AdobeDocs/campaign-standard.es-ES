---
title: Mensajes de seguimiento
seo-title: Mensajes de seguimiento
description: Mensajes de seguimiento
seo-description: Obtenga información sobre cómo crear y publicar un mensaje de seguimiento.
page-status-flag: nunca activado
uuid: d2a17da2-e935-420a-8531-78ed6a1fe68b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: transaccional-mensajería
discoiquuid: 9615e369-754f-4f6a-a1b1-14462f94666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d9357481a567cb0d11eea43211abf08a6dcb07d6

---


# Mensajes de seguimiento{#follow-up-messages}

Puede enviar un mensaje de seguimiento a los clientes que hayan recibido un mensaje transaccional específico. Para ello, debe configurar un flujo de trabajo dirigido al evento correspondiente.

Vamos a reutilizar el ejemplo descrito en la sección de principios [operativos de mensajería](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) transaccional: se envía un correo electrónico de abandono del carro de compras a los usuarios del sitio web que han agregado productos al carro de compras, pero que han abandonado el sitio sin pasar por sus compras.

Desea enviar un recordatorio práctico a todos los clientes que recibieron la notificación de abandono del carro de compras pero que no la abrieron después de tres días.

A continuación, cada cliente interesado recibirá un mensaje de seguimiento basado en los mismos datos que se usaron en el primer correo electrónico enviado.

## Acceso a los mensajes de seguimiento {#accessing-the-follow-up-messages}

Una vez creado y publicado un evento (el abandono del carro de compras según el [ejemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) anterior), el mensaje transaccional y el mensaje de seguimiento correspondientes se crean automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de seguimiento.

Para gestionar un evento en un flujo de trabajo, se requiere una plantilla de entrega. Sin embargo, al publicar el evento, el mensaje [de](../../channels/using/event-transactional-messages.md) transacción que se crea no se puede usar como plantilla. Por lo tanto, debe crear una plantilla de entrega de seguimiento específica diseñada para admitir este tipo de evento y para utilizarse como plantilla en un flujo de trabajo.

Para acceder a esta plantilla:

1. Haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la esquina superior izquierda.
1. Seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]**.
1. Marque la **[!UICONTROL Follow-up messages]** casilla en el panel izquierdo.

   ![](assets/message-center_follow-up-search.png)

Solo se muestran los mensajes de seguimiento.

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración o aparecer en el grupo de seguridad **[!UICONTROL Message Center agents]** (mcExec).

## Envío de un mensaje de seguimiento {#sending-a-follow-up-message}

Una vez creada la plantilla de envío de seguimiento, puede utilizarla en un flujo de trabajo para enviar un mensaje de seguimiento.

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo.

   Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Arrastre y suelte una **[!UICONTROL Scheduler]** actividad en el flujo de trabajo y ábrala. Establezca la frecuencia de ejecución en una vez al día.

   La actividad Programador se presenta en la sección [Programador](../../automating/using/scheduler.md) .

1. Arrastre y suelte una **[!UICONTROL Query]** actividad en el flujo de trabajo y ábrala.

   La actividad Consulta se presenta en la sección [Consulta](../../automating/using/query.md) .

1. Para ejecutar la consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y haga clic en la lista **[!UICONTROL Resource]** desplegable.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >De forma predeterminada, la actividad está preconfigurada para buscar perfiles.

1. Seleccione el evento al que desea dirigirse para que solo pueda acceder a los datos de este evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vaya a la ficha de la actividad y arrastre y suelte el **[!UICONTROL Target]** elemento de la **[!UICONTROL Delivery logs (logs)]** **[!UICONTROL Email]** sección en el espacio de trabajo.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Seleccione **[!UICONTROL Exists]** para dirigirse a todos los clientes que recibieron el correo electrónico.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Mueva el **[!UICONTROL Tracking logs (tracking)]** elemento de la paleta al espacio de trabajo y seleccione **[!UICONTROL Does not exist]** el objetivo de todos los clientes que no abrieron el correo electrónico.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Arrastre y suelte el evento que está dirigiendo (abandono **del** carro en este ejemplo) desde la **[!UICONTROL Email]** sección al espacio de trabajo. A continuación, defina una regla para dirigir todos los mensajes enviados hace tres días.

   ![](assets/message-center_follow-up-created.png)

   Esto significa que todos los destinatarios que recibieron el mensaje transaccional tres días antes de la ejecución del flujo de trabajo y que aún no lo han abierto están segmentados.

   Haga clic en **[!UICONTROL Confirm]** para guardar la consulta.

1. Arrastre y suelte una actividad de envío **** de correo electrónico en el flujo de trabajo.

   La actividad de envío de correo electrónico se presenta en la sección de envío [de](../../automating/using/email-delivery.md) correo electrónico.

   ![](assets/message-center_follow-up-workflow.png)

   También puede utilizar un envío [](../../automating/using/sms-delivery.md) SMS o una actividad de entrega [de aplicaciones](../../automating/using/push-notification-delivery.md) móviles. En este caso, asegúrese de seleccionar el canal **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** al crear la configuración del evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Open the **Email delivery** activity. En el asistente de creación, marque la **[!UICONTROL Follow-up messages]** casilla y seleccione la plantilla de envío de seguimiento que se creó después de publicar el evento.

   ![](assets/message-center_follow-up-template.png)

1. En el contenido del mensaje de seguimiento, puede aprovechar el contenido del evento agregando campos de personalización.

   ![](assets/message-center_follow-up-content.png)

1. Busque los campos definidos al crear el evento seleccionando **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**. Consulte [Personalización de un mensaje](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)transaccional.

   ![](assets/message-center_follow-up-personalization.png)

   Esto significa que puede aprovechar el mismo contenido, incluidos los datos enriquecidos, que se utilizó la primera vez que se envió el evento, para crear un recordatorio personalizado y sencillo.

1. Guarde la actividad e inicie el flujo de trabajo.

Una vez iniciado el flujo de trabajo, todos los clientes que hayan recibido la notificación de abandono del carro de compras hace tres días pero que no la hayan abierto recibirán un mensaje de seguimiento basado en los mismos datos.

>[!NOTE]
>
>Si seleccionó la dimensión de objetivo al crear la configuración de evento, el mensaje de seguimiento también aprovechará la base de datos de marketing de Adobe Campaign. **[!UICONTROL Profile]** Consulte [Perfil de mensajes](../../channels/using/profile-transactional-messages.md)transaccionales.


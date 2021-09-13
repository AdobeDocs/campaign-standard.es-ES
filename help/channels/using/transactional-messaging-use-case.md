---
title: Caso de uso de la mensajería transaccional
description: Descubra un ejemplo completo de la funcionalidad de mensajería transaccional de Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 4%

---

# Caso de uso de la mensajería transaccional {#transactional-messaging-use-case}

En este ejemplo, desea utilizar la funcionalidad de mensajería transaccional de Adobe Campaign para enviar un correo electrónico de confirmación después de cada compra en su sitio web, identificando a sus clientes mediante su ID de CRM.

Los requisitos previos son los siguientes:

* Asegúrese de que el recurso **[!UICONTROL Profile]** se ha ampliado con un nuevo campo correspondiente al ID de CRM.

* Cree y publique un recurso personalizado correspondiente a las compras y vincúlelo al recurso **[!UICONTROL Profile]** . De este modo, podrá recuperar información de este recurso para enriquecer el contenido del mensaje.

Para obtener más información sobre cómo ampliar, crear y publicar recursos, consulte [esta sección](../../developing/using/key-steps-to-add-a-resource.md).

A continuación se presentan los pasos principales para implementar este caso de uso.

>[!NOTE]
>
>Para obtener una representación gráfica del proceso general de mensajería transaccional, consulte [este esquema](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Paso 1: Creación y publicación de la configuración de evento {#create-event-configuration}

1. Cree un nuevo evento utilizando el canal **[!UICONTROL Email]** . Consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Seleccione la dimensión de segmentación **[!UICONTROL Profile]** para crear un [mensaje transaccional basado en perfiles](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Defina los atributos que estarán disponibles para personalizar el mensaje transaccional. En este ejemplo, añada los campos &quot;CRM ID&quot; y &quot;Product identifier&quot;. Consulte [Definición de los atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer el contenido del mensaje con información sobre las compras del cliente, cree un enriquecimiento dirigido al recurso **[!UICONTROL Purchase]** . Consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Cree una condición de combinación entre el campo &quot;Identificador de producto&quot; que se agregó anteriormente al evento y el campo correspondiente del recurso **[!UICONTROL Purchase]** .

   ![](assets/message-center_usecase3.png)

1. Como es obligatorio para eventos basados en perfiles, también debe crear un enriquecimiento dirigido al recurso **[!UICONTROL Profile]** .

1. Cree una condición de unión entre el campo &quot;CRM ID&quot; que se agregó anteriormente al mensaje y el campo correspondiente del recurso **[!UICONTROL Profile]** que ha ampliado. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. En la sección **[!UICONTROL Targeting enrichment]** , seleccione el enriquecimiento en el recurso **[!UICONTROL Profile]** , que se utilizará como destinatario de mensaje durante la ejecución del envío.

   ![](assets/message-center_usecase5.png)

1. Previsualice y publique el evento. Consulte [Vista previa y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Paso 2: Editar y publicar el mensaje transaccional {#create-transactional-message}

1. Vaya al mensaje transaccional que se creó automáticamente al publicar el evento. Consulte [Acceso a mensajes transaccionales](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Edite y personalice el mensaje. Consulte [Edición de un mensaje transaccional de perfil](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. A través de la reconciliación con el campo &quot;CRM ID&quot; que agregó al recurso **[!UICONTROL Profile]** , tiene acceso directo a toda la información de perfil para [personalizar](../../designing/using/personalization.md#inserting-a-personalization-field) su mensaje.

   ![](assets/message-center_usecase6.png)

1. Mediante la reconciliación con el campo &quot;Identificador de producto&quot;, puede enriquecer el contenido del mensaje con información sobre las compras del cliente añadiendo cualquier campo del recurso **[!UICONTROL Purchase]** .

   ![](assets/message-center_usecase7.png)

   Para ello, seleccione **[!UICONTROL Insert personalization field]** en la barra de herramientas contextual. En el nodo **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**, abra el nodo correspondiente al recurso personalizado **[!UICONTROL Purchase]** y seleccione cualquier campo.

1. Puede probar el mensaje con un perfil de prueba específico. Consulte [Prueba de un mensaje transaccional](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. Una vez que el contenido esté listo, guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Paso 3: Integración del activador de eventos {#integrate-event-trigger}

Integre el evento en el sitio web. Consulte [Integrar el activador de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Paso 4: Envío de mensajes {#message-delivery}

Una vez que se han realizado todos estos pasos, tan pronto como un cliente compra productos de su sitio web, recibe un correo electrónico de confirmación personalizado que incluye información sobre su compra.

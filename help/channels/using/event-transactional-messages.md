---
title: Mensajes transaccionales de eventos
seo-title: Mensajes transaccionales de eventos
description: Mensajes transaccionales de eventos
seo-description: Obtenga información sobre cómo crear y publicar un mensaje transaccional de eventos.
page-status-flag: no activado nunca
uuid: d 747 feb 5-58 fb -4 e 12-a 176-404 f 0 eca 5391
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajes transaccionales
discoiquuid: 4 f 6317 a 1-9 dfe -4714-bc 1 c -393629 d 855 cd
context-tags: Deliverytransactionaltemplate, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e08b7e01956a9106937cb72ab790cb2e98999fcd

---


# Event transactional messages{#event-transactional-messages}

Puede enviar mensajes transaccionales de eventos dirigidos a un evento. Este tipo de mensajes transaccionales no contiene información de perfil: el objetivo de entrega se define según los datos contenidos en el evento.

Once you have created and published an event (the cart abandonment as explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send an transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que el evento active enviar un mensaje de transacción, debe personalizar el mensaje, luego probarlo y publicarlo.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. Los mensajes transaccionales de evento no contienen información de perfil, por lo que no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles). See [Fatigue rules](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Defining a test profile in a transactional message {#defining-a-test-profile-in-a-transactional-message}

Defina un perfil de prueba adaptado, que le permitirá obtener una vista previa del mensaje y enviar una prueba para comprobarla.

### Creating a test profile within the transactional message {#creating-a-test-profile-within-the-transactional-----------message}

1. To access the message that you created, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Cree un perfil de prueba que esté vinculado al evento.

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. Este es el contenido que se utilizará al obtener una vista previa del mensaje y cuando el perfil de prueba recibe la prueba.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >También puede introducir la información relacionada con la tabla de perfil. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Una vez creado, el perfil de prueba se especificará previamente en el mensaje transaccional. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Creating a test profile outside the transactional message {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. En este ejemplo, seleccione "Abandono del carro de compras (evtcartabandono)".
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Guarde los cambios.

Ahora puede acceder al mensaje que ha creado y seleccionar el perfil de prueba actualizado.

**Temas relacionados:**

* [Administración de perfiles de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Definición de audiencias](../../audiences/using/creating-audiences.md)

## Personalizing a transactional message {#personalizing-a-transactional-message}

Para configurar la personalización en un mensaje de transacción, siga los pasos a continuación:

1. Click the **[!UICONTROL Content]** block to modify your message's subject and content. Para este ejemplo, importe una plantilla HTML que contenga imágenes, la hoja de estilo y un archivo HTML. Importing HTML templates is presented in the [Loading an existing content](../../designing/using/selecting-an-existing-content.md) section.

   ![](assets/message-center_6.png)

1. Introduzca el contenido del mensaje. En este ejemplo, hemos agregado tres campos de personalización: apellido, último producto consultado, cantidad total del carrito. El vínculo al carro abandonado es un vínculo a una dirección URL externa que redireccionará a la persona a su carro de compras. Este parámetro no se administra en Adobe Campaign.

   To add fields that you defined when you created your event (see [Configuring an event](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)), insert a personalization field in the message content. You can find the fields by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer el contenido del mensaje, agregue campos seleccionándolos en la tabla con la que haya vinculado el evento. In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table.

   ![](assets/message-center_7-enrichment.png)

   The steps for inserting a personalization field are detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

   ![](assets/message-center_8.png)

1. Previsualice el mensaje seleccionando el perfil definido para este evento.

   The steps for previewing a message are detailed in the [Previewing messages](../../sending/using/preparing-the-send.md) section.

   ![](assets/message-center_9.png)

   Puede comprobar que los campos de personalización coinciden con la información introducida en el perfil de prueba. For more on this, see [Defining a test profile in a transactional message](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

Puede crear listados de productos que hagan referencia a una o varias colecciones de datos en el contenido de un correo electrónico de transacción. Por ejemplo: en un mensaje de correo electrónico de abandono del carro de compras puede incluir una lista de todos los productos que estaban en el carro de compras de los usuarios cuando abandonaron el sitio Web, con una imagen, el precio y un vínculo a cada producto.

>[!CAUTION]
>
>Product listings are only available when editing transactional email messages through the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) interface.

Para agregar una lista de productos abandonados en un mensaje de transacción, siga los pasos a continuación.

También puede ver un conjunto de vídeos que explican los pasos necesarios para configurar los listados de productos en un correo electrónico de transacción. For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaign no admite listados de productos anidados, lo que significa que no puede incluir una lista de productos dentro de otra.

### Defining a product listing {#defining-a-product-listing}

Antes de poder utilizar una lista de productos en un mensaje de transacción, debe definir en el nivel de evento la lista de productos y los campos de cada producto de la lista que desee mostrar. For more on this, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Arrastre y suelte un componente de estructura en el espacio de trabajo. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

   Por ejemplo, seleccione un componente de estructura de una columna y agregue un componente de texto, un componente de imagen y un componente de botón. For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Seleccione cómo se mostrarán los elementos de la colección:

   * **[!UICONTROL Row]**: horizontalmente, lo que significa cada elemento en una fila debajo del otro.
   * **[!UICONTROL Column]**: verticalmente, es decir, cada elemento al lado de otro en la misma fila.
   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). Al editar la lista de productos, rellene únicamente la primera columna: las demás columnas no se tendrán en cuenta. For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Seleccione la recopilación de datos que creó al configurar el evento relacionado con el mensaje de transacción. You can find it under the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   Por ejemplo, si selecciona 2, el primer elemento de la colección no se mostrará en el correo electrónico. La lista de productos comenzará en el segundo elemento.

1. Seleccione el número máximo de elementos que se mostrarán en la lista.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

Para mostrar una lista de productos procedentes del evento vinculado al correo electrónico de transacción, siga los pasos a continuación.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   El campo de personalización que ha seleccionado ahora se muestra en el panel Configuración.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   El campo de personalización que ha seleccionado ahora se muestra en la posición deseada en el contenido de correo electrónico.

1. Proceda de forma similar para insertar el precio.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Por razones de seguridad, asegúrese de insertar el campo de personalización dentro de un vínculo comenzando con un nombre de dominio estático adecuado.

   ![](assets/message-center_loop_link_select.png)

   El campo de personalización que ha seleccionado ahora se muestra en el panel Configuración.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Arrastre uno o varios componentes de contenido y edítelos según sea necesario.

   ![](assets/message-center_loop_fallback.png)

   El contenido de reserva se mostrará si la colección está vacía cuando se activa el evento, por ejemplo, si un cliente no tiene nada en el carro de compras.

1. En el panel Configuración, edite los estilos para la lista de productos. For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. Obtenga una vista previa del correo electrónico con un perfil de prueba vinculado al evento transaccional relevante y para el cual haya definido los datos de la colección. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Testing a transactional message {#testing-a-transactional-message}

Una vez guardado el mensaje de transacción, puede enviar una prueba para probarla.

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending a proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.

## Publishing a transactional message {#publishing-a-transactional-message}

Una vez que haya verificado el mensaje de transacción, puede publicarlo.

![](assets/message-center_12.png)

Ahora, en cuanto se activa el evento «Abandonos del carro de compras», se solicita automáticamente un mensaje que contiene el título y el apellido del destinatario, la dirección URL del carro, el último producto consultado o una lista de productos si se ha definido una lista de productos y la cantidad total del carro que se enviará.

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. See [Reports](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspending a transactional message publication {#suspending-a-transactional-message-publication}

You can suspend publishing your transactional message by using the **[!UICONTROL Pause]** button, for example, to modify the data contained in the message. Por lo tanto, los eventos ya no se procesan, sino que se mantienen en cola en la base de datos de Adobe Campaign.

The queued events are kept during a period of time that is defined in the REST API (see [REST API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)) or in the trigger event if you are using the Triggers core service (see [Working with Campaign and Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. Ahora contienen todas las modificaciones realizadas mientras se suspendía la publicación de la plantilla.

## Unpublishing a transactional message {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created. Ahora, incluso si el evento se activa a través del sitio web, los mensajes correspondientes no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>Para volver a publicar el mensaje, debe volver a la configuración del evento correspondiente, publicarlo y publicarlo. For more on this, see [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

Si cancela un mensaje de transacción pausado, es posible que tenga que esperar hasta 24 horas para poder publicarlo de nuevo. This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue. The steps for pausing a message are detailed in the [Suspending a transactional message publication](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication) section.

The **[!UICONTROL Database cleanup]** workflow, which runs every day at 4am, is accessible through **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]**.

## Deleting a transactional message {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

By selecting a transactional message, you can delete it with the **[!UICONTROL Delete element]** button even if it has already been published. Sin embargo, la eliminación de un mensaje de transacción solo se puede realizar bajo determinadas condiciones:

* **Mensajes transaccionales**: Para eliminar un mensaje de transacción, el mensaje debe cancelarse su publicación y no estar en pausa.

   Si se cancela la publicación del mensaje de transacción, la configuración del evento también debe cancelarse para eliminar correctamente el mensaje transaccional, a menos que otro mensaje de transacción esté vinculado al evento correspondiente. For more information on how to unpublish a transactional message, refer to this [section](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >Al eliminar un mensaje de transacción que ya ha enviado notificaciones, también se eliminarán los registros de envío y seguimiento.

* **Mensajes transaccionales de una plantilla de evento predeterminada (mensajes transaccionales internos)**: Para eliminar un mensaje de transacción interno, el mensaje debe cancelarse su publicación y no estar en pausa.

   No debe ser el único mensaje transaccional en el evento, sino que otros mensajes deben vincularse al evento correspondiente.

## Transactional message retry process {#transactional-message-retry-process}

Un mensaje transaccional temporal está sujeto a reintentos automáticos que se realizan hasta que caduca la entrega. For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Cuando no se envía un mensaje de transacción, hay dos sistemas de reintentos:

* En el nivel de mensaje de transacción, un mensaje transaccional puede fallar antes de que se asigne el evento a una entrega de ejecución, lo que significa entre la recepción del evento y la preparación de la entrega. See [Event processing retry process](../../channels/using/event-transactional-messages.md#event-processing-retry-process).
* En el nivel de proceso de envío, una vez que el evento se ha asignado a una entrega de ejecución, el mensaje transaccional puede fallar debido a un error temporal. See [Message sending retry process](../../channels/using/event-transactional-messages.md#message-sending-retry-process).

### Event processing retry process {#event-processing-retry-process}

Si el evento no se puede asignar a una entrega de ejecución, se aplazará el procesamiento de sucesos. A continuación, se realizan reintentos hasta que se asigna a una nueva entrega de ejecución.

>[!NOTE]
>
>Un evento aplazado no aparece en el mensaje transaccional que envía registros, porque aún no está asignado a una entrega de ejecución.

Por ejemplo: el evento no se pudo asignar a una entrega de ejecución porque su contenido no era correcto, hubo un problema con los derechos de acceso o la marca, se detectó un error en la aplicación de reglas de tipología, etc. En este caso, puede pausar el mensaje, editarlo para solucionar el problema y publicarlo de nuevo. El sistema de reintento lo asignará a una nueva entrega de ejecución.

### Message sending retry process {#message-sending-retry-process}

Una vez que el evento se ha asignado a una entrega de ejecución, el mensaje transaccional puede fallar debido a un error temporal, si el buzón de correo del destinatario está lleno. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Cuando se asigna un evento a una entrega de ejecución, aparece en los registros de envío de esta entrega de ejecución y solo en este momento. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**Envío de registros de registros**

En el proceso de reintento, los registros de envío de la nueva entrega de ejecución no se actualizan inmediatamente (la actualización se realiza a través de un flujo de trabajo programado). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Entrega de ejecución fallida**

No se puede detener una entrega de ejecución. Sin embargo, si falla la entrega de ejecución actual, se crea una nueva tan pronto como se recibe un nuevo evento y se procesan todos los nuevos eventos mediante esta nueva entrega de ejecución. No se procesa ningún evento nuevo mediante la entrega de ejecución fallida.

Si algunos eventos ya asignados a una entrega de ejecución se han aplazado y se produce un error en la entrega, el sistema de reintento no asigna los eventos aplazados a la nueva entrega de ejecución, lo que significa que se pierden estos eventos.

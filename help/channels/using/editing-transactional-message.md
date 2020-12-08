---
solution: Campaign Standard
product: campaign
title: Mensajes transaccionales de eventos
description: Aprenda a crear y publicar un mensaje transaccional de evento.
page-status-flag: never-activated
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: caa41d6c727385bd6e77f64750872f191a5ad040
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 60%

---


# Edición de un mensaje transaccional {#editing-transactional-message}

Una vez creado y publicado un evento<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->, el mensaje transaccional correspondiente se crea automáticamente.

Los pasos para configurar y publicar el evento se presentan en la sección [Configuración de un evento transaccional](../../channels/using/configuring-transactional-event.md) y [Publicación de un evento transaccional](../../channels/using/publishing-transactional-event.md).

A continuación se describen los pasos para acceder, editar y personalizar este mensaje.

>[!IMPORTANT]
>
>Solo los usuarios con la función [Administración](../../administration/using/users-management.md#functional-administrators) pueden acceder y editar mensajes transaccionales.

Una vez que el mensaje esté listo, se puede probar y publicar. Consulte [Prueba de la vida útil de un mensaje transaccional](../../channels/using/testing-transactional-message.md) y [Mensaje transaccional](../../channels/using/publishing-transactional-message.md).

## Acceso a mensajes transaccionales {#accessing-transactional-messages}

Para acceder al mensaje transaccional que ha creado:

1. Haga clic en el logotipo **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda.
1. Seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Haga clic en el mensaje que desee para editarlo.

   ![](assets/message-center_message-board.png)

También puede acceder directamente a un mensaje transaccional a través del vínculo ubicado en el área izquierda de la pantalla de configuración del evento correspondiente. Consulte [Vista previa y publicación de un evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

## Personalización de un mensaje transaccional {#personalizing-a-transactional-message}

Para editar y personalizar un mensaje transaccional, siga los pasos a continuación.

>[!NOTE]
>
>En esta sección se describe cómo editar un mensaje transaccional **basado en eventos**. Las características específicas del mensaje transaccional **basado en perfiles** se detallan [a3/>.](#profile-transactional-message-specificities)
>
>Los pasos de configuración para crear un mensaje transaccional basado en eventos se presentan en [esta sección](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).

Por ejemplo: desea enviar una notificación a los usuarios del sitio web que han agregado productos al carro de compras y que abandonan el sitio sin pasar por sus compras. Este ejemplo se presenta en la sección [Principio operativo de mensajería transaccional](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle).

1. Haga clic en el bloque **[!UICONTROL Content]** para modificar el asunto y el contenido del mensaje. Para este ejemplo, seleccione cualquier plantilla que contenga imágenes y texto. Para obtener más información sobre las plantillas de contenido de correo electrónico, consulte [Diseño de correos electrónicos con plantillas](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Añada un asunto y edite el contenido del mensaje para adaptarlo a sus necesidades.

   >[!NOTE]
   >
   >El vínculo al carro de compras abandonado es un vínculo a una dirección URL externa que redirecciona a la persona al carro de compras. Este parámetro no se administra en Adobe Campaign.

1. En este ejemplo, desea añadir tres campos que definió al [crear el evento](../../channels/using/configuring-transactional-event.md): nombre, último producto consultado, cantidad total del carro de compras. Para ello, [inserte un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field) en el contenido del mensaje.

1. Vaya a esos campos seleccionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. También puede enriquecer el contenido del mensaje. Para ello, agregue campos de la tabla que vinculó a la configuración de evento (consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)). En este ejemplo, seleccione el campo **[!UICONTROL Title (salutation)]** de la tabla **[!UICONTROL Profile]** a través de **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserte todos los campos necesarios.

   ![](assets/message-center_8.png)

1. Para obtener una vista previa del mensaje, seleccione el perfil que ha definido para este evento.

   Los pasos para obtener una vista previa de un mensaje se detallan en la sección [Vista previa de mensajes](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Puede comprobar que los campos de personalización coinciden con la información introducida en el perfil de prueba. Para obtener más información sobre esto, consulte [Definición de un perfil de prueba específico](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).

## Uso de listas de productos en un mensaje transaccional {#using-product-listings-in-a-transactional-message}

Al editar el contenido de un correo electrónico transaccional, puede crear listas de productos que hagan referencia a una o más colecciones de datos. Por ejemplo: en un correo electrónico de abandono del carro de compras, puede incluir una lista de todos los productos que estaban en el carro de compras de los usuarios cuando salieron del sitio web, con una imagen, el precio y un vínculo a cada producto.

>[!IMPORTANT]
>
>Los listados de productos solo están disponibles para el canal de correo electrónico, al editar contenido de correo electrónico transaccional a través de la interfaz [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Para añadir una lista de productos abandonados en un mensaje transaccional, siga los pasos a continuación.

También puede ver [este conjunto de videos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails) explicando los pasos necesarios para configurar los listados de productos en un correo electrónico transaccional.

>[!NOTE]
>
>Adobe Campaign no admite listas de productos anidadas, lo que significa que no puede incluir una lista de productos dentro de otra.

### Definición de una lista de productos {#defining-a-product-listing}

Antes de poder usar una lista de productos en un mensaje transaccional, debe definir a nivel de evento la lista de productos y los campos de cada producto de la lista que desee mostrar. Para obtener más información, consulte [Definición de colecciones de datos](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. En el mensaje transaccional, haga clic en el bloque **[!UICONTROL Content]** para modificar el contenido del correo electrónico.
1. Arrastre y suelte un componente de estructura en el espacio de trabajo. Para obtener más información sobre esto, consulte [Definición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Por ejemplo, seleccione un componente de estructura de una columna y añada un componente de texto, un componente de imagen y un componente de botón. Para obtener más información sobre esto, consulte [Uso de componentes de contenido](../../designing/using/designing-from-scratch.md#about-content-components).

1. Seleccione el componente de estructura que acaba de crear y haga clic en el icono **[!UICONTROL Enable product listing]** de la barra de herramientas contextual.

   ![](assets/message-center_loop_create.png)

   El componente de estructura se resalta con un marco naranja y los ajustes de **[!UICONTROL Product listing]** se muestran en la paleta izquierda. 

   ![](assets/message-center_loop_palette.png)

1. Seleccione cómo se mostrarán los elementos de la recopilación:

   * **[!UICONTROL Row]**: horizontalmente; es decir, cada elemento de una fila debajo de la otra.
   * **[!UICONTROL Column]**: verticalmente; es decir, cada elemento está junto al otro en la misma fila.

   >[!NOTE]
   >
   >La opción **[!UICONTROL Column]** solo está disponible cuando se utiliza un componente de estructura de varias columnas (**[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** y **[!UICONTROL 4:4 column]**). Al editar la lista de productos, rellene solo la primera columna: las demás columnas no se tendrán en cuenta. Para obtener más información sobre la selección de componentes de estructura, consulte [Definición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleccione la recopilación de datos que ha creado al configurar el evento relacionado con el mensaje transaccional. Puede encontrarlo en el nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Para obtener más información sobre la configuración del evento, consulte [Definición de colecciones de datos](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Utilice la lista desplegable **[!UICONTROL First item]** para seleccionar qué elemento será el inicio de la lista mostrada en el correo electrónico.

   Por ejemplo, si selecciona 2, el primer elemento de la recopilación no se muestra en el mensaje de correo electrónico. La lista de productos comienza con el segundo artículo.

1. Seleccione el número máximo de elementos que se mostrarán en la lista.

   >[!NOTE]
   >
   >Si desea que los elementos de la lista se muestren verticalmente (**[!UICONTROL Column]**), el número máximo de elementos queda limitado según el componente de estructura seleccionado (2, 3 o 4 columnas). Para obtener más información sobre la selección de componentes de estructura, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Rellenar el listado de productos {#populating-the-product-listing}

Para mostrar una lista de productos procedentes del evento vinculado al correo electrónico de transacción, siga los pasos a continuación.

Para obtener más información sobre la creación de una recopilación y los campos relacionados al configurar el evento, consulte [Definición de colecciones de datos](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Seleccione el componente de imagen que ha insertado, seleccione **[!UICONTROL Enable personalization]** y haga clic en el lápiz en el panel Configuración.

   ![](assets/message-center_loop_image.png)

1. Seleccione **[!UICONTROL Add personalization field]** en la ventana **[!UICONTROL Image source URL]** que se abrirá.

   En el nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra el nodo correspondiente a la recopilación que ha creado (aquí **[!UICONTROL Product list]**) y seleccione el campo de imagen que ha definido (aquí **[!UICONTROL Product image]**). Haga clic en **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   El campo de personalización que ha seleccionado ahora se muestra en el panel Configuración.

1. En la posición deseada, seleccione **[!UICONTROL Insert personalization field]** en la barra de herramientas contextual.

   ![](assets/message-center_loop_product.png)

1. En el nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra el nodo correspondiente a la recopilación que ha creado (aquí **[!UICONTROL Product list]**) y seleccione el campo que ha creado (aquí **[!UICONTROL Product name]**). Haga clic en **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   El campo de personalización que ha seleccionado ahora se muestra en la posición deseada en el contenido del correo electrónico.

1. Proceda de forma similar para insertar el precio.
1. Seleccione texto y haga clic en **[!UICONTROL Insert link]** en la barra de herramientas contextual.

   ![](assets/message-center_loop_link_insert.png)

1. Seleccione **[!UICONTROL Add personalization field]** en la ventana **[!UICONTROL Insert link]** que se abrirá.

   En el nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra el nodo correspondiente a la recopilación que ha creado (aquí **[!UICONTROL Product list]**) y seleccione el campo URL que ha creado (aquí **[!UICONTROL Product URL]**). Haga clic en **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Por motivos de seguridad, asegúrese de insertar el campo de personalización dentro de un vínculo que comience por un nombre de dominio estático adecuado.

   ![](assets/message-center_loop_link_select.png)

   El campo de personalización que ha seleccionado ahora se muestra en el panel Configuración.

1. Seleccione el componente de estructura en el que se aplica la lista de productos y seleccione **[!UICONTROL Show fallback]** para definir un contenido predeterminado.

   ![](assets/message-center_loop_fallback_show.png)

1. Arrastre uno o varios componentes de contenido y edítelos según sea necesario.

   ![](assets/message-center_loop_fallback.png)

   El contenido de reserva se muestra si la recopilación está vacía cuando se activa el evento, por ejemplo, si un cliente no tiene nada en el carro de compras.

1. En el panel Configuración, edite los estilos de la lista de productos. Para obtener más información sobre esto, consulte [Administración de estilos de correo electrónico](../../designing/using/styles.md).
1. Vista previa del correo electrónico mediante un perfil de prueba vinculado al evento transaccional relevante y para el que se han definido datos de recopilación. Por ejemplo, añada la siguiente información en la sección **[!UICONTROL Event data]** del perfil de prueba que desee utilizar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obtener más información sobre la definición de un perfil de prueba en un mensaje transaccional, consulte [esta sección](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).

## Especificidades de mensaje transaccional basadas en perfiles {#profile-transactional-message-specificities}

Puede enviar mensajes transaccionales en función de los perfiles de mercadotecnia del cliente, lo que le permite aprovechar toda la información de perfil para personalizar el contenido del mensaje, utilizar el vínculo baja y aplicar reglas de tipología de mercadotecnia como [reglas de fatiga](../../sending/using/fatigue-rules.md).

* Para obtener más información sobre las diferencias entre los mensajes transaccionales basados en eventos y los basados en perfiles, consulte [esta sección](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types).

* Los pasos de configuración para crear un mensaje transaccional basado en perfiles se detallan en [esta sección](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

<!--### Editing a profile transactional message {#editing-profile-transactional-message}-->

Los pasos para crear, editar y personalizar un mensaje transaccional de perfil son los mismos que para un mensaje transaccional de evento.

Las diferencias se enumeran a continuación.

1. [Vaya al mensaje transaccional que se creó para editarlo.](#accessing-transactional-messages)
1. En el mensaje transaccional, haga clic en la sección **[!UICONTROL Content]**. Además de las plantillas de correo electrónico transaccionales, también puede elegir cualquier plantilla de correo electrónico dirigida al recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleccione la plantilla de correo electrónico predeterminada. Al igual que todos los correos electrónicos de marketing, incluye un **vínculo baja**.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Para obtener más información sobre las plantillas, consulte [esta sección](../../designing/using/using-reusable-content.md#content-templates).

1. Además, a diferencia de las configuraciones basadas en eventos en tiempo real, tiene **acceso directo a toda la información de perfil** para personalizar su mensaje. Puede agregar [campos de personalización](../../designing/using/personalization.md#inserting-a-personalization-field) como lo haría con cualquier otro correo electrónico de mercadotecnia estándar.

1. Guarde los cambios antes de publicar el mensaje. Para obtener más información, consulte [Publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

<!--### Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the latest execution delivery.

   An **execution delivery** is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

>[!NOTE]
>
>For more information on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)
* [About typologies and typology rules](../../sending/using/about-typology-rules.md)-->

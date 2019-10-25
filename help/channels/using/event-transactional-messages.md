---
title: Mensajes transaccionales de eventos
seo-title: Mensajes transaccionales de eventos
description: Mensajes transaccionales de eventos
seo-description: Obtenga información sobre cómo crear y publicar un mensaje transaccional de eventos.
page-status-flag: nunca activado
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: transaccional-mensajería
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Mensajes transaccionales de eventos{#event-transactional-messages}

Puede enviar mensajes transaccionales de eventos dirigidos a un evento. Este tipo de mensajes transaccionales no contiene información de perfil: el objetivo de entrega está definido por los datos contenidos en el propio evento.

Una vez creado y publicado un evento (el abandono del carro de compras tal como se explica en [esta sección](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), el mensaje transaccional correspondiente se crea automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transaccional.

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe formar parte del grupo de **[!UICONTROL Administrators (all units)]** seguridad.
>
>Los mensajes transaccionales de eventos no contienen información de perfil, por lo tanto no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles). Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Definición de un perfil de prueba en un mensaje transaccional {#defining-a-test-profile-in-a-transactional-message}

Defina un perfil de prueba adaptado, que le permitirá previsualizar el mensaje y enviar una prueba para comprobarlo.

### Creación de un perfil de prueba dentro del mensaje transaccional {#creating-a-test-profile-within-the-transactional-----------message}

1. Para acceder al mensaje que ha creado, haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Cree un perfil de prueba que esté vinculado al evento.

   ![](assets/message-center_test-profile.png)

1. Especifique la información que desea enviar en formato JSON en la **[!UICONTROL Event data used for personalization]** sección. Este es el contenido que se utilizará al obtener una vista previa del mensaje y cuando el perfil de prueba reciba la prueba.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >También puede introducir la información relacionada con la tabla de perfil. Consulte [Enriquecimiento del contenido](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)de mensajes transaccionales.

1. Una vez creado, el perfil de prueba se especificará previamente en el mensaje transaccional. Haga clic en el **[!UICONTROL Test profiles]** bloque del mensaje para comprobar el objetivo de la prueba.

   ![](assets/message-center_5.png)

### Creación de un perfil de prueba fuera del mensaje transaccional {#creating-a-test-profile-outside-the-transactional-----------message}

También puede crear un nuevo perfil de prueba o utilizar uno que ya exista en el **[!UICONTROL Test profiles]** menú.

1. Haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la esquina superior izquierda, luego seleccione **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. En la **[!UICONTROL Event]** sección de la página del perfil de prueba que ha elegido, seleccione el evento que acaba de crear. En este ejemplo, seleccione "Abandono del carro de compras (EVTcartAbandonment)".
1. Especifique la información que desea enviar en formato JSON en el cuadro de **[!UICONTROL Event data]** texto.

   ![](assets/message-center_3.png)

1. Guarde los cambios.

Ahora puede acceder al mensaje que ha creado y seleccionar el perfil de prueba actualizado.

**Temas relacionados:**

* [Administración de perfiles de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Definición de audiencias](../../audiences/using/creating-audiences.md)

## Personalización de un mensaje transaccional {#personalizing-a-transactional-message}

Para configurar la personalización en un mensaje transaccional, siga los pasos a continuación:

1. Haga clic en el **[!UICONTROL Content]** bloque para modificar el asunto y el contenido del mensaje. Para este ejemplo, seleccione cualquier plantilla que contenga imágenes y texto. Para obtener más información sobre las plantillas de contenido de correo electrónico, consulte [Diseño con plantillas](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Agregue un asunto y edite el contenido del mensaje para adaptarlo a sus necesidades.

   >[NOTA]
   >
   >El vínculo al carro abandonado es un vínculo a una dirección URL externa que redireccionará a la persona al carro de compras. Este parámetro no se administra en Adobe Campaign.

1. En este ejemplo, desea agregar tres campos que definió al [crear el evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): nombre, último producto consultado, cantidad total del carro de compras. Para ello, [inserte un campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalización en el contenido del mensaje.

1. Vaya a esos campos a través **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer el contenido del mensaje, agregue campos seleccionándolos en la tabla con la que vinculó el evento. En nuestro ejemplo, seleccione el **[!UICONTROL Title (salutation)]** campo de la **[!UICONTROL Profile]** tabla a través de **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserte todos los campos necesarios.

   ![](assets/message-center_8.png)

1. Para previsualizar el mensaje, seleccione el perfil que definió para este evento.

   Los pasos para obtener una vista previa de un mensaje se detallan en la sección [Vista previa de mensajes](../../sending/using/previewing-messages.md) .

   ![](assets/message-center_9.png)

   Puede comprobar que los campos de personalización coinciden con la información introducida en el perfil de prueba. Para obtener más información sobre esto, consulte [Definición de un perfil de prueba en un mensaje](#defining-a-test-profile-in-a-transactional-message)transaccional.

## Uso de listados de productos en un mensaje transaccional {#using-product-listings-in-a-transactional-message}

Puede crear listas de productos que hagan referencia a una o varias colecciones de datos en el contenido de un correo electrónico transaccional. Por ejemplo: en un correo electrónico de abandono del carro de compras puede incluir una lista de todos los productos que estaban en el carro de compras de los usuarios cuando salieron del sitio web, con una imagen, el precio y un vínculo a cada producto.

>[!CAUTION]
>
>Las listas de productos solo están disponibles cuando se editan mensajes de correo electrónico transaccionales a través de la interfaz de [Email Designer](../../designing/using/overview.md#email-designer) .

Para agregar una lista de productos abandonados en un mensaje transaccional, siga los pasos a continuación.

También puede ver un conjunto de vídeos en los que se explican los pasos necesarios para configurar las listas de productos en un mensaje de correo electrónico transaccional. For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaign no admite listados de productos anidados, lo que significa que no puede incluir una lista de productos dentro de otra.

### Definición de una lista de productos {#defining-a-product-listing}

Antes de poder utilizar una lista de productos en un mensaje transaccional, debe definir en el nivel de evento la lista de productos y los campos de cada producto de la lista que desee mostrar. Para obtener más información sobre esto, consulte [Definición de colecciones](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de datos.

1. En el mensaje transaccional, haga clic en el **[!UICONTROL Content]** bloque para modificar el contenido del correo electrónico.
1. Arrastre y suelte un componente de estructura en el espacio de trabajo. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.

   Por ejemplo, seleccione un componente de estructura de una columna y agregue un componente de texto, un componente de imagen y un componente de botón. Para obtener más información sobre esto, consulte [Adición de fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleccione el componente de estructura que acaba de crear y haga clic en el icono **[!UICONTROL Enable product listing]** de la barra de herramientas contextual.

   ![](assets/message-center_loop_create.png)

   El componente de estructura se resalta con un marco naranja y los ajustes se muestran en la paleta izquierda. **[!UICONTROL Product listing]**

   ![](assets/message-center_loop_palette.png)

1. Seleccione cómo se mostrarán los elementos de la colección:

   * **[!UICONTROL Row]**:: horizontalmente, es decir, cada elemento de una fila debajo de la otra.
   * **[!UICONTROL Column]**:: verticalmente, lo que significa que cada elemento está junto al otro en la misma fila.
   >[!NOTE]
   >
   >La **[!UICONTROL Column]** opción solo está disponible cuando se utiliza un componente de estructura de varias columnas ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** y **[!UICONTROL 4:4 column]** ). Al editar el listado de productos, rellene solo la primera columna: las demás columnas no se tendrán en cuenta. Para obtener más información sobre la selección de componentes de estructura, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.

1. Seleccione la recopilación de datos que creó al configurar el evento relacionado con el mensaje transaccional. Puede encontrarlo en el nodo **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** .

   ![](assets/message-center_loop_selection.png)

   Para obtener más información sobre la configuración del evento, consulte [Definición de colecciones](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de datos.

1. Utilice la lista desplegable **[!UICONTROL First item]** para seleccionar qué elemento iniciará la lista que se muestra en el correo electrónico.

   Por ejemplo, si selecciona 2, el primer elemento de la colección no se mostrará en el correo electrónico. La lista de productos comenzará en el segundo artículo.

1. Seleccione el número máximo de elementos que se mostrarán en la lista.

   >[!NOTE]
   >
   >Si desea que los elementos de la lista se muestren verticalmente ( **[!UICONTROL Column]** ), el número máximo de elementos estará limitado según el componente de estructura seleccionado (2, 3 o 4 columnas). Para obtener más información sobre la selección de componentes de estructura, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.

### Rellenar el listado de productos {#populating-the-product-listing}

Para mostrar una lista de productos procedentes del evento vinculado al correo electrónico de transacción, siga los pasos a continuación.

Para obtener más información sobre la creación de una colección y los campos relacionados al configurar el evento, consulte [Definición de colecciones](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de datos.

1. Seleccione el componente de imagen que insertó, seleccione **[!UICONTROL Enable personalization]** y haga clic en el lápiz en el panel Configuración.

   ![](assets/message-center_loop_image.png)

1. Seleccione **[!UICONTROL Add personalization field]** en la **[!UICONTROL Image source URL]** ventana que se abre.

   En el nodo **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** , abra el nodo correspondiente a la colección que ha creado (aquí **[!UICONTROL Product list]** ) y seleccione el campo de imagen que ha definido (aquí **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   El campo de personalización que seleccionó ahora se muestra en el panel Configuración.

1. En la posición deseada, seleccione **[!UICONTROL Insert personalization field]** en la barra de herramientas contextual.

   ![](assets/message-center_loop_product.png)

1. En el nodo **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** , abra el nodo correspondiente a la colección que ha creado (aquí **[!UICONTROL Product list]** ) y seleccione el campo que ha creado (aquí **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   El campo de personalización que ha seleccionado ahora se muestra en la posición deseada en el contenido del correo electrónico.

1. Proceda de forma similar para insertar el precio.
1. Seleccione texto y seleccione **[!UICONTROL Insert link]** en la barra de herramientas contextual.

   ![](assets/message-center_loop_link_insert.png)

1. Seleccione **[!UICONTROL Add personalization field]** en la **[!UICONTROL Insert link]** ventana que se abre.

   En el nodo **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** , abra el nodo correspondiente a la colección que ha creado (aquí **[!UICONTROL Product list]** ) y seleccione el campo URL que ha creado (aquí **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Por motivos de seguridad, asegúrese de insertar el campo de personalización dentro de un vínculo que comience por un nombre de dominio estático adecuado.

   ![](assets/message-center_loop_link_select.png)

   El campo de personalización que seleccionó ahora se muestra en el panel Configuración.

1. Seleccione el componente de estructura en el que se aplica la lista de productos y seleccione **[!UICONTROL Show fallback]** para definir un contenido predeterminado.

   ![](assets/message-center_loop_fallback_show.png)

1. Arrastre uno o varios componentes de contenido y edítelos según sea necesario.

   ![](assets/message-center_loop_fallback.png)

   El contenido de reserva se mostrará si la colección está vacía cuando se activa el evento, por ejemplo, si un cliente no tiene nada en el carro de compras.

1. En el panel Configuración, edite los estilos de la lista de productos. Para obtener más información sobre esto, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.
1. Obtenga una vista previa del correo electrónico mediante un perfil de prueba vinculado al evento transaccional relevante y para el que definió los datos de recopilación. Por ejemplo, agregue la siguiente información en la sección **[!UICONTROL Event data]** del perfil de prueba que desee utilizar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obtener más información sobre la definición de un perfil de prueba en un mensaje transaccional, consulte [esta sección](#defining-a-test-profile-in-a-transactional-message).

## Prueba de un mensaje transaccional {#testing-a-transactional-message}

Una vez guardado el mensaje transaccional, ahora puede enviar una prueba para probarlo.

![](assets/message-center_10.png)

Los pasos para enviar una prueba se detallan en la sección [Envío de una prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) .

## Publicación de un mensaje transaccional {#publishing-a-transactional-message}

Una vez que haya comprobado el mensaje transaccional, puede publicarlo.

![](assets/message-center_12.png)

Ahora, tan pronto como se activa el evento de "abandono del carro de compras", se muestra automáticamente un mensaje que contiene el título y los apellidos del destinatario, la dirección URL del carro de compras, el último producto consultado o una lista de productos si se ha definido una lista de productos y la cantidad total que se va a enviar.

Para acceder a los informes relacionados con su mensaje transaccional, utilice el **[!UICONTROL Reports]** botón . Consulte [Informes](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspensión de una publicación de mensajes transaccionales {#suspending-a-transactional-message-publication}

Puede suspender la publicación del mensaje de transacción utilizando el **[!UICONTROL Pause]** botón, por ejemplo, para modificar los datos contenidos en el mensaje. Por lo tanto, los eventos ya no se procesan, sino que se mantienen en una cola en la base de datos de Adobe Campaign.

Los eventos en cola se guardan durante un período de tiempo definido en la API de REST (consulte la documentación [de la API de](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)REST) o en el evento desencadenador si utiliza el servicio principal de activadores (consulte [Uso de Campaign y Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Al hacer clic en **[!UICONTROL Resume]**, se procesan todos los eventos en cola (siempre que no hayan caducado). Ahora contienen todas las modificaciones realizadas durante la suspensión de la publicación de la plantilla.

## Cancelación de la publicación de un mensaje transaccional {#unpublishing-a-transactional-message}

Al hacer clic en **[!UICONTROL Unpublish]** se puede cancelar la publicación de mensajes transaccionales, pero también la publicación del evento correspondiente, que elimina de la API de REST el recurso correspondiente al evento que creó anteriormente. Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>Para volver a publicar el mensaje, debe volver a la configuración del evento correspondiente, publicarlo y publicarlo. Para obtener más información sobre esto, consulte [Publicación de un mensaje](#publishing-a-transactional-message)transaccional.

Si cancela la publicación de un mensaje transaccional pausado, es posible que tenga que esperar hasta 24 horas para poder volver a publicarlo. Esto permite que el flujo de trabajo **[!UICONTROL Database cleanup]** limpie todos los eventos que se han enviado a la cola. Los pasos para pausar un mensaje se detallan en la sección [Suspender una publicación](#suspending-a-transactional-message-publication) de mensajes transaccionales.

Se puede acceder al **[!UICONTROL Database cleanup]** flujo de trabajo, que se ejecuta todos los días a las 4 de la mañana, a través de **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]**.

## Eliminación de un mensaje transaccional {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

Si selecciona un mensaje transaccional, puede eliminarlo con el **[!UICONTROL Delete element]** botón incluso si ya se ha publicado. Sin embargo, la eliminación de un mensaje transaccional solo se puede realizar bajo ciertas condiciones:

* **Mensajes** transaccionales: Para eliminar un mensaje transaccional, se debe cancelar la publicación del mensaje y no ponerlo en pausa.

   Si se deja de publicar el mensaje transaccional, también es necesario cancelar la publicación de la configuración del evento para eliminar correctamente el mensaje transaccional, a menos que otro mensaje transaccional esté vinculado al evento correspondiente. For more information on how to unpublish a transactional message, refer to this [section](#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >Al eliminar un mensaje transaccional que ya ha enviado notificaciones también se eliminarán los registros de envío y seguimiento.

* **Mensajes transaccionales de una plantilla de evento lista para usar (mensajes transaccionales internos)**: Para eliminar un mensaje transaccional interno, se debe cancelar la publicación del mensaje y no ponerlo en pausa.

   Tampoco debería ser el único mensaje transaccional en el evento, otros mensajes deben estar vinculados al evento correspondiente.

## Proceso de reintento de mensaje transaccional {#transactional-message-retry-process}

Un mensaje transaccional no entregado temporalmente está sujeto a reintentos automáticos que se realizan hasta que caduca la entrega. Para obtener más información sobre la duración de la entrega, consulte Parámetros [del período de](../../administration/using/configuring-email-channel.md#validity-period-parameters)validez.

Cuando no se puede enviar un mensaje transaccional, hay dos sistemas de reintentos:

* En el nivel de mensajería transaccional, un mensaje transaccional puede fallar antes de que el evento se asigne a una entrega de ejecución, lo que significa entre la recepción del evento y la preparación de la entrega. Consulte Proceso [de reintento](#event-processing-retry-process)de procesamiento de eventos.
* A nivel de proceso de envío, una vez que el evento se ha asignado a una entrega de ejecución, el mensaje transaccional puede fallar debido a un error temporal. Consulte [Proceso](#message-sending-retry-process)de reintento de envío de mensajes.

### Proceso de reintentos de procesamiento de eventos {#event-processing-retry-process}

Si no se puede asignar el evento a una entrega de ejecución, se pospone el procesamiento del evento. Los reintentos se realizan hasta que se asignan a una nueva entrega de ejecución.

>[!NOTE]
>
>Un evento pospuesto no aparece en los registros de envío de mensajes transaccionales, porque todavía no está asignado a una entrega de ejecución.

Por ejemplo, no se pudo asignar el evento a una entrega de ejecución porque su contenido no era correcto, había un problema con los derechos de acceso o la marca, se detectó un error al aplicar reglas de tipología, etc. En este caso, puede pausar el mensaje, editarlo para solucionar el problema y publicarlo de nuevo. El sistema de reintentos lo asignará a una nueva entrega de ejecución.

### Proceso de reintento de envío de mensajes {#message-sending-retry-process}

Una vez asignado el evento a una entrega de ejecución, el mensaje transaccional puede fallar debido a un error temporal, si el buzón del destinatario está lleno, por ejemplo. Para obtener más información sobre esto, consulte [Reintentos después de un error](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)temporal de entrega.

>[!NOTE]
>
>Cuando se asigna un evento a una entrega de ejecución, aparece en los registros de envío de esta entrega de ejecución y solo en este momento. Los envíos fallidos se muestran en la **[!UICONTROL Execution list]** ficha del mensaje transaccional.

### Limitaciones {#limitations}

**Envío de la actualización de registros**

En el proceso de reintento, los registros de envío de la nueva entrega de ejecución no se actualizan inmediatamente (la actualización se realiza mediante un flujo de trabajo programado). Significa que el mensaje podría estar en **[!UICONTROL Pending]** estado aunque el evento transaccional se haya procesado mediante la nueva entrega de ejecución.

**Error al ejecutar la entrega**

No puede detener una entrega de ejecución. Sin embargo, si se produce un error en la entrega de ejecución actual, se crea una nueva en cuanto se recibe un nuevo evento y todos los eventos nuevos se procesan mediante esta nueva entrega de ejecución. No se procesan nuevos eventos debido al error en la entrega de ejecución.

Si se han pospuesto algunos eventos ya asignados a una entrega de ejecución y se produce un error en dicha entrega, el sistema de reintentos no asigna los eventos pospuestos a la nueva entrega de ejecución, lo que significa que estos eventos se pierden.

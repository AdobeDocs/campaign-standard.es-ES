---
title: Mensajes transaccionales de eventos
description: Aprenda a crear y publicar un mensaje transaccional de evento.
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 762700893c913d9aea884d00438c84b39a800188
workflow-type: tm+mt
source-wordcount: '2478'
ht-degree: 100%

---


# Mensajes transaccionales de eventos{#event-transactional-messages}

Puede enviar mensajes transaccionales de eventos dirigidos a un evento. Este tipo de mensajes transaccionales no contiene información de perfil: el destinatario se define por los datos contenidos en el propio evento.

Una vez que haya creado y publicado un evento (el abandono del carro de compras como se explica en [esta sección](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), el mensaje transaccional correspondiente se crea automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje transaccional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de seguridad **[!UICONTROL Administrators (all units)]**.
>
>Los mensajes transaccionales de evento no contienen información sobre perfiles, por lo que no son compatibles con las normas de fatiga (incluso en el caso de un enriquecimiento con perfiles). Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md#choosing-the-channel).

## Definición de un perfil de prueba en un mensaje transaccional {#defining-a-test-profile-in-a-transactional-message}

Defina un perfil de prueba adaptado, que le permite obtener una vista previa del mensaje y enviar una prueba para comprobar que todo esté bien.

### Creación de un perfil de prueba dentro del mensaje transaccional {#creating-a-test-profile-within-the-transactional-----------message}

1. Para acceder al mensaje que ha creado, haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Cree un perfil de prueba que esté vinculado a su evento.

   ![](assets/message-center_test-profile.png)

1. Especifique la información que desea enviar en formato JSON en la sección **[!UICONTROL Event data used for personalization]**. Este es el contenido que se utiliza al obtener una vista previa del mensaje y cuando el perfil de prueba reciba la prueba.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >También puede introducir la información relativa a la tabla de perfiles. Consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Una vez creado, el perfil de prueba se especifica previamente en el mensaje transaccional. Haga clic en el bloque **[!UICONTROL Test profiles]** del mensaje para comprobar el destinatario de la prueba.

   ![](assets/message-center_5.png)

### Creación de un perfil de prueba fuera del mensaje transaccional {#creating-a-test-profile-outside-the-transactional-----------message}

También puede crear un nuevo perfil de prueba o utilizar uno que ya exista en el menú **[!UICONTROL Test profiles]**.

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. En la sección **[!UICONTROL Event]** de la página del perfil de prueba que ha elegido, seleccione el evento que acaba de crear. En este ejemplo, seleccione “Abandono del carro de compras (EVTcartAbandonment)”.
1. Especifique la información que desea enviar en formato JSON en el cuadro de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Guarde los cambios.

Ahora puede acceder al mensaje que ha creado y seleccionar el perfil de prueba actualizado.

**Temas relacionados:**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Definición de audiencias](../../audiences/using/creating-audiences.md)

## Personalización de un mensaje transaccional {#personalizing-a-transactional-message}

Para configurar la personalización en un mensaje transaccional, siga los pasos a continuación:

1. Haga clic en el bloque **[!UICONTROL Content]** para modificar el asunto y el contenido del mensaje. Para este ejemplo, seleccione cualquier plantilla que contenga imágenes y texto. Para obtener más información sobre las plantillas de contenido de correo electrónico, consulte [Diseño con plantillas](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Añada un asunto y edite el contenido del mensaje para adaptarlo a sus necesidades.

   >[!NOTE]
   >
   >El vínculo al carro de compras abandonado es un vínculo a una dirección URL externa que redirecciona a la persona al carro de compras. Este parámetro no se administra en Adobe Campaign.

1. En este ejemplo, desea añadir tres campos que definió al [crear el evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): nombre, último producto consultado, cantidad total del carro de compras. Para ello, [inserte un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field) en el contenido del mensaje.

1. Vaya a esos campos seleccionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer el contenido del mensaje, añada campos seleccionándolos en la tabla con la que vinculó el evento. En el ejemplo, seleccione el campo **[!UICONTROL Title (salutation)]** de la tabla **[!UICONTROL Profile]** seleccionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserte todos los campos necesarios.

   ![](assets/message-center_8.png)

1. Para obtener una vista previa del mensaje, seleccione el perfil que ha definido para este evento.

   Los pasos para obtener una vista previa de un mensaje se detallan en la sección [Vista previa de mensajes](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Puede comprobar que los campos de personalización coinciden con la información introducida en el perfil de prueba. Para obtener más información, consulte [Definición de un perfil de prueba en un mensaje transaccional](#defining-a-test-profile-in-a-transactional-message).

## Uso de listas de productos en un mensaje transaccional {#using-product-listings-in-a-transactional-message}

Puede crear listas de productos que hagan referencia a una o varias recopilaciones de datos en el contenido de un correo electrónico transaccional. Por ejemplo: en un correo electrónico de abandono del carro de compras puede incluir una lista de todos los productos que estaban en el carro de compras de los usuarios cuando salieron del sitio web, con una imagen, el precio y un vínculo a cada producto.

>[!IMPORTANT]
>
>Las listas de productos solo están disponibles cuando se editan mensajes de correo electrónico transaccionales a través de la interfaz del [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Para añadir una lista de productos abandonados en un mensaje transaccional, siga los pasos a continuación.

También puede ver un conjunto de vídeos en los que se explican los pasos necesarios para configurar las listas de productos en un mensaje de correo electrónico transaccional. Para obtener más información, consulte [esta página](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.translate.html).

>[!NOTE]
>
>Adobe Campaign no admite listas de productos anidadas, lo que significa que no puede incluir una lista de productos dentro de otra.

### Definición de una lista de productos {#defining-a-product-listing}

Antes de poder usar una lista de productos en un mensaje transaccional, debe definir a nivel de evento la lista de productos y los campos de cada producto de la lista que desee mostrar. Para obtener más información, consulte [Definición de colecciones de datos](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. En el mensaje transaccional, haga clic en el bloque **[!UICONTROL Content]** para modificar el contenido del correo electrónico.
1. Arrastre y suelte un componente de estructura en el espacio de trabajo. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Por ejemplo, seleccione un componente de estructura de una columna y añada un componente de texto, un componente de imagen y un componente de botón. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleccione el componente de estructura que acaba de crear y haga clic en el icono **[!UICONTROL Enable product listing]** de la barra de herramientas contextual.

   ![](assets/message-center_loop_create.png)

   El componente de estructura se resalta con un marco naranja y los ajustes de **[!UICONTROL Product listing]** se muestran en la paleta izquierda. 

   ![](assets/message-center_loop_palette.png)

1. Seleccione cómo se mostrarán los elementos de la recopilación:

   * **[!UICONTROL Row]**: horizontalmente; es decir, cada elemento de una fila debajo de la otra.
   * **[!UICONTROL Column]**: verticalmente; es decir, cada elemento está junto al otro en la misma fila.

   >[!NOTE]
   >
   >La opción **[!UICONTROL Column]** solo está disponible cuando se utiliza un componente de estructura de varias columnas (**[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** y **[!UICONTROL 4:4 column]**). Al editar la lista de productos, rellene solo la primera columna: las demás columnas no se tendrán en cuenta. Para obtener más información sobre la selección de componentes de estructura, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleccione la recopilación de datos que ha creado al configurar el evento relacionado con el mensaje transaccional. Puede encontrarlo en el nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Para obtener más información sobre la configuración del evento, consulte [Definición de colecciones de datos](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Utilice la lista desplegable **[!UICONTROL First item]** para seleccionar qué elemento será el inicio de la lista mostrada en el correo electrónico.

   Por ejemplo, si selecciona 2, el primer elemento de la recopilación no se muestra en el mensaje de correo electrónico. La lista de productos comienza con el segundo artículo.

1. Seleccione el número máximo de elementos que se mostrarán en la lista.

   >[!NOTE]
   >
   >Si desea que los elementos de la lista se muestren verticalmente (**[!UICONTROL Column]**), el número máximo de elementos queda limitado según el componente de estructura seleccionado (2, 3 o 4 columnas). Para obtener más información sobre la selección de componentes de estructura, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Rellenar el listado de productos {#populating-the-product-listing}

Para mostrar una lista de productos procedentes del evento vinculado al correo electrónico de transacción, siga los pasos a continuación.

Para obtener más información sobre la creación de una recopilación y los campos relacionados al configurar el evento, consulte [Definición de colecciones de datos](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

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

1. En el panel Configuración, edite los estilos de la lista de productos. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).
1. Vista previa del correo electrónico mediante un perfil de prueba vinculado al evento transaccional relevante y para el que se han definido datos de recopilación. Por ejemplo, añada la siguiente información en la sección **[!UICONTROL Event data]** del perfil de prueba que desee utilizar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obtener más información sobre la definición de un perfil de prueba en un mensaje transaccional, consulte [esta sección](#defining-a-test-profile-in-a-transactional-message).

## Prueba de un mensaje transaccional {#testing-a-transactional-message}

Una vez guardado el mensaje transaccional, ahora puede enviar una prueba para probarlo.

![](assets/message-center_10.png)

Los pasos para enviar una prueba se detallan en la sección [Envío de una prueba](../../sending/using/sending-proofs.md).

## Publicación de un mensaje transaccional {#publishing-a-transactional-message}

Una vez que haya comprobado el mensaje transaccional, puede publicarlo.

![](assets/message-center_12.png)

Ahora, tan pronto como se activa el evento “Abandono del carro de compras”, se mostrará automáticamente un mensaje que contiene el título y los apellidos del destinatario, la dirección URL del carro de compras, el último producto consultado o una lista de productos, si se ha definido una, y la cantidad total que se va a enviar.

Para acceder a los informes relacionados con su mensaje transaccional, utilice el botón **[!UICONTROL Reports]**. Consulte [Informes](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspender la publicación de un mensaje transaccional {#suspending-a-transactional-message-publication}

Puede suspender la publicación del mensaje transaccional utilizando el botón **[!UICONTROL Pause]**, por ejemplo, para modificar los datos contenidos en el mensaje. Por lo tanto, los eventos ya no se procesan, sino que se mantienen en cola en la base de datos de Adobe Campaign.

Los eventos en cola se mantienen durante un periodo de tiempo definido en la API de REST (consulte la [documentación de la API de REST](../../api/using/get-started-apis.md)) o en el evento de activación si utiliza el servicio principal de activadores (consulte [Uso de Campaign y activadores de Experience Cloud](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Al hacer clic en **[!UICONTROL Resume]**, se procesan todos los eventos en cola (siempre que no hayan caducado). Ahora contienen todas las modificaciones realizadas durante la suspensión de la publicación de la plantilla.

## Cancelación de la publicación de un mensaje transaccional {#unpublishing-a-transactional-message}

Al hacer clic en **[!UICONTROL Unpublish]** se puede cancelar la publicación del mensaje transaccional, pero también la publicación del evento correspondiente, que elimina de la API de REST el recurso correspondiente al evento que ha creado anteriormente.

![](assets/message-center_unpublish-template.png)

Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

>[!NOTE]
>
>Para volver a publicar el mensaje, debe volver a la configuración del evento correspondiente, publicarlo y, después, publicar el mensaje. Para obtener más información, consulte [Publicación de un mensaje transaccional](#publishing-a-transactional-message).

Si cancela la publicación de un mensaje transaccional en pausa, es posible que tenga que esperar hasta 24 horas para volver a publicarlo. Esto permite que el flujo de trabajo **[!UICONTROL Database cleanup]** limpie todos los eventos en cola.

Los pasos para pausar un mensaje se detallan en la sección [Suspender la publicación de un mensaje transaccional](#suspending-a-transactional-message-publication).

Se puede acceder al flujo de trabajo **[!UICONTROL Database cleanup]**, que se ejecuta todos los días a las 4 de la mañana, seleccionando **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

## Eliminación de un mensaje transaccional {#deleting-a-transactional-message}

Una vez que se ha cancelado la publicación de un mensaje transaccional, o si todavía no se ha publicado, puede eliminarlo de la lista de mensajes transaccionales. Para ello:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Pase el ratón sobre el mensaje que desee.
1. Haga clic en el botón **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

Sin embargo, la eliminación de un mensaje transaccional solo se puede realizar bajo determinadas condiciones:

* Asegúrese de que el mensaje transaccional está en estado **[!UICONTROL Draft]**, de lo contrario no podrá eliminarlo. El estado **[!UICONTROL Draft]** se aplica a un mensaje que aún no se ha publicado o cuya [publicación se ha cancelado](#unpublishing-a-transactional-message) (y no se ha [pausado](#suspending-a-transactional-message-publication)).

* **Mensajes transaccionales**: a menos que se vincule otro mensaje transaccional al evento correspondiente, si se cancela la publicación del mensaje, la configuración de evento también debe cancelarse para eliminar correctamente el mensaje transaccional. Para obtener más información, consulte [Cancelación de la publicación de un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >Al eliminar un mensaje transaccional que ya ha enviado notificaciones, también se eliminan sus registros de seguimiento y envíos.

* **Mensajes transaccionales de una plantilla de evento lista para usar (mensajes transaccionales internos)**: si un mensaje transaccional interno es el único asociado al evento interno correspondiente, no se puede eliminar. Primero debe crear otro mensaje transaccional duplicándolo o en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]**.

## Proceso de reintentos de un mensaje transaccional {#transactional-message-retry-process}

Un mensaje transaccional no entregado temporalmente está sujeto a reintentos automáticos que se realizan hasta que caduca el envío. Para obtener más información sobre la duración del envío, consulte [Parámetros del periodo de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Cuando no se puede enviar un mensaje transaccional, hay dos sistemas de reintentos:

* En el nivel de mensajería transaccional, un mensaje transaccional puede fallar antes de que el evento se asigne a un envío de ejecución; es decir, entre la recepción del evento y la preparación de este. Consulte [Proceso de reintentos del procesamiento de un evento](#event-processing-retry-process).
* A nivel de proceso de envío, una vez que el evento se ha asignado a un envío de ejecución, el mensaje transaccional puede fallar debido a un error temporal. Consulte [Proceso de reintentos del envío de mensajes](#message-sending-retry-process).

### Proceso de reintentos del procesamiento de un evento {#event-processing-retry-process}

Si el evento no se puede asignar a un envío de ejecución, se pospone el procesamiento del evento. Los reintentos se realizan hasta que se asignan a un nuevo envío de ejecución.

>[!NOTE]
>
>Un evento pospuesto no aparece en los registros de envío del mensaje transaccional, ya que todavía no está asignado a un envío de ejecución.

Por ejemplo, el evento no se ha podido asignar a un envío de ejecución porque su contenido no era correcto, había un problema con los derechos de acceso o la marca, se detectó un error al aplicar reglas de tipología, etc. En este caso, puede pausar el mensaje, editarlo para solucionar el problema y publicarlo de nuevo. El sistema de reintentos lo asigna a un nuevo envío de ejecución.

### Proceso de reintentos del envío de mensajes {#message-sending-retry-process}

Una vez asignado el evento a un envío de ejecución, el mensaje transaccional puede fallar debido a un error temporal, si el buzón del destinatario está lleno, por ejemplo. Para obtener más información, consulte [Reintentos después de un error temporal de entrega](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Cuando se asigna un evento a un envío de ejecución, aparece en los registros de este envío de ejecución y solo en este momento. Los envíos fallidos se muestran en la pestaña **[!UICONTROL Execution list]** del mensaje transaccional.

### Limitaciones {#limitations}

**Envío de la actualización de registros**

En el proceso de reintentos, los registros de envío del nuevo envío de ejecución no se actualizan inmediatamente (la actualización se realiza mediante un flujo de trabajo programado). Significa que el mensaje podría estar en estado **[!UICONTROL Pending]** aunque el nuevo envío de ejecución haya procesado el evento transaccional.

**Error en el envío de ejecución**

No se puede detener un envío de ejecución. Sin embargo, si falla el envío de ejecución actual, se crea uno nuevo en cuanto se recibe un nuevo evento y todos los eventos nuevos se procesan con este nuevo envío de ejecución. El envío de ejecución con errores no procesa eventos nuevos.

Si algunos eventos ya asignados a un envío de ejecución se han pospuesto y si ese envío de ejecución falla, el sistema de reintentos no asigna los eventos pospuestos al nuevo envío de ejecución, lo que significa que estos eventos se pierden.

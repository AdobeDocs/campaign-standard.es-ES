---
solution: Campaign Standard
product: campaign
title: Mensajes transaccionales de eventos
description: Aprenda a crear y publicar un mensaje transaccional de evento.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# Ciclo de vida del mensaje transaccional {#publishing-transactional-message}

Cuando el [mensaje transaccional](../../channels/using/editing-transactional-message.md) está listo para ser enviado, se puede publicar.

A continuación se detallan los pasos para probar, publicar, pausar, cancelar la publicación y eliminar un evento. En esta sección también se describe el proceso de reintentos de mensajes transaccionales.

## Proceso de publicación de mensajes transaccionales {#transactional-messaging-pub-process}

El gráfico siguiente ilustra el proceso general de publicación de mensajes transaccionales.

![](assets/message-center_pub-process.png)

Para obtener más información sobre la publicación de un mensaje transaccional, consulte [esta sección](#publishing-a-transactional-message).
Para obtener más información sobre la pausa de un mensaje transaccional, consulte [esta sección](#suspending-a-transactional-message-publication).
Para obtener más información sobre cómo cancelar la publicación de un mensaje transaccional, consulte [esta sección](#unpublishing-a-transactional-message).

Para obtener más información sobre cómo publicar y cancelar la publicación de un evento, consulte [esta sección](../../channels/using/publishing-transactional-event.md).

## Prueba de un mensaje transaccional {#testing-a-transactional-message}

Primero debe crear un perfil de prueba específico que le permita comprobar correctamente el mensaje transaccional.

### Definición de un perfil de prueba específico {#defining-specific-test-profile}

Defina un perfil de prueba que se vinculará a su evento, lo que le permitirá previsualización de su mensaje y enviar una prueba relevante.

1. En el panel de mensaje transaccional, haga clic en el botón **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Especifique la información que desea enviar en formato JSON en la sección **[!UICONTROL Event data used for personalization]**. Este es el contenido que se utiliza al obtener una vista previa del mensaje y cuando el perfil de prueba reciba la prueba.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >También puede introducir la información relativa a la tabla de perfiles. Consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->.

1. Una vez creado, el perfil de prueba se especificará previamente en el mensaje transaccional. Haga clic en el bloque **[!UICONTROL Test profiles]** del mensaje para comprobar el destinatario de la prueba.

   ![](assets/message-center_5.png)

También puede crear un nuevo perfil de prueba o utilizar uno que ya exista en el menú **[!UICONTROL Test profiles]**. Para ello:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. En la sección **[!UICONTROL Event]**, seleccione el evento que acaba de crear. En este ejemplo, seleccione “Abandono del carro de compras (EVTcartAbandonment)”.
1. Especifique la información que desea enviar en formato JSON en el cuadro de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Guarde los cambios.
1. Acceda al mensaje que ha creado y seleccione el perfil de prueba actualizado.

**Temas relacionados:**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Creación de audiencias](../../audiences/using/creating-audiences.md)

### Envío de una prueba {#sending-proof}

Una vez que haya creado uno o varios perfiles de prueba específicos y guardado el mensaje transaccional, puede enviar una prueba para probarlo.

![](assets/message-center_10.png)

Los pasos para enviar una prueba se detallan en la sección [Envío de pruebas](../../sending/using/sending-proofs.md).

## Publicación de un mensaje transaccional {#publishing-a-transactional-message}

Una vez que haya comprobado el mensaje transaccional, puede publicarlo.

![](assets/message-center_12.png)

Ahora, tan pronto como se activa el evento “Abandono del carro de compras”, se mostrará automáticamente un mensaje que contiene el título y los apellidos del destinatario, la dirección URL del carro de compras, el último producto consultado o una lista de productos, si se ha definido una, y la cantidad total que se va a enviar.

Para acceder a los informes relacionados con su mensaje transaccional, utilice el botón **[!UICONTROL Reports]**. Consulte [Informes dinámicos](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Suspender la publicación de un mensaje transaccional {#suspending-a-transactional-message-publication}

Puede suspender la publicación del mensaje transaccional utilizando el botón **[!UICONTROL Pause]**, por ejemplo, para modificar los datos contenidos en el mensaje. Por lo tanto, los eventos ya no se procesan, sino que se mantienen en cola en la base de datos de Adobe Campaign.

Los eventos en cola se mantienen durante un período de tiempo definido en la API de REST (consulte la [documentación de la API de REST](../../api/using/managing-transactional-messages.md) o en el evento de activación si está utilizando el servicio principal de Triggers (consulte [Acerca de Adobe Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Al hacer clic en **[!UICONTROL Resume]**, se procesan todos los eventos en cola (siempre que no hayan caducado). Ahora contienen todas las modificaciones realizadas durante la suspensión de la publicación de la plantilla.

### Cancelación de la publicación de un mensaje transaccional {#unpublishing-a-transactional-message}

Al hacer clic en **[!UICONTROL Unpublish]** se puede cancelar la publicación del mensaje transaccional, pero también la publicación del evento correspondiente, que elimina de la API de REST el recurso correspondiente al evento que ha creado anteriormente.

![](assets/message-center_unpublish-template.png)

Ahora, incluso si el evento se activa a través de su sitio web, los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.

>[!NOTE]
>
>Para volver a publicar el mensaje, debe volver a la configuración de evento correspondiente, [publicar el evento](../../channels/using/publishing-transactional-event.md) y luego [publicar el mensaje](#publishing-a-transactional-message).

Si cancela la publicación de un mensaje transaccional en pausa, es posible que tenga que esperar hasta 24 horas para volver a publicarlo. Esto permite que el flujo de trabajo **[!UICONTROL Database cleanup]** limpie todos los eventos en cola.

Los pasos para pausar un mensaje se detallan en la sección [Suspender la publicación de un mensaje transaccional](#suspending-a-transactional-message-publication).

Se puede acceder al flujo de trabajo **[!UICONTROL Database cleanup]**, que se ejecuta todos los días a las 4 de la mañana, seleccionando **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

### Eliminación de un mensaje transaccional {#deleting-a-transactional-message}

Una vez que se ha cancelado la publicación de un mensaje transaccional, o si todavía no se ha publicado, puede eliminarlo de la lista de mensajes transaccionales. Para ello:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Pase el ratón sobre el mensaje que desee.
1. Haga clic en el botón **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

Sin embargo, la eliminación de un mensaje transaccional solo se puede realizar bajo determinadas condiciones:

* Asegúrese de que el mensaje transaccional está en estado **[!UICONTROL Draft]**, de lo contrario no podrá eliminarlo. El estado **[!UICONTROL Draft]** se aplica a un mensaje que aún no se ha publicado o cuya [publicación se ha cancelado](#unpublishing-a-transactional-message) (y no se ha [pausado](#suspending-a-transactional-message-publication)).

* **Mensajes transaccionales**: a menos que se vincule otro mensaje transaccional al evento correspondiente, si se cancela la publicación del mensaje, la configuración de evento también debe cancelarse para eliminar correctamente el mensaje transaccional. Para obtener más información, consulte [Cancelación de la publicación de un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).

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
>Cuando se asigna un evento a un envío de ejecución, aparece en los registros de este envío de ejecución y solo en este momento. Los envíos fallidos se muestran en la ficha **[!UICONTROL Execution list]** del mensaje transaccional que envía registros.

### Limitaciones del proceso de reintento {#limitations}

**Envío de la actualización de registros**

En el proceso de reintentos, los registros de envío del nuevo envío de ejecución no se actualizan inmediatamente (la actualización se realiza mediante un flujo de trabajo programado). Significa que el mensaje podría estar en estado **[!UICONTROL Pending]** aunque el nuevo envío de ejecución haya procesado el evento transaccional.

**Error en el envío de ejecución**

No se puede detener un envío de ejecución. Sin embargo, si falla el envío de ejecución actual, se crea uno nuevo en cuanto se recibe un nuevo evento y todos los eventos nuevos se procesan con este nuevo envío de ejecución. El envío de ejecución con errores no procesa eventos nuevos.

Si algunos eventos ya asignados a un envío de ejecución se han pospuesto y si ese envío de ejecución falla, el sistema de reintentos no asigna los eventos pospuestos al nuevo envío de ejecución, lo que significa que estos eventos se pierden.

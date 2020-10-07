---
title: Envío de notificaciones push
description: La actividad de envío de notificaciones push permite configurar el envío de una sola notificación push de envío o de una notificación push recurrente en un flujo de trabajo.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---


# Envío de notificaciones push{#push-notification-delivery}

## Descripción {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. Puede ser una sola notificación de envío y enviarse una sola vez, o puede ser una notificación recurrente.

* **Las notificaciones de envío único** son envíos de notificación push de aplicación móvil estándar, que se envían una vez.
* **Las notificaciones recurrentes** le permiten enviar el mismo envío de notificaciones push de la aplicación móvil varias veces a diferentes destinatarios durante un período definido. Puede acumular los envíos por periodo para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

Cuando se vincula a un Planificador, se pueden definir las notificaciones push recurrentes.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de objetivo como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de planificador en el flujo de trabajo para automatizar la ejecución.

**Temas relacionados**

* [Envío de una notificación push recurrente con un flujo de trabajo](../../automating/using/recurring-push-notifications.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Push notification]** en su flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el botón ![](assets/dlv_activity_params-24px.png) de las acciones rápidas de la actividad. Este botón es específico de la actividad **[!UICONTROL Push notification]**. Se puede acceder a las propiedades de la notificación push mediante la barra de acciones del panel push.

1. Seleccione el modo de envío de notificaciones push:

   * **[!UICONTROL Single notification]**:: la notificación push se envía una sola vez. Aquí puede especificar si desea o no añadir una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 del procedimiento.
   * **[!UICONTROL Recurring notification]**:: la notificación push se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el periodo de acumulación de los envíos. This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application&#39;s marketing activity list.

      Por ejemplo, para una notificación de cumpleaños recurrente que se envía diariamente, puede elegir acumulado los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente, aunque la notificación se envía todos los días.

1. Seleccione un tipo de notificación. Estos tipos provienen de plantillas de notificaciones push definidas en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales de la notificación push. También puede adjuntarlo a una campaña existente. La etiqueta de la actividad de envío del flujo de trabajo se actualiza con la etiqueta de notificación push.
1. Defina el contenido de la notificación push. Consulte [Creación de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. De forma predeterminada, la actividad **[!UICONTROL Push notification]** no incluye ninguna transición de salida. Si desea añadir una transición de salida a la actividad **[!UICONTROL Push Notification]**, vaya a la pestaña **[!UICONTROL General]** de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió la notificación. Los miembros del destinatario excluidos durante la preparación del envío quedan excluidos de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le redirige directamente al panel de notificaciones Push. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y solo si el mensaje se ha creado a partir de un flujo de trabajo, puede desactivar la opción **[!UICONTROL Request confirmation before sending messages]**. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de notificaciones push le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).

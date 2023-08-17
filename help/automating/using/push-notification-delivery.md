---
title: Envío de notificaciones push
description: La actividad Entrega de notificaciones push permite configurar el envío de una sola notificación push de envío o de una notificación push recurrente en un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# Envío de notificaciones push{#push-notification-delivery}

## Descripción {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

El **[!UICONTROL Push notification]** La actividad de le permite configurar el envío de una notificación push en un flujo de trabajo. Puede ser una sola notificación de envío y enviarse una sola vez, o puede ser una notificación recurrente.

* **Único** las notificaciones de envío son envíos de notificaciones push de aplicaciones móviles estándar, enviados una vez.
* **Recurrente** las notificaciones le permiten enviar la misma entrega de notificaciones push de aplicación móvil varias veces a diferentes destinatarios durante un periodo definido. Puede acumular los envíos por periodo para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

El **[!UICONTROL Push notification]** la actividad se utiliza generalmente para automatizar el envío de una notificación a un destinatario calculado en el mismo flujo de trabajo.

Cuando se vincula a un planificador, puede definir notificaciones push recurrentes.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, a través de actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de planificador en el flujo de trabajo para automatizar la ejecución.

**Temas relacionados**

* [Envío de una notificación push recurrente con un flujo de trabajo](../../automating/using/recurring-push-notifications.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Push notification]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el botón ![](assets/dlv_activity_params-24px.png) de las acciones rápidas de la actividad. Este botón es específico de la actividad **[!UICONTROL Push notification]**. Se puede acceder a las propiedades de la notificación push a través de la barra de acciones del panel push.

1. Seleccione el modo de envío de la notificación push:

   * **[!UICONTROL Single notification]**: la notificación push se envía una sola vez. Aquí puede especificar si desea o no añadir una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 del procedimiento.
   * **[!UICONTROL Recurring notification]**: la notificación push se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el periodo de acumulación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el periodo definido en una sola notificación push que también se denomina **ejecución recurrente** y se puede acceder a desde la lista de actividad de marketing de la aplicación.

     Por ejemplo, para una notificación de cumpleaños recurrente, que se envía diariamente, puede elegir acumular los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente, aunque la notificación se envíe todos los días.

1. Seleccione un tipo de notificación. Estos tipos provienen de plantillas de notificaciones push definidas en la variable **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** menú.
1. Introduzca las propiedades generales de la notificación push. También puede adjuntarlo a una campaña existente. La etiqueta de la actividad envío del flujo de trabajo se actualiza con la etiqueta de notificación push.
1. Defina el contenido de las notificaciones push. Consulte [Creación de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. De forma predeterminada, la actividad **[!UICONTROL Push notification]** no incluye ninguna transición de salida. Si desea añadir una transición de salida a la actividad **[!UICONTROL Push Notification]**, vaya a la pestaña **[!UICONTROL General]** de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: esto le permite generar una transición de salida que contiene la población a la que se ha enviado la notificación. Los miembros destinatarios excluidos durante la preparación del envío se excluyen de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, le lleva directamente al panel de notificaciones push. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y solo si el mensaje se ha creado a partir de un flujo de trabajo, puede desactivar la opción **[!UICONTROL Request confirmation before sending messages]**. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de las notificaciones push permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

En las entregas principales, a las que se puede acceder desde la lista de actividad de marketing, se puede ver el número total de envíos que se han procesado (según el periodo de acumulación especificado cuando la variable **[!UICONTROL Push notification]** se configuró la actividad). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).

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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 1%

---


# Envío de notificaciones push{#push-notification-delivery}

## Descripción {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

La **[!UICONTROL Push notification]** actividad le permite configurar el envío de una notificación push en un flujo de trabajo. Puede ser una **sola notificación de envío** y enviarse una sola vez, o puede ser una notificación **recurrente** .

Las notificaciones de envío único son envíos de notificación push de aplicación móvil estándar, que se envían una vez.

Las notificaciones recurrentes le permiten enviar el mismo envío de notificaciones push de la aplicación móvil varias veces a diferentes destinatarios durante un período definido. Puede acumulados los envíos por período para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Push notification]** actividad se utiliza generalmente para automatizar el envío de una notificación a un destinatario calculado en el mismo flujo de trabajo.

Cuando se vincula a un Planificador, se pueden definir las notificaciones push recurrentes.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de objetivo como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de Planificador en el flujo de trabajo para automatizar la ejecución.

**Temas relacionados**

* [Envío de una notificación push recurrente con un flujo de trabajo](../../automating/using/recurring-push-notifications.md)

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Push notification]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad. Este botón es específico de la **[!UICONTROL Push notification]** actividad. Se puede acceder a las propiedades de la notificación push mediante la barra de acciones del panel push.

1. Seleccione el modo de envío de notificaciones push:

   * **[!UICONTROL Single notification]**:: la notificación push se envía una sola vez. Aquí puede especificar si desea o no agregar una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring notification]**:: la notificación push se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el período definido en una sola notificación push que también se denomina ejecución **** recurrente y a la que se puede acceder desde la lista de actividad de marketing de la aplicación.

      Por ejemplo, para una notificación de cumpleaños recurrente que se envía diariamente, puede elegir acumulado los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente, aunque la notificación se envía todos los días.

1. Seleccione un tipo de notificación. Estos tipos provienen de plantillas de notificaciones push definidas en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales de la notificación push. También puede adjuntarlo a una campaña existente. La etiqueta de la actividad de envío del flujo de trabajo se actualiza con la etiqueta de notificación push.
1. Defina el contenido de la notificación push. Consulte [Creación de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. De forma predeterminada, la **[!UICONTROL Push notification]** actividad no incluye ninguna transición saliente. Si desea agregar una transición de salida a la **[!UICONTROL Push Notification]** actividad, vaya a la **[!UICONTROL General]** ficha de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió la notificación. Los miembros del destinatario excluidos durante la preparación del envío quedan excluidos de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le redirige directamente al panel de notificaciones Push. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y sólo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de notificaciones push le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

En los envíos principales, a los que se puede acceder desde la lista de actividad de marketing, se puede vista el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL Push notification]** actividad). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).

---
title: Envío de notificaciones push
description: La actividad de envío de notificaciones push permite configurar el envío de una sola notificación push de envío o una notificación push recurrente en un flujo de trabajo.
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Envío de notificaciones push{#push-notification-delivery}

## Descripción {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

La **[!UICONTROL Push notification]**actividad permite configurar el envío de una notificación push en un flujo de trabajo. Puede ser una** sola notificación de envío **y enviarse una sola vez, o puede ser una notificación** recurrente **.

Las notificaciones de envío único son envíos estándar de notificaciones push de aplicaciones móviles, que se envían una vez.

Las notificaciones recurrentes le permiten enviar la misma entrega de notificaciones push de la aplicación móvil varias veces a distintos destinos durante un período definido. Puede agregar los envíos por período para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Push notification]**actividad generalmente se utiliza para automatizar el envío de una notificación a un destino calculado en el mismo flujo de trabajo.

Cuando se vincula a un programador, puede definir notificaciones push recurrentes.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Push notification]**actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no a la propia entrega) mediante el ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad. Este botón es específico de la **[!UICONTROL Push notification]**actividad. Se puede acceder a las propiedades de la notificación push mediante la barra de acciones del tablero push.

1. Seleccione el modo de envío de notificaciones push:

   * **[!UICONTROL Single notification]**:: la notificación push se envía una sola vez. Aquí puede especificar si desea o no agregar una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring notification]**:: la notificación push se envía varias veces, según la frecuencia definida en una**[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el período definido en una sola notificación push que también se denomina ejecución **** recurrente y a la que se puede acceder desde la lista de actividades de marketing de la aplicación.

      Por ejemplo, para una notificación de cumpleaños recurrente que se envía diariamente, puede elegir agregar los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente, aunque la notificación se envía todos los días.

1. Seleccione un tipo de notificación. Estos tipos provienen de plantillas de notificaciones push definidas en el menú **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Introduzca las propiedades generales de la notificación push. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de entrega del flujo de trabajo se actualiza con la etiqueta de notificación push.
1. Defina el contenido de la notificación push. Consulte [Creación de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. De forma predeterminada, la **[!UICONTROL Push notification]**actividad no incluye ninguna transición de salida. Si desea agregar una transición de salida a su**[!UICONTROL Push Notification]** actividad, vaya a la **[!UICONTROL General]**ficha de las opciones de actividad avanzadas (botón![](assets/dlv_activity_params-24px.png)en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió la notificación. Los miembros del objetivo excluidos durante la preparación de la entrega quedan excluidos de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Al volver a abrir la actividad, se le lleva directamente al tablero de notificaciones push. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de entrega solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el tablero de mensajes, y sólo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]**opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a las entregas creadas en un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de notificaciones push le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

En las entregas principales, a las que se puede acceder desde la lista de actividades de marketing, puede ver el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL Push notification]**actividad). Para ello, abra la vista de detalles del**[!UICONTROL Deployment]** bloque de entrega principal seleccionando ![](assets/wkf_dlv_detail_button.png).

## Envío de una notificación push recurrente con un flujo de trabajo {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20.00 horas a los suscriptores de la aplicación móvil, en función de sus zonas horarias. Para ello:

1. La **[!UICONTROL Scheduler]**actividad le permite iniciar el flujo de trabajo días antes del inicio de la entrega para poder enviar la notificación a todos los suscriptores a las 20:00 en cualquier zona horaria determinada:

   * En el **[!UICONTROL Execution frequency]**campo, seleccione Mensual.
   * Seleccione las 20:00 en el **[!UICONTROL Time]**campo.
   * Elija el día en que se enviará el envío cada mes.
   * Seleccione una fecha de inicio para el flujo de trabajo, al menos un día antes del inicio del envío. De lo contrario, algunos destinatarios podrían recibir el mensaje un día después si la hora seleccionada ya ha pasado en sus zonas horarias.
   * En la **[!UICONTROL Execution options]**ficha, seleccione la zona horaria en la que comenzará el flujo de trabajo en el**[!UICONTROL Time zone]** campo. Aquí, por ejemplo, el flujo de trabajo comenzará a las 20:00 horas, hora del Pacífico, una semana antes del primer día del mes, para permitir que se creen entregas para todos los husos horarios aplicables.
   >[!NOTE]
   >
   >De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. La actividad **Consulta** le permite dirigirse a los clientes VIP de entre 20 y 30 años, que se han suscrito a la aplicación móvil y que no han abierto el correo electrónico enviado:

   * Seleccione una audiencia (sus clientes VIP) y filtre según su edad.
   * Arrastre y suelte las **suscripciones en un elemento de aplicación** en el espacio de trabajo. Seleccione **Existe** y seleccione la aplicación móvil que desee utilizar.
   * Seleccione el correo electrónico que ha enviado a sus clientes.
   * Arrastre y suelte el elemento Registros de **envío (registros)** en el espacio de trabajo y seleccione **Existe** para dirigirse a todos los clientes que recibieron el correo electrónico.
   * Arrastre y suelte el elemento Registros de **seguimiento (seguimiento)** en el espacio de trabajo y seleccione **No existe** para dirigirse a todos los clientes que no abrieron el correo electrónico.

      ![](assets/wkf_push_example_2.png)

1. La actividad de notificación **** Push le permite introducir el contenido del mensaje y seleccionar los campos de personalización que desea utilizar:

   * Seleccione la **[!UICONTROL Recurring notification]**opción.
   * Defina el contenido de la notificación push. Para obtener más información sobre el contenido de las notificaciones push, consulte esta [sección](../../channels/using/preparing-and-sending-a-push-notification.md).
   * En el **[!UICONTROL Schedule]**bloque, seleccione**[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aquí elegimos el **[!UICONTROL Time zone of the contact date]**Pacífico como en el flujo de trabajo**[!UICONTROL Scheduler]**.
   * En el **[!UICONTROL Optimize the sending time per recipient]**campo, seleccione**[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Haga clic en el **[!UICONTROL Start]**botón para iniciar el flujo de trabajo recurrente.

   ![](assets/wkf_push_example_3.png)

El flujo de trabajo se está ejecutando. Comenzará en la fecha de inicio elegida para las **[!UICONTROL Scheduler]**20:00, hora del Pacífico, la notificación push recurrente se enviará cada primer día del mes a las 20:00, dependiendo del huso horario del cliente.

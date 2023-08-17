---
title: Envío de SMS
description: La actividad envío de SMS permite configurar el envío de un solo mensaje SMS o un SMS recurrente en un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: sms,main;delivery,smsContent,back
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 65d3f3d8-039d-4188-a6a4-0065724aa82b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---

# Envío de SMS{#sms-delivery}

## Descripción {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

La actividad **[!UICONTROL SMS delivery]** le permite configurar el envío de un SMS en un flujo de trabajo. Puede ser un único SMS y enviado una sola vez, o puede ser un SMS recurrente.

* **Los mensajes SMS de un solo envío son SMS estándar, enviados una vez.**
* **Los mensajes SMS recurrentes le permiten enviar el mismo SMS varias veces a diferentes destinatarios durante un periodo definido.** Puede acumular los envíos por periodo para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL SMS delivery]** se utiliza generalmente para automatizar el envío de un SMS a un destinatario calculado en el mismo flujo de trabajo.

Cuando se vincula a un planificador, puede definir mensajes SMS recurrentes.

Los destinatarios del SMS se definen antes de la actividad en el mismo flujo de trabajo, a través de actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de planificador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL SMS delivery]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el botón ![](assets/dlv_activity_params-24px.png) de la barra de acciones del flujo de trabajo. Este botón es específico de la actividad **[!UICONTROL SMS delivery]**. Se puede acceder a las propiedades del SMS a través de la barra de acción del panel SMS.

1. Seleccione el modo de envío SMS:

   * **[!UICONTROL SMS]**: el SMS se envía una sola vez. Aquí puede especificar si desea o no añadir una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 del procedimiento.
   * **[!UICONTROL Recurring SMS]**: el SMS se envía varias veces, según la frecuencia definida en una actividad de **[!UICONTROL Scheduler]**. Seleccione el periodo de acumulación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el periodo definido en una sola vista que también se denomina **ejecución recurrente** y a la que se puede acceder desde la lista de actividad de marketing de la aplicación.

     Por ejemplo, para un SMS de cumpleaños recurrente, que se envía diariamente, puede elegir acumular los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente, aunque el SMS se envíe todos los días.

1. Seleccione un tipo de SMS. Los tipos de SMS provienen de plantillas de SMS definidas en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Introduzca las propiedades generales del SMS. También puede adjuntarlo a una campaña existente. La etiqueta de la actividad envío del flujo de trabajo se actualiza con la etiqueta SMS.
1. Defina el contenido del SMS. Consulte la sección [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md).
1. De forma predeterminada, la actividad **[!UICONTROL SMS delivery]** no incluye ninguna transición de salida. Si desea añadir una transición de salida a la actividad **[!UICONTROL SMS delivery]**, vaya a la pestaña **[!UICONTROL General]** de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: esto le permite generar una transición de salida que contiene la población a la que se ha enviado el SMS. Los miembros destinatarios excluidos durante la preparación del envío (cuarentena, número no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, le lleva directamente al panel SMS. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y solo si el mensaje se ha creado a partir de un flujo de trabajo, puede desactivar la opción **[!UICONTROL Request confirmation before sending messages]**. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de SMS permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña o envío principal en caso de un SMS recurrente).

Sin embargo, las ejecuciones de envíos recurrentes se enmascaran de forma predeterminada. Para verlos, marque la opción **[!UICONTROL Show recurring executions]** en el panel de búsqueda de las actividades de marketing.

En los envíos principales, a los que se puede acceder desde la lista de actividad de marketing o directamente a través de las ejecuciones recurrentes asociadas, se puede ver el número total de envíos que se han procesado (según el periodo de acumulación especificado cuando se configuró la actividad **[!UICONTROL SMS delivery]**). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).

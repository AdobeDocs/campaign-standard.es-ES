---
title: Envío de SMS
description: La actividad de envío de SMS le permite configurar el envío de un solo mensaje SMS o un SMS recurrente en un flujo de trabajo.
page-status-flag: nunca activado
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: channel-activity
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Envío de SMS{#sms-delivery}

## Descripción {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

La **[!UICONTROL SMS delivery]** actividad le permite configurar el envío de un SMS en un flujo de trabajo. Puede ser un **único mensaje** de SMS y enviado una sola vez, o puede ser un mensaje de texto **recurrente** .

Los mensajes SMS de un solo envío son SMS estándar, enviados una vez.

Los mensajes SMS recurrentes le permiten enviar el mismo SMS varias veces a diferentes destinos durante un período definido. Puede agregar los envíos por período para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL SMS delivery]** actividad se utiliza generalmente para automatizar el envío de un mensaje de texto a un destino calculado en el mismo flujo de trabajo.

Cuando está vinculado a un programador, puede definir mensajes SMS recurrentes.

Los destinatarios de SMS se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL SMS delivery]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no a la propia entrega) mediante el ![](assets/dlv_activity_params-24px.png) botón de la barra de acciones del flujo de trabajo. Este botón es específico de la **[!UICONTROL SMS delivery]** actividad. Se puede acceder a las propiedades de SMS a través de la barra de acciones del tablero SMS.

1. Seleccione el modo de envío SMS:

   * **[!UICONTROL SMS]**:: el SMS se envía una sola vez. Aquí puede especificar si desea o no agregar una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring SMS]**:: el SMS se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el período definido en una sola vista que también se denomina ejecución **** recurrente y a la que se puede acceder desde la lista de actividades de marketing de la aplicación.

      Por ejemplo, para un SMS de cumpleaños recurrente que se envía diariamente, puede elegir agregar los envíos por mes. Esto le permite recibir informes sobre su entrega mensualmente, aunque el SMS se envía todos los días.

1. Seleccione un tipo de SMS. Los tipos SMS provienen de plantillas SMS definidas en el **[!UICONTROL Resources]** menú &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales del SMS. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de envío del flujo de trabajo se actualiza con la etiqueta SMS.
1. Defina el contenido de SMS. Consulte la sección sobre la [creación de un mensaje](../../channels/using/creating-an-sms-message.md)SMS.
1. De forma predeterminada, la **[!UICONTROL SMS delivery]** actividad no incluye ninguna transición de salida. Si desea agregar una transición de salida a su **[!UICONTROL SMS delivery]** actividad, vaya a la **[!UICONTROL General]** ficha de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió el SMS. Los miembros del objetivo excluidos durante la preparación de la entrega (cuarentena, número no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le lleva directamente al tablero de SMS. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de entrega solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el tablero de mensajes y solo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a las entregas creadas en un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de SMS permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, entrega principal en caso de un SMS recurrente).

Sin embargo, las ejecuciones de entregas recurrentes se enmascaran de forma predeterminada. Para verlos, marque la **[!UICONTROL Show recurring executions]** opción en el panel de búsqueda de las actividades de marketing.

En las entregas principales, a las que se puede acceder desde la lista de actividades de marketing o directamente a través de las ejecuciones recurrentes asociadas, puede ver el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL SMS delivery]** actividad). Para ello, abra la vista de detalles del **[!UICONTROL Deployment]** bloque de entrega principal seleccionando ![](assets/wkf_dlv_detail_button.png).

## Ejemplo {#example}

![](assets/wkf_sms_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un SMS a los perfiles cuyo cumpleaños es ese día. Para ello:

* La **[!UICONTROL Scheduler]** le permite iniciar el flujo de trabajo todos los días a las 8:00.

   ![](assets/wkf_delivery_example_2.png)

* La **[!UICONTROL Query]** actividad le permite calcular los perfiles que han proporcionado un número de teléfono móvil y cuyo cumpleaños es el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo de cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El **[!UICONTROL SMS]** problema es recurrente. Los envíos se agregan por mes. Así que todos los mensajes SMS enviados en un mes se agregan a una sola vista. En un año, se ejecutan 365 entregas, pero se reagrupan en 12 vistas (también llamadas ejecuciones **** recurrentes) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_sms_example_4.png)

Para ver otro ejemplo de envío de SMS en un flujo de trabajo, consulte Caso [de uso: Flujo de trabajo de redireccionamiento que envía una nueva entrega a los no abridores](../../automating/using/workflow-cross-channel-retargeting.md).

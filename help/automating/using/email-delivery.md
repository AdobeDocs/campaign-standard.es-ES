---
title: Envío de correo electrónico
seo-title: Envío de correo electrónico
description: Envío de correo electrónico
seo-description: La actividad de envío de correo electrónico le permite configurar el envío de un único correo electrónico de envío o de un correo electrónico recurrente en un flujo de trabajo.
page-status-flag: nunca activado
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: channel-activity
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: entrega,flujo de trabajo,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Envío de correo electrónico{#email-delivery}

## Descripción {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

La **[!UICONTROL Email delivery]** actividad le permite configurar el envío de un correo electrónico en un flujo de trabajo. Puede ser un **único correo electrónico de envío** y enviarlo una sola vez, o puede ser un correo electrónico **recurrente** .

Los correos electrónicos de envío único son mensajes de correo electrónico estándar, que se envían una vez.

Los correos electrónicos recurrentes permiten enviar el mismo correo electrónico varias veces a distintos destinos durante un período definido. Puede agregar los envíos por período para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Email delivery]** actividad generalmente se utiliza para automatizar el envío de un correo electrónico a un destino calculado en el mismo flujo de trabajo.

Cuando se vincula a un programador, puede definir correos electrónicos recurrentes.

Los destinatarios de correo electrónico se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no a la propia entrega) mediante el ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad. Este botón es específico de la **[!UICONTROL Email delivery]** actividad. Se puede acceder a las propiedades del correo electrónico a través de la barra de acciones del panel de correo electrónico.

1. Seleccione el modo de envío de correo electrónico:

   * **[!UICONTROL Email]**:: el correo electrónico se envía una sola vez. Aquí puede especificar si desea o no agregar una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring email]**:: el correo electrónico se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el período definido en un único correo electrónico que también se denomina ejecución **** recurrente y al que se puede acceder desde la lista de actividades de marketing de la aplicación.

      Por ejemplo, para un correo electrónico de cumpleaños recurrente, que se envía diariamente, puede elegir agregar los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente aunque el correo electrónico se envíe todos los días.

1. Seleccione un tipo de correo electrónico. Los tipos de correo electrónico proceden de plantillas de correo electrónico definidas en el menú **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales del correo electrónico. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de entrega del flujo de trabajo se actualiza con la etiqueta de correo electrónico.
1. Defina el contenido del correo electrónico. Consulte la sección sobre edición [de](../../designing/using/overview.md)contenido.
1. De forma predeterminada, la **[!UICONTROL Email delivery]** actividad no incluye ninguna transición de salida. Si desea agregar una transición de salida a su **[!UICONTROL Email delivery]** actividad, vaya a la **[!UICONTROL General]** ficha de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió el correo electrónico. Los miembros del objetivo excluidos durante la preparación de la entrega (cuarentena, correo electrónico no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le redirige directamente al panel de correo electrónico. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de entrega solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el tablero de mensajes y solo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a las entregas creadas en un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de correo electrónico le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, entrega principal en caso de un correo electrónico recurrente).

![](assets/wkf_display_recurrent_executions_2.png)

Sin embargo, las ejecuciones de entregas recurrentes se enmascaran de forma predeterminada. Para verlos, marque la **[!UICONTROL Show recurring executions]** opción en el panel de búsqueda de las actividades de marketing.

![](assets/wkf_display_recurrent_executions.png)

En las entregas principales, a las que se puede acceder desde la lista de actividades de marketing o directamente a través de las ejecuciones recurrentes asociadas, puede ver el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL Email delivery]** actividad). Para ello, abra la vista de detalles del **[!UICONTROL Deployment]** bloque de entrega principal seleccionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Ejemplo {#example}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día. Para ello:

* La **[!UICONTROL Scheduler]** le permite iniciar el flujo de trabajo todos los días a las 8:00.

   ![](assets/wkf_delivery_example_2.png)

* La **[!UICONTROL Query]** actividad le permite calcular los perfiles que han proporcionado un correo electrónico y de quién es el cumpleaños en el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo de cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El **[!UICONTROL Email]** problema es recurrente. Los envíos se agregan por mes. Por lo tanto, todos los correos electrónicos enviados en un mes se agregan a una sola vista. En un año, se ejecutan 365 entregas, pero se reagrupan en 12 vistas (también llamadas ejecuciones **** recurrentes) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

**Temas relacionados**

* [Caso de uso: Crear un envío de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso:Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía una nueva entrega a no abridores](../../automating/using/workflow-cross-channel-retargeting.md)
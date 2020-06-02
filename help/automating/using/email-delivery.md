---
title: Envío de correo electrónico
description: La actividad envío de correo electrónico permite configurar el envío de un único correo electrónico de envío o de un correo electrónico recurrente en un flujo de trabajo.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6e87dc8f299f0c9fbb33e5e56c0a76cfef0aa9a6
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 1%

---


# Envío de correo electrónico{#email-delivery}

## Descripción {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

La **[!UICONTROL Email delivery]** actividad le permite configurar el envío de un correo electrónico en un flujo de trabajo. Puede ser un **único correo electrónico de envío** y enviarlo una sola vez, o puede ser un correo electrónico **recurrente** .

Los correos electrónicos de envío único son mensajes de correo electrónico estándar, que se envían una vez.

Los correos electrónicos recurrentes permiten enviar el mismo correo electrónico varias veces a diferentes destinatarios durante un período definido. Puede acumulados los envíos por período para obtener informes que se correspondan con sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Email delivery]** actividad se utiliza generalmente para automatizar el envío de un correo electrónico a un destinatario calculado en el mismo flujo de trabajo.

Cuando se vincula a un Planificador, puede definir correos electrónicos recurrentes.

Los destinatarios de correo electrónico se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de objetivo como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de Planificador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad. Este botón es específico de la **[!UICONTROL Email delivery]** actividad. Se puede acceder a las propiedades del correo electrónico a través de la barra de acciones del panel de correo electrónico.

1. Seleccione el modo de envío de correo electrónico:

   * **[!UICONTROL Email]**:: el correo electrónico se envía una sola vez. Aquí puede especificar si desea o no agregar una transición de salida a la actividad. Los diferentes tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring email]**:: el correo electrónico se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto le permite agrupar todos los envíos que se producen durante el período definido en un único mensaje de correo electrónico que también se denomina ejecución **** recurrente y al que se puede acceder desde la lista de actividad de marketing de la aplicación.

      Por ejemplo, para un correo electrónico de cumpleaños recurrente, que se envía diariamente, puede elegir acumulado los envíos por mes. Esto le permite recibir informes sobre su envío mensualmente aunque el correo electrónico se envíe todos los días.
   >[!NOTE]
   >
   >Los envíos recurrentes se preparan en función del período **de** agregación. Por ejemplo, si el período de agregación es &quot;por día&quot;, el envío se volverá a preparar sólo una vez al día. Si planea llamar a este flujo de trabajo varias veces al día, utilice [!UICONTROL No aggregation].

1. Seleccione un tipo de correo electrónico. Los tipos de correo electrónico proceden de plantillas de correo electrónico definidas en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales del correo electrónico. También puede adjuntarlo a una campaña existente. La etiqueta de la actividad de envío del flujo de trabajo se actualiza con la etiqueta de correo electrónico.
1. Defina el contenido del correo electrónico. Consulte la sección sobre edición [de](../../designing/using/designing-content-in-adobe-campaign.md)contenido.
1. De forma predeterminada, la **[!UICONTROL Email delivery]** actividad no incluye ninguna transición saliente. Si desea agregar una transición de salida a la **[!UICONTROL Email delivery]** actividad, vaya a la **[!UICONTROL General]** ficha de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió el correo electrónico. Los miembros del destinatario excluidos durante la preparación del envío (cuarentena, correo electrónico no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le redirige directamente al panel de correo electrónico. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y sólo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de correo electrónico le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, envío principal en caso de un correo electrónico recurrente).

![](assets/wkf_display_recurrent_executions_2.png)

Sin embargo, las ejecuciones de envíos recurrentes se enmascaran de forma predeterminada. Para vista, marque la opción **[!UICONTROL Show recurring executions]** en el panel de búsqueda actividades de marketing.

![](assets/wkf_display_recurrent_executions.png)

En los envíos principales, a los que se puede acceder desde la lista de actividad de marketing o directamente a través de las ejecuciones recurrentes asociadas, se puede vista el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL Email delivery]** actividad). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Ejemplo {#example}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día. Para ello:

* La **[!UICONTROL Scheduler]** le permite realizar inicios del flujo de trabajo todos los días a las 8:00 h.

   ![](assets/wkf_delivery_example_2.png)

* La **[!UICONTROL Query]** actividad le permite calcular los perfiles que han proporcionado un correo electrónico y de quién es el cumpleaños en el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo de cumpleaños se realiza con un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El **[!UICONTROL Email]** problema es recurrente. Los envíos se agregan por mes. Por lo tanto, todos los correos electrónicos enviados en un mes se agregan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas ejecuciones **** recurrentes) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

**Temas relacionados**

* [Caso de uso: Crear un envío de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de un envío segmentado en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de envíos con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía un nuevo envío a los no abridores](../../automating/using/workflow-cross-channel-retargeting.md)
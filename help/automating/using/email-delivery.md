---
title: Envío por correo electrónico
seo-title: Envío por correo electrónico
description: Envío por correo electrónico
seo-description: La actividad de envío por correo electrónico permite configurar el envío de un único correo electrónico o un correo electrónico recurrente en un flujo de trabajo.
page-status-flag: no activado nunca
uuid: 7 de 53431-84 ae -4 d 21-8361-2775 ad 314 ed 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: channel-activities
discoiquuid: 5 f 288 cf 6-f 8 ff -4 ac 9-9 c 1 a -8010260554 bb
context-tags: entrega, flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Envío por correo electrónico{#email-delivery}

## Descripción {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

La **[!UICONTROL Email delivery]** actividad permite configurar el envío de un correo electrónico en un flujo de trabajo. Puede ser un **único correo electrónico enviado** y enviado una sola vez, o puede ser un correo electrónico **recurrente** .

Los mensajes de correo electrónico únicos son correos electrónicos estándar, enviados una vez.

Los mensajes de correo electrónico recurrentes le permiten enviar el mismo correo electrónico varias veces a diferentes objetivos durante un período definido. Puede agregar las entregas por período para obtener informes que correspondan a sus necesidades.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Email delivery]** actividad se utiliza generalmente para automatizar el envío de un correo electrónico a un objetivo calculado en el mismo flujo de trabajo.

Cuando se vincula a un programador, puede definir correos electrónicos recurrentes.

Los destinatarios de correo electrónico están definidos en el flujo superior de la actividad en el mismo flujo de trabajo mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación de los mensajes se activa según los parámetros de ejecución del flujo de trabajo. Desde el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (obligatorio de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad en el flujo de trabajo.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no de la propia entrega) a través ![](assets/dlv_activity_params-24px.png) del botón de las acciones rápidas de la actividad. Este botón es específico de **[!UICONTROL Email delivery]** la actividad. Se puede acceder a las propiedades del correo electrónico mediante la barra de acciones en el panel de correo electrónico.

1. Seleccione el modo de envío de correo electrónico:

   * **[!UICONTROL Email]**: El correo electrónico se envía una sola vez. Puede especificar si desea o no agregar una transición saliente a la actividad. Los distintos tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring email]**: El correo electrónico se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. Esto permite reagrupar todos los envíos que se producen durante el período definido en un único correo electrónico que también se denomina **ejecución recurrente** y se puede acceder a ellos desde la lista de actividades de marketing de la aplicación.

      Por ejemplo, para un correo electrónico de cumpleaños recurrente, se envía diariamente, puede elegir agregar los envíos al mes. Esto le permite recibir informes sobre su entrega mensualmente, aunque el correo electrónico se envíe todos los días.

1. Seleccione un tipo de correo electrónico. Los tipos de correo electrónico provienen de plantillas de correo electrónico definidas en **[!UICONTROL Resources]** el menú &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Introduzca las propiedades generales del correo electrónico. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de entrega del flujo de trabajo se actualiza con la etiqueta de correo electrónico.
1. Defina el contenido de correo electrónico. Consulte la sección relativa a la edición [de contenido](../../designing/using/about-email-content-design.md).
1. De forma predeterminada, **[!UICONTROL Email delivery]** la actividad no incluye transiciones salientes. Si desea agregar una transición saliente a la **[!UICONTROL Email delivery]** actividad, vaya a **[!UICONTROL General]** la ficha de las opciones de actividad avanzadas ( ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**: esto permite generar una transición saliente que contiene exactamente la misma población que la transición entrante.
   * **[!UICONTROL Add outbound transition with the population]**: esto permite generar una transición saliente que contenga la población a la que se envió el correo electrónico. Los miembros del objetivo excluidos durante la preparación de entrega (cuarentena, correo electrónico no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, se le dirigirá directamente al tablero de correo electrónico. Solo se puede editar su contenido.

De forma predeterminada, al iniciar un flujo de trabajo de entrega, se activa la preparación de los mensajes. El envío de mensajes creados a partir de un flujo de trabajo todavía debe confirmarse después de haber iniciado el flujo de trabajo. Sin embargo, en el panel de mensajes, y solo si el mensaje se creó desde un flujo de trabajo, puede deshabilitar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso cuando se realiza la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de correo electrónico permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, entrega principal en caso de correo electrónico recurrente).

![](assets/wkf_display_recurrent_executions_2.png)

Sin embargo, las ejecuciones de entregas recurrentes se enmascaran de forma predeterminada. Para verlos, marque **[!UICONTROL Show recurring executions]** la opción en el panel de búsqueda de actividades de marketing.

![](assets/wkf_display_recurrent_executions.png)

En las entregas principales, a las que se puede acceder desde la lista de actividades de marketing o directamente a través de las ejecuciones recurrentes asociadas, puede ver el número total de envíos procesados (según el período de agregación especificado cuando se configuró la **[!UICONTROL Email delivery]** actividad). Para ello, abra la vista de detalles del **[!UICONTROL Deployment]** bloque de la entrega principal seleccionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Ejemplo {#example}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día. Para ello:

* Esto **[!UICONTROL Scheduler]** le permite iniciar el flujo de trabajo todos los días a las 8 am.

   ![](assets/wkf_delivery_example_2.png)

* La **[!UICONTROL Query]** actividad permite calcular los perfiles que han proporcionado un correo electrónico y cuyo cumpleaños es el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo de cumpleaños se lleva a cabo con un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El es **[!UICONTROL Email]** recurrente. Los envíos se agregan por mes. Por lo tanto, todos los mensajes de correo electrónico enviados en un mes se agregan en una sola vista. En un año, se ejecutan 365 entregas pero se regeneran en 12 vistas (también denominadas ejecuciones **recurrentes**) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran todos los meses, no por cada envío.

   ![](assets/wkf_delivery_example_4.png)

**Temas relacionados**

* [Caso de uso: Crear una entrega de correo electrónico una sola semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en la ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Volver a configurar el flujo de trabajo envío de una nueva entrega a no abiertos](../../automating/using/workflow-cross-channel-retargeting.md)
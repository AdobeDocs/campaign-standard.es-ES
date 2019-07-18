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
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Email delivery{#email-delivery}

## Description {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

The **[!UICONTROL Email delivery]** activity allows you to configure sending an email in a workflow. This can be a **single send** email and sent just once, or it can be a **recurring** email.

Los mensajes de correo electrónico únicos son correos electrónicos estándar, enviados una vez.

Los mensajes de correo electrónico recurrentes le permiten enviar el mismo correo electrónico varias veces a diferentes objetivos durante un período definido. Puede agregar las entregas por período para obtener informes que correspondan a sus necesidades.

## Context of use {#context-of-use}

The **[!UICONTROL Email delivery]** activity is generally used to automate sending an email to a target calculated in the same workflow.

Cuando se vincula a un programador, puede definir correos electrónicos recurrentes.

Los destinatarios de correo electrónico están definidos en el flujo superior de la actividad en el mismo flujo de trabajo mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación de los mensajes se activa según los parámetros de ejecución del flujo de trabajo. Desde el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (obligatorio de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Email delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Email delivery]** activity. Se puede acceder a las propiedades del correo electrónico mediante la barra de acciones en el panel de correo electrónico.

1. Seleccione el modo de envío de correo electrónico:

   * **[!UICONTROL Email]**: El correo electrónico se envía una sola vez. Puede especificar si desea o no agregar una transición saliente a la actividad. Los distintos tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring email]**: El correo electrónico se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. This allows you to regroup all the sends that occur during the defined period in one single email that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Por ejemplo, para un correo electrónico de cumpleaños recurrente, se envía diariamente, puede elegir agregar los envíos al mes. Esto le permite recibir informes sobre su entrega mensualmente, aunque el correo electrónico se envíe todos los días.

1. Seleccione un tipo de correo electrónico. The email types come from email templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Introduzca las propiedades generales del correo electrónico. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de entrega del flujo de trabajo se actualiza con la etiqueta de correo electrónico.
1. Defina el contenido de correo electrónico. Refer to the section concerning [content editing](../../designing/using/about-email-content-design.md).
1. By default, the **[!UICONTROL Email delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Email delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: esto permite generar una transición saliente que contiene exactamente la misma población que la transición entrante.
   * **[!UICONTROL Add outbound transition with the population]**: esto permite generar una transición saliente que contenga la población a la que se envió el correo electrónico. Los miembros del objetivo excluidos durante la preparación de entrega (cuarentena, correo electrónico no válido, etc.) se excluyen de esta transición.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, se le dirigirá directamente al tablero de correo electrónico. Solo se puede editar su contenido.

De forma predeterminada, al iniciar un flujo de trabajo de entrega, se activa la preparación de los mensajes. El envío de mensajes creados a partir de un flujo de trabajo todavía debe confirmarse después de haber iniciado el flujo de trabajo. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Al desmarcar esta opción, los mensajes se envían sin previo aviso cuando se realiza la preparación.

## Remarks {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de correo electrónico permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, entrega principal en caso de correo electrónico recurrente).

![](assets/wkf_display_recurrent_executions_2.png)

Sin embargo, las ejecuciones de entregas recurrentes se enmascaran de forma predeterminada. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Email delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Example {#example}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día. Para ello:

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The **[!UICONTROL Query]** activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. El cálculo de cumpleaños se lleva a cabo con un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL Email]** is recurring. Los envíos se agregan por mes. Por lo tanto, todos los mensajes de correo electrónico enviados en un mes se agregan en una sola vista. In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. Los detalles del historial y del informe se muestran todos los meses, no por cada envío.

   ![](assets/wkf_delivery_example_4.png)


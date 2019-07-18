---
title: Envío de correo directo
seo-title: Envío de correo directo
description: Envío de correo directo
seo-description: La actividad de envío de correo directo permite configurar el envío de un único correo directo o un correo directo recurrente en un flujo de trabajo.
page-status-flag: no activado nunca
uuid: bfa 7 b 176-a 17 c -4079-a 073-64 b 8 ce 4788 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: channel-activities
discoiquuid: b 9 ddb 2 a 0-54 ff -4 ada-be 6 f -8109 fa 06 d 461
context-tags: Directmail, flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

The **[!UICONTROL Direct mail delivery]** activity allows you to configure and prepare a file containing profile data that you want to use for a direct mail campaign. This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

Los mensajes directos estándar se envían una vez.

Los mensajes recurrentes le permiten enviar el mismo correo directo varias veces a diferentes objetivos durante un período definido. Puede agregar las entregas por período para obtener informes que correspondan a sus necesidades.

## Context of use {#context-of-use}

The **[!UICONTROL Direct mail delivery]** activity is generally used to automate preparing a file that contains profile data. Este archivo se puede enviar a un socio o proveedor a cargo del correo.

Cuando se vincula a un programador, puede definir mensajes directos recurrentes.

Los destinatarios de correo directo están definidos en el flujo superior de la actividad en el mismo flujo de trabajo mediante actividades de segmentación como consultas, intersecciones, etc. Los perfiles cuya dirección de correo no se especifique se excluyen automáticamente cuando se prepare el correo directo.

La preparación de los mensajes se activa según los parámetros de ejecución del flujo de trabajo. Desde el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (obligatorio de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. Este botón es específico de las actividades de canal. Se puede acceder a las propiedades del correo directo mediante la barra de acciones en el panel de correo directo.

1. Seleccione el modo de envío de correo directo:

   * **[!UICONTROL Direct mail]**: el correo directo se envía una sola vez. Puede especificar si desea o no agregar una transición saliente a la actividad. Los distintos tipos de transición se detallan en el paso 7 de este procedimiento.
   * **[!UICONTROL Recurring direct mail]**: El mensaje directo se envía varias veces, según la frecuencia definida en una **[!UICONTROL Scheduler]** actividad. Seleccione el período de agregación de los envíos. This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Por ejemplo, para un correo de cumpleaños recurrente, que se procesa diariamente, puede elegir agregar los envíos al mes. Esto le permite recibir informes sobre su entrega mensualmente, aunque el correo se procese todos los días.

      >[!NOTE]
      >
      >En los mensajes directos recurrentes, se genera un nuevo archivo en cada ejecución del flujo de trabajo. El período de agregación seleccionado no afecta a este comportamiento.

1. Seleccione un tipo de correo directo. The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Introduzca las propiedades generales del correo directo. También puede adjuntarla a una campaña existente. La etiqueta de la actividad de entrega del flujo de trabajo se actualiza con la etiqueta de correo directo.
1. Defina el contenido de correo directo. Refer to the section concerning [content editing](../../designing/using/about-personalization.md).
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: esto permite generar una transición saliente que contiene exactamente la misma población que la transición entrante. Esta transición contiene el archivo generado por la actividad de correo directo y la población sin procesar recibida por la actividad de correo directo.
   * **[!UICONTROL Add outbound transition with the population]**: esto permite generar una transición saliente que contenga la población a la que se enviará el correo directo. Los miembros del objetivo excluidos durante la preparación de correo directo (cuarentena, dirección no válida, etc.) se excluyen de esta transición. La transición también contiene el archivo generado por el correo directo.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, se le dirigirá directamente al tablero de correo directo. Solo se puede editar su contenido.

De forma predeterminada, al iniciar un flujo de trabajo de entrega, se activa la preparación de los mensajes. El envío de mensajes creados a partir de un flujo de trabajo todavía debe confirmarse después de haber iniciado el flujo de trabajo. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Al desmarcar esta opción, los mensajes se envían sin previo aviso cuando se realiza la preparación.

## Remarks {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de correo directo permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, entrega principal en caso de correo directo recurrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

Las ejecuciones de entregas recurrentes se enmascaran de forma predeterminada. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

An example of **[!UICONTROL Direct mail delivery]** is available in the [Direct Mail](../../channels/using/example-of-direct-mail-in-a-workflow.md) chapter.

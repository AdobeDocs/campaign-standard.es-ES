---
title: Programador
seo-title: Programador
description: Programador
seo-description: La actividad del programador permite programar un flujo de trabajo o una actividad.
page-status-flag: no activado nunca
uuid: f 5 e 50 a 11-8 dc 9-4 d 98-9531-024 c 0 fb 3 f 7 da
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 0 fb 16 cea -3941-404 f -899 c -33 f 81 ed 4 ed 5
context-tags: programación, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e3a627376a91eb394aea90b1d94c7958ad77fd40

---


# Scheduler{#scheduler}

## Description {#description}

![](assets/scheduler.png)

The **[!UICONTROL Scheduler]** activity allows you to schedule when a workflow or an activity is started.

## Context of use {#context-of-use}

**[!UICONTROL Scheduler]** La actividad debe considerarse como un inicio programado. The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. Esta actividad no debe tener una transición de entrada.

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. Se establecerá en caso contrario para que se ejecute en la zona horaria del servidor.

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. Significa que un flujo de trabajo no se puede ejecutar automáticamente más de una vez cada 10 minutos.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: el flujo de trabajo se ejecuta una sola vez.
   * **[!UICONTROL Several times a day]**: El flujo de trabajo se ejecuta varias veces al día. Puede configurar ejecuciones en momentos específicos o periódicamente.
   * **[!UICONTROL Daily]**: el flujo de trabajo se ejecuta a una hora específica, una vez al día.
   * **[!UICONTROL Weekly]**: el flujo de trabajo se ejecuta en un momento específico, en uno o varios días de una semana.
   * **[!UICONTROL Monthly]**: el flujo de trabajo se ejecuta en un momento concreto, una o varias veces al mes. Puede seleccionar meses, cuando necesite ejecutar el flujo de trabajo. También puede configurar ejecuciones en un día de semana específico del mes, como el segundo martes del mes.
   * **[!UICONTROL Yearly]**: El flujo de trabajo se ejecuta en un momento concreto, una o varias veces al año.

1. Defina los detalles de ejecución según la frecuencia seleccionada. Los campos de detalle pueden variar según la frecuencia utilizada (tiempo, frecuencia de repetición, días especificados, etc.).

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** El campo permite identificar los tiempos en que se activa el flujo de trabajo. For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. No puede ser inferior a 10 minutos. If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. Especifique cuándo caducará la ejecución:

   * **[!UICONTROL Never]**: El flujo de trabajo se ejecutará según la frecuencia especificada, sin ningún límite para el intervalo de tiempo o el número de iteraciones.
   * **[!UICONTROL After a certain number of iterations]**: El flujo de trabajo se ejecutará según la frecuencia especificada, hasta que se llegue al límite **de X** . The **[!UICONTROL Number of iterations]** will therefore need to be specified.
   * **[!UICONTROL On a specific date]**: el flujo de trabajo se ejecutará según la frecuencia especificada, hasta una fecha específica. Por lo tanto, es necesario especificar la fecha límite de ejecución.

1. Check the schedule of the next ten executions of your workflow by clicking **[!UICONTROL Preview next executions]**.

1. In the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. Esto le permite iniciar el flujo de trabajo en una zona horaria específica; de lo contrario, el flujo de trabajo se ejecutará en zona horaria del servidor de forma predeterminada.

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

En el siguiente ejemplo, la actividad se configura para que comience el flujo de trabajo cada semana, cada dos días del lunes a las 7, durante una duración indeterminada.

![](assets/wkf_scheduler_example.png)


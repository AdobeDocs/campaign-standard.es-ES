---
title: Inicio y finalización
seo-title: Inicio y finalización
description: Inicio y finalización
seo-description: Las actividades de inicio y finalización permiten marcar claramente dónde comienza y finaliza el flujo de trabajo.
page-status-flag: no activado nunca
uuid: 146 b 6337-122 c -453 d -8 ffd -5 c 157 db 29217
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: a 0 a 8 a 725-8 ede -4626-9798-b 86924 b 58 beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Start and end{#start-and-end}

## Description {#description}

![](assets/start.png)

![](assets/end.png)

The **[!UICONTROL Start]** and **[!UICONTROL End]** activities allow you to clearly mark where your workflow starts and ends.

## Context of use {#context-of-use}

La ejecución de un flujo de trabajo comienza con actividades sin una transición entrante y se detiene cuando ya no hay tareas en curso. Nevertheless, you can add **[!UICONTROL Start]** and **[!UICONTROL End]** activities to clearly mark the starting and ending points of a workflow. Esto resulta especialmente útil para flujos de trabajo relativamente complejos.

It is a best practice to use an **[!UICONTROL End]** activity instead of leaving the last transition of a workflow on its own to ensure that the workflow properly ends.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Start]** or **[!UICONTROL End]** activity into your workflow.
1. Put the **[!UICONTROL Start]** activity in front of other activities such as queries, and the **[!UICONTROL End]** activity after a series of activities.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. You can configure the **End** object so that it interrupts all of the workflow's ongoing tasks, including those that have not finished. Para ello, seleccione la opción correspondiente.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Triggering another workflow {#triggering-another-workflow}

Using the **[!UICONTROL External signal]** tab of an **[!UICONTROL End]** activity, you can trigger another workflow. Refer to the [External signal](../../automating/using/external-signal.md) section.

## Example {#example}

The following example shows how a complex workflow is executed with a **[!UICONTROL Start]** activity and several **[!UICONTROL End]** activities. The **[!UICONTROL Stop all tasks in progress]** box has been checked for the first **[!UICONTROL End]** activity. Once the corresponding task is finished, the entire workflow will be stopped: it will have the same effect as if the ![](assets/stop_darkgrey-24px.png) button had been selected (refer to the [Action bar](../../automating/using/workflow-interface.md#action-bar) section).

![](assets/wkf_start_end_example.png)


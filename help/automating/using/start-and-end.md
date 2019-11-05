---
title: Inicio y final
description: Las actividades Inicio y Fin le permiten marcar claramente dónde comienza y termina el flujo de trabajo.
page-status-flag: nunca activado
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Inicio y final{#start-and-end}

## Descripción {#description}

![](assets/start.png)

![](assets/end.png)

Las **[!UICONTROL Start]** actividades y **[!UICONTROL End]** permiten marcar claramente dónde comienza y termina el flujo de trabajo.

## Contexto de uso {#context-of-use}

La ejecución de un flujo de trabajo comienza con actividades sin transición de entrada y se detiene cuando ya no hay tareas en curso. Sin embargo, puede agregar **[!UICONTROL Start]** y **[!UICONTROL End]** realizar actividades para marcar claramente los puntos de inicio y fin de un flujo de trabajo. Esto resulta especialmente útil para flujos de trabajo relativamente complejos.

Se recomienda utilizar una **[!UICONTROL End]** actividad en lugar de dejar la última transición de un flujo de trabajo por sí solo para garantizar que el flujo de trabajo finalice correctamente.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Start]** o **[!UICONTROL End]** actividad en el flujo de trabajo.
1. Coloque la actividad **[!UICONTROL Start]** delante de otras actividades, como consultas, y la **[!UICONTROL End]** actividad después de una serie de actividades.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Puede configurar el objeto **End** para que interrumpa todas las tareas en curso del flujo de trabajo, incluidas las que no hayan finalizado. Para ello, seleccione la opción correspondiente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Activación de otro flujo de trabajo {#triggering-another-workflow}

Mediante la **[!UICONTROL External signal]** ficha de una **[!UICONTROL End]** actividad, puede activar otro flujo de trabajo. Consulte la sección Señal [](../../automating/using/external-signal.md) externa.

## Ejemplo {#example}

El siguiente ejemplo muestra cómo se ejecuta un flujo de trabajo complejo con una **[!UICONTROL Start]** actividad y varias **[!UICONTROL End]** actividades. La **[!UICONTROL Stop all tasks in progress]** casilla se ha marcado para la primera **[!UICONTROL End]** actividad. Una vez finalizada la tarea correspondiente, se detendrá todo el flujo de trabajo: tendrá el mismo efecto que si se hubiera seleccionado el ![](assets/stop_darkgrey-24px.png) botón (consulte la sección Barra [de](../../automating/using/workflow-interface.md#action-bar) acciones).

![](assets/wkf_start_end_example.png)


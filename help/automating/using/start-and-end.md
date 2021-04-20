---
solution: Campaign Standard
product: campaign
title: Inicio y final (Start y End)
description: Las actividades Start y End permiten marcar claramente dónde termina y dónde comienza el flujo de trabajo.
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 98%

---


# Inicio y final (Start y End){#start-and-end}

## Descripción {#description}

![](assets/start.png)

![](assets/end.png)

Las actividades **[!UICONTROL Start]** y **[!UICONTROL End]** permiten marcar claramente dónde termina y dónde comienza el flujo de trabajo.

## Contexto de uso {#context-of-use}

La ejecución de un flujo de trabajo comienza con actividades sin una transición de entrada y se detiene cuando ya no hay ninguna tarea en curso. Sin embargo, puede agregar actividades **[!UICONTROL Start]** y **[!UICONTROL End]** para marcar claramente los puntos de inicio y final de un flujo de trabajo. Esto resulta especialmente útil con flujos de trabajo relativamente complejos.

Se recomienda utilizar una actividad **[!UICONTROL End]** en lugar de dejar la última transición de un flujo de trabajo sola para garantizar que el flujo de trabajo finalice correctamente.

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Start]** o **[!UICONTROL End]** en el flujo de trabajo.
1. Ponga la actividad **[!UICONTROL Start]** delante de otras actividades como consultas y la actividad **[!UICONTROL End]** después de una serie de actividades.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Puede configurar el objeto **Final** para que interrumpa todas las tareas en curso del flujo de trabajo, incluidas las que no hayan finalizado. Para ello, seleccione la opción correspondiente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Activación de otro flujo de trabajo {#triggering-another-workflow}

En la pestaña **[!UICONTROL External signal]** de una actividad **[!UICONTROL End]**, puede activar otro flujo de trabajo. Consulte la sección [Señales externas](../../automating/using/external-signal.md).

## Ejemplo {#example}

El siguiente ejemplo muestra cómo se ejecuta un flujo de trabajo complejo con una actividad **[!UICONTROL Start]** y varias actividades **[!UICONTROL End]**. La casilla **[!UICONTROL Stop all tasks in progress]** se ha marcado para la primera actividad **[!UICONTROL End]**. Una vez finalizada la tarea correspondiente, se detendrá todo el flujo de trabajo: tendrá el mismo efecto que si se hubiera seleccionado el botón ![](assets/stop_darkgrey-24px.png) (consulte la sección [Barra de acciones](../../automating/using/workflow-interface.md#action-bar)).

![](assets/wkf_start_end_example.png)


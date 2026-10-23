---
title: Inicio y final (Start y End)
description: Las actividades Start y End permiten marcar claramente dónde termina y dónde comienza el flujo de trabajo.
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1dfc547f-747d-403e-a5b7-a68f56191c71
TQID: 'https://experienceleague.adobe.com/JbfMoJzvulqLurUn904RKXvg2aqb74BTTwFpSNkL9MU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 97%
---
# Inicio y final{#start-and-end}

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

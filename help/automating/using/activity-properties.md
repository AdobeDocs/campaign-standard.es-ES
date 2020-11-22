---
solution: Campaign Standard
product: campaign
title: Administración de propiedades de actividades
description: Obtenga información sobre cómo administrar las propiedades de las actividades de flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---


# Administración de propiedades de actividades {#activity-properties}

## Propiedades globales de una actividad {#global-properties-of-an-activity}

Cada actividad tiene una **[!UICONTROL General]** ficha que le permite modificar parámetros generales específicos de la actividad.

![](assets/activity-properties.png)

La **[!UICONTROL Properties]** ficha permite modificar los parámetros globales de la actividad, en particular la etiqueta y el ID. La configuración de esta ficha es opcional.

![](assets/activity-properties2.png)

## Administración de transiciones salientes de una actividad {#managing-an-activity-s-outbound-transitions}

De forma predeterminada, determinadas actividades no tienen una transición de salida. Puede agregar uno desde la **[!UICONTROL Transitions]** ficha o desde la ficha de la actividad **[!UICONTROL Properties]** para aplicar otros procesos a la población en el mismo flujo de trabajo.

Según las actividades, puede agregar varios tipos de transiciones salientes:

* **Transición** estándar: población calculada por la actividad
* **Transición sin población**: este tipo de transición saliente se puede agregar para continuar con el flujo de trabajo y no contiene ninguna población para no consumir ningún espacio innecesario en el sistema.
* **Rechaza**: población rechazada. Por ejemplo, si los datos de entrada de la actividad no se pudieron procesar porque eran incorrectos o estaban incompletos.
* **Complemento**: población restante después de ejecutar la actividad. Por ejemplo, si una actividad de segmentación está configurada para guardar solo un porcentaje de la población entrante.

Si corresponde, especifique un **[!UICONTROL Segment code]** valor para la transición saliente de la actividad. Este código de segmento le permitirá identificar de dónde provienen los subconjuntos de la población de destinatarios y, posteriormente, podrá servir para fines de personalización de mensajes.

## Opciones de ejecución de actividad {#activity-execution-options}

En la pantalla de propiedades de la actividad, hay una **[!UICONTROL Advanced options]** ficha que permite definir el modo y el comportamiento de ejecución de la actividad en caso de que se produzcan errores.

Para acceder a estas opciones, seleccione una actividad en un flujo de trabajo y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de la barra de acciones.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** field allows you to define the action to be carried out when the task is started. Existen tres opciones para esto:

* **Normal**: la actividad se ejecuta normalmente.
* **Habilitar pero no ejecutar**: la actividad está en pausa, y como consecuencia lo están los procesos futuros que le siguen. Esto puede resultar útil si desea estar presente cuando se inicie la tarea.
* **No habilitar**: la actividad no se ejecuta y, en consecuencia, tampoco todas las actividades siguientes (en la misma rama).

El **[!UICONTROL In case of error]** campo permite especificar la acción que se realizará en caso de que la actividad encuentre un error. Hay dos opciones disponibles para esto:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y, como resultado, tampoco se ejecuta ninguna de las actividades que la siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un Planificador colocado en la parte superior, esto debería activarse en la siguiente fecha de ejecución.

El **[!UICONTROL Behavior]** campo permite definir el procedimiento que se debe seguir si se utilizan tareas asincrónicas. Hay dos opciones disponibles para esto:

* **Tareas múltiples autorizadas**: se pueden ejecutar varias tareas al mismo tiempo, aunque la primera no haya finalizado.
* **La tarea actual tiene prioridad**: una vez que se está llevando a cabo una tarea, ésta tiene prioridad. Mientras una tarea siga en curso, no se ejecutará ninguna otra tarea.

El **[!UICONTROL Max. execution duration]** campo permite especificar una duración como &quot;30&quot; o &quot;1 h&quot;. Si la actividad no finaliza después de que haya transcurrido el tiempo especificado, se activa una alerta. Esto no afecta al funcionamiento del flujo de trabajo.

El **[!UICONTROL Affinity]** campo permite forzar la ejecución de un flujo de trabajo o una actividad de flujo de trabajo en un equipo concreto. Para ello, debe especificar una o varias afinidades para el flujo de trabajo o la actividad en cuestión.

El **[!UICONTROL Time zone]** campo permite seleccionar la zona horaria de la actividad. Adobe Campaign le permite administrar las diferencias horarias entre varios países en la misma instancia. La configuración aplicada se configura cuando se crea la instancia.

>[!NOTE]
>
>De forma predeterminada, si no hay ningún huso horario seleccionado, la actividad utilizará el huso horario definido en las propiedades del flujo de trabajo.

The **Comment** field is a free field that allows you to add a note.

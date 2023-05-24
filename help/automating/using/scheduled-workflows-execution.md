---
title: Ejecución superpuesta de flujos de trabajo programados
description: Obtenga información sobre cómo evitar la ejecución superpuesta de flujos de trabajo programados.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Ejecución superpuesta de flujos de trabajo programados{#preventing-overlapping-execution-of-scheduled-workflows}

## Acerca de la ejecución de flujos de trabajo programados

En Campaign Standard, el motor de flujos de trabajo garantiza que una instancia de flujo de trabajo se ejecute en un solo proceso. El bloqueo de actividades como importaciones, consultas de larga ejecución o escrituras en la base de datos impide la ejecución de cualquier otra tarea al ejecutarse.

Por otro lado, las actividades que no bloquean no bloquean la ejecución de otras tareas (normalmente actividades que esperan un evento como el **[!UICONTROL Scheduler]** actividad).

Esto puede dar lugar a un escenario en el que un flujo de trabajo basado en programación pueda empezar a ejecutarse incluso cuando la ejecución anterior de ese mismo flujo de trabajo aún no haya finalizado, lo que podría provocar problemas de datos inesperados.

Por lo tanto, al diseñar un flujo de trabajo programado que incluya varias actividades, debe asegurarse de que el flujo de trabajo no se vuelva a programar hasta que finalice. Para ello, debe configurar el flujo de trabajo para evitar su ejecución si una o más tareas de una ejecución anterior siguen pendientes.

## Configuración del flujo de trabajo

Para comprobar si una o más tareas de una ejecución de flujo de trabajo anterior siguen pendientes, debe utilizar un **[!UICONTROL Query]** y una **[!UICONTROL Test]** actividad.

1. Añadir un **[!UICONTROL Query]** actividad después de **[!UICONTROL Scheduler]** actividad y, a continuación, configúrela como se indica a continuación.

1. Cambie el recurso de la actividad a **[!UICONTROL WorkflowTaskDetail]**, lo que significa que se dirigirá a las tareas actuales del flujo de trabajo.

   ![](assets/scheduled-wkf-resource.png)

1. Configure la consulta con las reglas siguientes:

   ![](assets/scheduled-wkf-query.png)

   * La primera regla filtra la tarea actual (query2) así como la siguiente tarea de planificación (schedule2) que pertenece al flujo de trabajo actual.

      >[!NOTE]
      >
      >Cuando un **[!UICONTROL Scheduler]** La actividad se inicia e inmediatamente añade otra tarea de planificación para que se ejecute en la siguiente hora programada e inicie el flujo de trabajo. Por lo tanto, es importante filtrar tanto la consulta como las tareas programadas cuando se buscan tareas pendientes de una ejecución anterior.

   * La segunda regla determina si alguna tarea de una ejecución anterior del flujo de trabajo sigue activa (pendiente), lo que corresponde al estado de ejecución 0.

1. Añadir un **[!UICONTROL Test]** actividad para comprobar el número de tareas pendientes devueltas por el **[!UICONTROL Query]** actividad. Para ello, configure dos transiciones salientes.

   ![](assets/scheduled-wkf-test.png)

   * La primera transición continúa con la ejecución del flujo de trabajo si no hay tareas pendientes,
   * La segunda transición cancela la ejecución del flujo de trabajo si hay alguna tarea pendiente.

   ![](assets/scheduled-wkf-workflow.png)

Ahora puede configurar el resto del flujo de trabajo según sea necesario. Si la ejecución del flujo de trabajo se cancela debido a tareas pendientes, cuando el flujo de trabajo se ejecute de nuevo según la programación, puede seguir estos pasos. Esto garantiza que la ejecución del flujo de trabajo continúe solo si no hay tareas activas (pendientes) de una ejecución anterior.

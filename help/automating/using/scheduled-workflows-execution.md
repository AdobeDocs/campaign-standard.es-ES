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

En Campaign Standard, el motor de flujo de trabajo garantiza que una instancia de flujo de trabajo se ejecute únicamente mediante un proceso. Bloquear actividades como importaciones, consultas de larga duración o escrituras en la base de datos impide la ejecución de cualquier otra tarea al ejecutarse.

Por otro lado, las actividades que no bloquean no bloquean la ejecución de otras tareas (generalmente actividades que esperan un evento como la actividad **[!UICONTROL Scheduler]**).

Esto puede provocar un escenario en el que un flujo de trabajo basado en programación pueda comenzar a ejecutarse incluso cuando la ejecución anterior de ese mismo flujo de trabajo aún no haya finalizado, lo que puede provocar problemas de datos inesperados.

Por lo tanto, al diseñar un flujo de trabajo programado que incluya varias actividades, debe asegurarse de que el flujo de trabajo no se vuelva a programar hasta que finalice. Para ello, debe configurar el flujo de trabajo para evitar su ejecución si una o más tareas de una ejecución anterior siguen pendientes.

## Configuración del flujo de trabajo

Para comprobar si una o más tareas de una ejecución de flujo de trabajo anterior siguen pendientes, debe utilizar una actividad **[!UICONTROL Query]** y una actividad **[!UICONTROL Test]**.

1. Agregue una actividad **[!UICONTROL Query]** después de la actividad **[!UICONTROL Scheduler]** y configúrela de la siguiente manera:

1. Cambie el recurso de la actividad a **[!UICONTROL WorkflowTaskDetail]**, lo que significa que se dirigirá a las tareas actuales del flujo de trabajo.

   ![](assets/scheduled-wkf-resource.png)

1. Configure la consulta con las reglas siguientes:

   ![](assets/scheduled-wkf-query.png)

   * La primera regla filtra la tarea actual (query2) así como la siguiente tarea de programación (schedule2) que pertenece al flujo de trabajo actual.

      >[!NOTE]
      >
      >Cuando se inicia una actividad **[!UICONTROL Scheduler]**, inmediatamente agrega otra tarea de programación para que se ejecute en la siguiente hora programada e inicie el flujo de trabajo. Por lo tanto, es importante filtrar tanto la consulta como las tareas de programación al buscar tareas pendientes de una ejecución anterior.

   * La segunda regla determina si cualquier tarea de una ejecución anterior del flujo de trabajo sigue activa (pendiente), que corresponde al estado de ejecución 0.

1. Agregue una actividad **[!UICONTROL Test]** para comprobar el número de tareas pendientes que devuelve la actividad **[!UICONTROL Query]**. Para ello, configure dos transiciones salientes.

   ![](assets/scheduled-wkf-test.png)

   * La primera transición continúa la ejecución del flujo de trabajo si no hay tareas pendientes,
   * La segunda transición cancela la ejecución del flujo de trabajo si hay tareas pendientes.

   ![](assets/scheduled-wkf-workflow.png)

Ahora puede configurar el resto del flujo de trabajo según sea necesario. Si la ejecución del flujo de trabajo se cancela debido a tareas pendientes, cuando el flujo de trabajo se ejecuta de nuevo según la programación, puede seguir estos pasos. Esto garantizará que la ejecución del flujo de trabajo se realice únicamente si no hay tareas activas (pendientes) de una ejecución anterior.

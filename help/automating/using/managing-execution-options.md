---
title: Administración de opciones de ejecución
description: Obtenga información sobre cómo administrar las opciones de ejecución de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 7%

---

# Administración de opciones de ejecución {#managing-execution-options}

Para modificar las opciones de ejecución de un flujo de trabajo, utilice el botón ![](assets/edit_darkgrey-24px.png) para acceder a las propiedades del flujo de trabajo y seleccione la sección **[!UICONTROL Execution]** .

![](assets/wkf_execution_6.png)

Las opciones posibles son:

* **[!UICONTROL Default affinity]**: este campo permite forzar un flujo de trabajo o una actividad de flujo de trabajo para que se ejecute en un equipo en particular.

* **[!UICONTROL History in days]**: especifica el número de días después de los cuales se debe purgar el historial. El historial contiene elementos relacionados con el flujo de trabajo: registros, tareas, eventos (objetos técnicos vinculados a la operación del flujo de trabajo), así como archivos descargados por la actividad **[!UICONTROL Transfer file]**. El valor predeterminado es de 30 días para las plantillas de flujo de trabajo integradas.

   La depuración del historial se realiza mediante el flujo de trabajo técnico Database cleanup , que se ejecuta de forma predeterminada todos los días (consulte [List of technical workflows](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Si el campo **[!UICONTROL History in days]** se deja en blanco, su valor se considerará &quot;1&quot;, lo que significa que el historial se purgará después de 1 día.

* **[!UICONTROL Save SQL queries in the log]**: permite guardar las consultas SQL del flujo de trabajo en los registros.

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**: marque esta opción si desea que se registre todo el plan de ejecución. Está desactivado de forma predeterminada.

   Para obtener más información sobre esta opción, consulte esta [sección](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**: marque esta opción si desea poder ver los detalles de las transiciones.

   >[!CAUTION]
   >
   >Esta opción consume mucho espacio en el disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.

* **[!UICONTROL Execute in the engine (do not use in production)]**: permite ejecutar el flujo de trabajo localmente para fines de prueba de entorno de desarrollo.

* **[!UICONTROL Severity]**: permite especificar un nivel de prioridad para ejecutar flujos de trabajo en la instancia de Adobe Campaign. Los equipos de Adobe utilizan este campo solo para fines de monitorización.

La sección **[!UICONTROL Error management]** proporciona opciones adicionales que le permiten administrar cómo se comportan los flujos de trabajo en caso de errores. Estas opciones se detallan en la sección [Error management](../../automating/using/monitoring-workflow-execution.md#error-management) .

## Modo de diagnóstico {#diagnostic-mode}

>[!CAUTION]
>
>Esta opción puede afectar al rendimiento del flujo de trabajo de forma significativa y debe utilizarse con moderación.

Cuando está activada, la opción **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** de la sección **[!UICONTROL Execution]** de las propiedades del flujo de trabajo registra todo el plan de ejecución si una consulta tarda más de un minuto.

![](assets/wkf_diagnostic.png)

Después de activar esta opción e iniciar el flujo de trabajo, si la consulta tarda más de un minuto, se registrará el plan de ejecución. A continuación, puede recuperar el plan de ejecución utilizando un EXPLAIN ANALYZE.

Para obtener más información, consulte [Documentación PostgreSQL](https://www.postgresql.org/docs/9.4/using-explain.html).

Si tiene un análisis de secuencia en esta consulta, **[!UICONTROL Diagnostic mode]** también proporcionará recomendaciones para crear un índice con la ayuda de una expresión de filtro.

>[!NOTE]
>
> Estas recomendaciones están destinadas únicamente a fines de referencia y deben utilizarse cuidadosamente en función de su caso de uso.

![](assets/wkf_diagnostic_4.png)

Se deben cumplir las dos condiciones siguientes durante la ejecución del flujo de trabajo a las recomendaciones de déclencheur:

* El análisis de la secuencia tarda más del 40% de tiempo en la consulta.

* Las filas resultantes después del análisis de secuencia son inferiores al 1 % del total de filas presentes en la tabla.

Puede administrar la opción desde el menú avanzado seleccionando **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: Desde el  **[!UICONTROL Value]** campo , puede configurar una nueva hora para la ejecución de la consulta. Si la ejecución de la consulta supera este valor, se registrará el plan de ejecución.

   ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: Desde el  **[!UICONTROL Value]** campo , puede cambiar el porcentaje de tiempo de consulta que debe tardar el análisis de secuencia en generarse la recomendación.

   ![](assets/wkf_diagnostic_3.png)

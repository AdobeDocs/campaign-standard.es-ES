---
solution: Campaign Standard
product: campaign
title: Administración de opciones de ejecución
description: Obtenga información sobre cómo administrar las opciones de ejecución de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 14%

---


# Administración de opciones de ejecución {#managing-execution-options}

Para modificar las opciones de ejecución de un flujo de trabajo, utilice el botón ![](assets/edit_darkgrey-24px.png) para acceder a las propiedades del flujo de trabajo y seleccione la sección **[!UICONTROL Execution]** .

![](assets/wkf_execution_6.png)

Las opciones posibles son:

* **[!UICONTROL Default affinity]**: este campo permite forzar un flujo de trabajo o una actividad de flujo de trabajo para que se ejecute en un equipo en particular.

* **[!UICONTROL History in days]**: especifica el número de días después de los cuales se debe purgar el historial. El historial contiene elementos relacionados con el flujo de trabajo : registros, tareas, eventos (objetos técnicos vinculados a la operación del flujo de trabajo), así como archivos descargados por la actividad **[!UICONTROL Transfer file]**. El valor predeterminado es de 30 días para las plantillas de flujo de trabajo integradas.

   La depuración del historial se realiza mediante el flujo de trabajo técnico Database cleanup , que se ejecuta de forma predeterminada todos los días (consulte [List of technical workflows](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Si el campo **[!UICONTROL History in days]** se deja en blanco, su valor se considerará &quot;1&quot;, lo que significa que el historial se purgará después de 1 día.

* **[!UICONTROL Save SQL queries in the log]**: permite guardar las consultas SQL del flujo de trabajo en los registros.

* **[!UICONTROL Keep interim results]**: marque esta opción si desea poder ver los detalles de las transiciones.

   >[!CAUTION]
   >
   >Esta opción consume mucho espacio en el disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.

* **[!UICONTROL Execute in the engine (do not use in production)]**: permite ejecutar el flujo de trabajo localmente para fines de prueba de entorno de desarrollo.

* **[!UICONTROL Severity]**: permite especificar un nivel de prioridad para ejecutar flujos de trabajo en la instancia de Adobe Campaign. Los equipos de Adobe utilizan este campo solo para fines de monitorización.

La sección **[!UICONTROL Error management]** proporciona opciones adicionales que le permiten administrar cómo se comportan los flujos de trabajo en caso de errores. Estas opciones se detallan en la sección [Error management](../../automating/using/monitoring-workflow-execution.md#error-management) .

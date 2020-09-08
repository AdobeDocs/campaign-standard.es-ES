---
title: Administración de opciones de ejecución
description: Obtenga información sobre cómo administrar las opciones de ejecución de flujos de trabajo.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8ebded956ef52bb742160d62ebbd8095c390d51c
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 2%

---


# Administración de opciones de ejecución {#managing-execution-options}

Para modificar las opciones de ejecución de un flujo de trabajo, utilice el ![](assets/edit_darkgrey-24px.png) botón para acceder a las propiedades del flujo de trabajo y seleccione la **[!UICONTROL Execution]** sección.

![](assets/wkf_execution_6.png)

Las opciones posibles son:

* **[!UICONTROL Default affinity]**:: este campo permite forzar la ejecución de un flujo de trabajo o una actividad de flujo de trabajo en un equipo concreto.

* **[!UICONTROL History in days]**:: especifica el número de días después de los cuales se debe purgar el historial. El historial contiene elementos relacionados con el flujo de trabajo: registros, tareas, eventos (objetos técnicos vinculados a la operación de flujo de trabajo), así como archivos descargados por la **[!UICONTROL Transfer file]** actividad. El valor predeterminado es de 30 días para las plantillas de flujo de trabajo integradas.

   La depuración del historial se realiza mediante el flujo de trabajo técnico de limpieza de la base de datos, que se ejecuta de forma predeterminada todos los días (consulte [Lista de flujos de trabajo técnicos](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Si el **[!UICONTROL History in days]** campo se deja en blanco, su valor se considerará &quot;1&quot;, lo que significa que el historial se purgará después de 1 día.

* **[!UICONTROL Save SQL queries in the log]**:: permite guardar las consultas SQL del flujo de trabajo en los registros.

* **[!UICONTROL Keep interim results]**:: marque esta opción si desea poder realizar una vista del detalle de las transiciones. Advertencia: esta opción puede ralentizar considerablemente la ejecución del flujo de trabajo.

* **[!UICONTROL Execute in the engine (do not use in production)]**:: le permite ejecutar el flujo de trabajo de forma local, con fines de prueba de entorno de desarrollo.

* **[!UICONTROL Severity]**:: permite especificar un nivel de prioridad para la ejecución de flujos de trabajo en la instancia de Adobe Campaign. Este campo lo utilizan los equipos de Adobe sólo para fines de supervisión.

La **[!UICONTROL Error management]** sección proporciona opciones adicionales que le permiten administrar el comportamiento de los flujos de trabajo en caso de errores. Estas opciones se detallan en la sección Administración de [errores](../../automating/using/monitoring-workflow-execution.md#error-management) .

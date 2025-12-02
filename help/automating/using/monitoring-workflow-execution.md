---
title: Control de la ejecución del flujo de trabajo
description: Obtenga información sobre cómo monitorizar la ejecución de un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 6%

---

# Control de la ejecución del flujo de trabajo {#monitoring}

## Registro de flujo de trabajo y tareas {#workflow-log-and-tasks}

El icono ![](assets/printpreview_darkgrey-24px.png) abre el registro de flujo de trabajo y el menú de tareas.

El historial del flujo de trabajo se guarda durante el tiempo especificado en las opciones de ejecución del flujo de trabajo (consulte [Propiedades del flujo de trabajo](../../automating/using/managing-execution-options.md)). Durante esta duración, todos los mensajes se guardan, incluso después de un reinicio. Si no desea guardar los mensajes de una ejecución anterior, debe depurar el historial haciendo clic en el botón ![](assets/delete_darkgrey-24px.png).

La pestaña **[!UICONTROL Log]** contiene el historial de ejecución de todas las actividades o actividades seleccionadas. Indexa las operaciones realizadas y los errores de ejecución por orden cronológico.

![](assets/wkf_execution_4.png)

La pestaña **[!UICONTROL Tasks]** detalla la secuencia de ejecución de las actividades. Haga clic en una tarea para obtener más información.

![](assets/wkf_execution_5.png)

En estas dos listas:

* Haga clic en el contador para ver el número total de actividades según el filtro aplicado. El contador se muestra de forma predeterminada si el número de elementos de la lista es inferior a 30.
* El botón **[!UICONTROL Configure list]** le permite elegir la información mostrada, definir el orden de las columnas y ordenar la lista.
* Puede utilizar filtros para encontrar la información que necesita más rápido. Utilice el campo de búsqueda para buscar un texto específico en los nombres de las actividades de flujo de trabajo (por ejemplo: &quot;consulta&quot;) y registros.

## Administración de errores {#error-management}

Cuando se produce un error, el flujo de trabajo se detiene y la actividad que se estaba ejecutando cuando se produjo el error parpadea en rojo.

El estado del flujo de trabajo se vuelve rojo y el error se registra en el registro.

Puede configurar el flujo de trabajo para que no se detenga y continúe ejecutándose sin errores. Para ello, vaya a las propiedades del flujo de trabajo a través del botón ![](assets/edit_darkgrey-24px.png) y, en la sección **[!UICONTROL Execution]**, seleccione la opción **Ignorar** en el campo **En caso de error**.

En este caso, se anula la tarea errónea. Este modo es especialmente adecuado para flujos de trabajo diseñados para volver a intentar la operación más tarde (acciones periódicas).

>[!NOTE]
>
>Puede aplicar esta configuración individualmente para cada actividad. Para ello, seleccione una actividad y ábrala con la acción rápida ![](assets/edit_darkgrey-24px.png). A continuación, seleccione el modo de administración de errores en la ficha **Opciones de ejecución**. Ver [Opciones de ejecución de actividades](../../automating/using/activity-properties.md).

En las propiedades del [flujo de trabajo](../../automating/using/managing-execution-options.md), hay disponibles opciones adicionales relacionadas con la administración de errores.

![](assets/wkf_execution_error.png)

Las opciones posibles son las siguientes:

* **[!UICONTROL Supervisors]**: permite definir el grupo de personas al que se debe notificar (correo electrónico y notificación en la aplicación) si el flujo de trabajo encuentra un error. Si no se define ningún grupo, no se notificará a nadie. Para obtener más información sobre las notificaciones de Adobe Campaign, consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: permite especificar la acción que se va a realizar en caso de que la actividad encuentre un error. Hay dos opciones disponibles para esto:

   * **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
   * **Ignorar**: la actividad no se ejecuta y, como resultado, ninguna de las actividades que la siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un planificador en una posición anterior, el déclencheur debería ser la siguiente fecha de ejecución.

* **[!UICONTROL Consecutive errors]** : permite definir una serie de errores consecutivos que se autorizan antes de que la ejecución del flujo de trabajo se suspenda automáticamente.

   * Si el número especificado es **[!UICONTROL 0]**, o siempre que no se alcance el número especificado, se omiten las actividades que encuentren errores. Las demás ramas del flujo de trabajo se ejecutan normalmente.

   * Si se alcanza el número especificado, se suspende todo el flujo de trabajo y se convierte en **[!UICONTROL Erroneous]**. Si se han definido supervisores, se les notifica automáticamente por correo electrónico. Consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

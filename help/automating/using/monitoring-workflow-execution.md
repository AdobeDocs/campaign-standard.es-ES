---
solution: Campaign Standard
product: campaign
title: Control de la ejecución del flujo de trabajo
description: Obtenga información sobre cómo supervisar la ejecución de un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---


# Control de la ejecución del flujo de trabajo {#monitoring}

## Registro y tareas de flujo de trabajo {#workflow-log-and-tasks}

El icono ![](assets/printpreview_darkgrey-24px.png) abre el registro del flujo de trabajo y el menú de tarea.

El historial de flujo de trabajo se guarda durante el tiempo especificado en las opciones de ejecución de flujo de trabajo (consulte [Propiedades de flujo de trabajo](../../automating/using/managing-execution-options.md)). Durante este período, todos los mensajes se guardan, incluso después de un reinicio. Si no desea guardar los mensajes de una ejecución anterior, debe purgar el historial haciendo clic en el botón ![](assets/delete_darkgrey-24px.png).

La ficha **[!UICONTROL Log]** contiene el historial de ejecución de todas las actividades o actividades seleccionadas. Indexa las operaciones realizadas y los errores de ejecución por orden cronológico.

![](assets/wkf_execution_4.png)

La ficha **[!UICONTROL Tasks]** detalla la secuencia de ejecución de las actividades. Haga clic en una tarea para obtener más información.

![](assets/wkf_execution_5.png)

En estas dos listas:

* Haga clic en el contador para ver el número total de actividades según el filtro aplicado. El contador se muestra de forma predeterminada si el número de elementos de la lista es menor que 30.
* El botón **[!UICONTROL Configure list]** permite elegir la información mostrada, definir el orden de las columnas y ordenar la lista.
* Puede utilizar filtros para encontrar la información que necesita más rápidamente. Utilice el campo de búsqueda para buscar un texto específico en los nombres de actividades de flujo de trabajo (por ejemplo: &quot;consulta&quot;) y registros.

## Gestión de errores {#error-management}

Cuando se produce un error, el flujo de trabajo se pone en pausa y la actividad que se estaba ejecutando cuando se encontró el error se parpadea en rojo.

El estado del flujo de trabajo cambia a rojo y el error se registra en el registro.

Puede configurar el flujo de trabajo para que no se detenga y continúe ejecutándose sin errores. Para ello, vaya a las propiedades del flujo de trabajo mediante el botón ![](assets/edit_darkgrey-24px.png) y, en la sección **[!UICONTROL Execution]**, seleccione la opción **Ignorar** en el campo **En caso de error**.

En este caso, se anula la tarea errónea. Este modo es especialmente adecuado para flujos de trabajo diseñados para volver a intentar la operación más adelante (acciones periódicas).

>[!NOTE]
>
>Puede aplicar esta configuración individualmente para cada actividad. Para ello, seleccione una actividad y ábrala mediante la acción rápida ![](assets/edit_darkgrey-24px.png). A continuación, seleccione el modo de administración de errores en la ficha **Opciones de ejecución**. Consulte [opciones de ejecución de Actividad](../../automating/using/activity-properties.md).

En las [propiedades](../../automating/using/managing-execution-options.md) del flujo de trabajo, hay disponibles opciones adicionales relacionadas con la administración de errores.

![](assets/wkf_execution_error.png)

Las opciones posibles son:

* **[!UICONTROL Supervisors]**:: le permite definir el grupo de personas a las que se notificará (correo electrónico y notificaciones en la aplicación) si el flujo de trabajo encuentra un error. Si no se define ningún grupo, no se notificará a nadie. Para obtener más información sobre las notificaciones de Adobe Campaign, consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**:: permite especificar la acción que se realizará en caso de que la actividad encuentre un error. Hay dos opciones disponibles para esto:

   * **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
   * **Ignorar**: la actividad no se ejecuta y, como resultado, tampoco se ejecuta ninguna de las actividades que la siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un Planificador colocado en la parte superior, esto debería activarse en la siguiente fecha de ejecución.

* **[!UICONTROL Consecutive errors]** :: le permite definir una serie de errores consecutivos que se autorizan antes de que la ejecución del flujo de trabajo se suspenda automáticamente.

   * Si el número especificado es **[!UICONTROL 0]**, o si no se alcanza el número especificado, se omiten las actividades que encuentran errores. Las otras ramas del flujo de trabajo se ejecutan normalmente.

   * Si se alcanza el número especificado, se suspende todo el flujo de trabajo y se convierte en **[!UICONTROL Erroneous]**. Si se han definido supervisores, se les notifica automáticamente por correo electrónico. Consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

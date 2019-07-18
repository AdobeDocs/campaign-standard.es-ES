---
title: Ejecución de un flujo de trabajo
seo-title: Ejecución de un flujo de trabajo
description: Ejecución de un flujo de trabajo
seo-description: Obtenga información sobre cómo ejecutar y supervisar un flujo de trabajo.
page-status-flag: no activado nunca
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: flujo de trabajo general operation
discoiquuid: 906 c 85 ea -83 b 7-4268-86 da-cd 353 f 1 dc 591
context-tags: flujo de trabajo, información general; flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

Un flujo de trabajo siempre se inicia manualmente. However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
>Recomendamos que no ejecute más de 5 flujos de trabajo simultáneamente. Cuando se ejecutan demasiados flujos de trabajo al mismo tiempo, el sistema puede agotar la cantidad de recursos y volverse inestable. También recomendamos que distribuya los flujos de trabajo a través del tiempo.

Acciones relacionadas con la ejecución (iniciar, parar, pausar, etc.) are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

En un flujo de trabajo, el resultado de cada actividad se envía generalmente a la siguiente actividad a través de una transición, representada por una flecha.

Una transición no termina si no está vinculada a una actividad de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Se puede ejecutar un flujo de trabajo que contenga transiciones inagotadas: se generará un mensaje de advertencia y el flujo de trabajo se pausará una vez alcanzado la transición, pero esto no generará un error. También puede iniciar un flujo de trabajo sin haber terminado completamente el diseño y puede completarlo mientras avanza.

Una vez ejecutado la actividad, el número de registros enviados en la transición se muestra por encima.

![](assets/wkf_transition_count.png)

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Puede ver los datos y la estructura de datos.

De forma predeterminada, sólo se puede acceder a los detalles de la última transición del flujo de trabajo. To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>Esta opción consume mucha memoria y está diseñada para ayudarle a construir un flujo de trabajo y garantizar que esté configurado y comportado correctamente. Déjelo desactivado en las instancias de producción.

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. Para ello, edite los campos correspondientes y confirme las modificaciones.

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

You can find more details and examples of REST calls in the [API documentation.](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

El ciclo de vida de un flujo de trabajo incluye tres pasos principales y cada paso está vinculado a un estado y a un color:

* **Edición** (gris)

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). El servidor aún no administra el flujo de trabajo y puede modificarse sin riesgo alguno.

* **Progreso** (azul)

   Una vez completada la fase inicial de diseño, el flujo de trabajo se puede iniciar y el servidor lo gestiona.

* **Finalizado** (verde)

   Un flujo de trabajo termina una vez que ya no hay tareas en curso o cuando un operador ha detenido explícitamente la instancia.

Una vez que se ha iniciado, un flujo de trabajo también puede tener otros dos estados:

* **Advertencia** (amarillo)

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **Erróneo** (rojo)

   Se produjo un error cuando se ejecutó un flujo de trabajo. El flujo de trabajo se detuvo y el usuario debe llevar a cabo una acción. To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

La lista de actividades de marketing permite mostrar todos los flujos de trabajo y sus estados. For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

Los iconos de la barra de acciones permiten iniciar, rastrear y modificar la ejecución del flujo de trabajo. See [Action bar](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Inicio**

The ![](assets/play_darkgrey-24px.png) button starts executing a workflow, which then takes on the **In progress** (blue) status. Si el flujo de trabajo se ha pausado, se reanuda; de lo contrario, se inicia y las actividades iniciales se activan.

>[!NOTE]
>
>Comenzar es un proceso asíncrono: La solicitud se guarda y el motor de ejecución del flujo de trabajo lo procesará lo más pronto posible.

**Pausar**

The ![](assets/pause_darkgrey-24px.png) button pauses the execution. The workflow takes on the **Warning** (yellow) status. No se activará ninguna actividad hasta que se reanude, pero las operaciones en curso no se suspenden.

**Detener**

The ![](assets/stop_darkgrey-24px.png) button stops a workflow that is being executed, which will then take on the **Finished** (green) status. Las operaciones en curso se interrumpen si es posible y las importaciones o consultas SQL en curso se cancelan inmediatamente. No se puede reanudar desde el flujo de trabajo desde el mismo lugar en el que se detuvo.

**Reiniciar**

The ![](assets/pauseplay_darkgrey-24px.png) button involves stopping, then restarting a workflow. En la mayoría de los casos, esto permite reiniciar más rápido. It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

Cuando se seleccionan una o varias actividades en un flujo de trabajo, se pueden realizar otras acciones, como:

**Ejecución inmediata**

![](assets/pending_darkgrey-24px.png) El botón inicia todas las actividades pendientes seleccionadas lo antes posible.

**Ejecución normal**

The ![](assets/check_darkgrey-24px.png) button reactivates any paused or deactivated activities.

**Ejecución suspendida**

![](assets/check_pause_darkgrey-24px.png) El botón pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todos los que lo siguen (en la misma rama) no se ejecutan.

**Sin ejecución**

The ![](assets/checkdisable.png) button deactivates any selected activities.

>[!NOTE]
>
>Las acciones rápidas permiten acceder a distintas acciones relacionadas con una actividad en particular y aparecer cuando se selecciona una actividad.

## Monitoring {#monitoring}

![](assets/printpreview_darkgrey-24px.png) El icono abre el registro de flujo de trabajo y el menú de tareas.

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). Durante esta duración, se guardan todos los mensajes, incluso después de reiniciar. If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

**[!UICONTROL Log]** La ficha contiene el historial de ejecución de todas las actividades o de cualquier actividad seleccionada. Indexa las operaciones realizadas y los errores de ejecución por orden cronológico.

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. Haga clic en una tarea para obtener más información.

![](assets/wkf_execution_5.png)

En estas dos listas:

* Haga clic en el contador para ver la cantidad total de actividades según el filtro aplicado. El contador se muestra de forma predeterminada si el número de elementos de la lista es inferior a 30.
* The **[!UICONTROL Configure list]** button allows you to choose the information displayed, define the column order, and sort the list.
* Puede utilizar filtros para encontrar la información que necesita. Utilice el campo de búsqueda para buscar un texto específico en los nombres de actividades del flujo de trabajo (por ejemplo: " consulta ") y registros.

## Error management {#error-management}

Cuando se produce un error, el flujo de trabajo se pausa y la actividad que se estaba ejecutando cuando se detectó el error se bloquea.

El estado del flujo de trabajo se activa y el error se registra en el registro.

Puede configurar el flujo de trabajo para que no se pause y siga ejecutándose sin errores. To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

En este caso, se anulará la tarea errónea. Este modo es especialmente adecuado para los flujos de trabajo diseñados para volver a intentar la operación más adelante (acciones periódicas).

>[!NOTE]
>
>Puede aplicar esta configuración individualmente para cada actividad. To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. See [Activity execution options](../../automating/using/executing-a-workflow.md#activity-execution-options).

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. Siempre y cuando no se llegue a este número, se ignorarán los elementos erróneos y las demás ramas de flujo de trabajo se ejecutan normalmente. Si se alcanza este número, el flujo de trabajo se suspende y se notifica automáticamente a los supervisores de flujo de trabajo (correo electrónico y notificación en la aplicación). See [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties) and [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

Los supervisores también pueden definirse en las propiedades de ejecución del flujo de trabajo.

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

**[!UICONTROL Default affinity]** El campo permite forzar un flujo de trabajo o una actividad de flujo de trabajo que se ejecute en un equipo concreto.

In the **[!UICONTROL History in days]** field, specify the duration after which the history must be purged.

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. Advertencia: marcar esta opción puede ralentizar significativamente la ejecución del flujo de trabajo.

**[!UICONTROL Severity]** El campo permite especificar un nivel de prioridad para ejecutar flujos de trabajo en la instancia de Adobe Campaign. Los flujos de trabajo críticos se ejecutarán primero.

The **[!UICONTROL Supervisors]** field is where you can define the group of people to notify (email and in-app notification) if the workflow encounters an error. Si no se define ningún grupo, no se notificará a nadie. For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

The **[!UICONTROL In case of error]** field allows you to specify the action to be carried out should the activity encounter an error. Esto ofrece dos opciones:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. The workflow status is then **Erroneous** and the color associated turns red. Una vez solucionado el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y como resultado ninguna de las actividades que siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un programador colocado hacia arriba, esto debería activarse en la siguiente fecha de ejecución.

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. Las demás ramas de flujo de trabajo se ejecutan normalmente.
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. Si los supervisores se han definido, se les notificará automáticamente por correo electrónico.

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. Esta ficha permite modificar los parámetros generales de la actividad, especialmente la etiqueta y el ID. La configuración de esta ficha es opcional.

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

De forma predeterminada, determinadas actividades no tienen una transición saliente. You can add one from the **[!UICONTROL Transitions]** tab or from the activity's **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

Según las actividades, puede agregar varios tipos de transiciones salientes:

* Transición estándar: población calculada por la actividad
* Transición sin población: este tipo de transición saliente se puede agregar para continuar con el flujo de trabajo y no contiene ninguna población para no consumir espacio innecesario en el sistema.
* Rechazos: población rechazada. Por ejemplo, si los datos de entrada de la actividad no se pudieron procesar porque era incorrecto o incompleto.
* Complementar: población restante después de ejecutar la actividad. Por ejemplo, si una actividad de segmentación está configurada para guardar únicamente un porcentaje de la población entrante.

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. Este código de segmento permite identificar dónde provienen los subconjuntos de la población objetivo y, posteriormente, puede servir para personalizar los mensajes.

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** field allows you to define the action to be carried out when the task is started. Existen tres opciones para:

* **Normal**: la actividad se ejecuta normalmente.
* **Habilitar pero no ejecutar**: La actividad está pausada y, como consecuencia, también es cualquier proceso futuro. Esto puede resultar útil si desea estar presente cuando se inicie la tarea.
* **No habilite**: la actividad no se ejecuta y, como consecuencia, ninguna de las actividades sigue (en la misma rama).

The **[!UICONTROL In case of error]** field allows you to specify the action to be carried out should the activity encounter an error. Esto ofrece dos opciones:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. The workflow status is then **Erroneous** and the color associated turns red. Una vez solucionado el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y como resultado ninguna de las actividades que siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un programador colocado hacia arriba, esto debería activarse en la siguiente fecha de ejecución.

The **[!UICONTROL Behavior]** field allows you to define the procedure to follow if asynchronous tasks are used. Esto ofrece dos opciones:

* **Varias tareas autorizadas**: se pueden ejecutar varias tareas al mismo tiempo aunque no haya finalizado la primera.
* **La tarea actual tiene prioridad**: una vez que una tarea está en curso, tiene prioridad. Siempre que una tarea esté aún en progreso, no se ejecutará ninguna otra tarea.

**[!UICONTROL Max. execution duration]** El campo permite especificar una duración como "30 s" o "1 h". Si la actividad no termina después de que haya transcurrido la duración especificada, se activa una alerta. Esto no afecta a la forma en que funciona el flujo de trabajo.

**[!UICONTROL Affinity]** El campo permite forzar un flujo de trabajo o una actividad de flujo de trabajo que se ejecute en un equipo concreto. Para ello, debe especificar una o varias afinidades para el flujo de trabajo o la actividad en cuestión.

**[!UICONTROL Time zone]** El campo permite seleccionar el huso horario de la actividad. Adobe Campaign permite administrar las diferencias horarias entre varios países en la misma instancia. La configuración aplicada se configura cuando se crea la instancia.

**El** campo Comentario es un campo gratuito que permite agregar una nota.

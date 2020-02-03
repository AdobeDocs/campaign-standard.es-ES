---
title: Ejecución de un flujo de trabajo
description: Obtenga información sobre cómo ejecutar y supervisar un flujo de trabajo.
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Ejecución de un flujo de trabajo{#executing-a-workflow}

## Acerca de la ejecución del flujo de trabajo {#about-workflow-execution}

Un flujo de trabajo siempre se inicia manualmente. Sin embargo, una vez iniciada, puede permanecer inactiva, según la información especificada en una actividad de [Programador](../../automating/using/scheduler.md) .

>[!CAUTION]
>
> Adobe recomienda a los clientes dar prioridad a las ejecuciones de flujos de trabajo y ejecutar hasta veinte ejecuciones de flujos de trabajo concurrentes para lograr de forma consistente el máximo rendimiento en toda la instancia. Se pueden planificar más de veinte ejecuciones de flujo de trabajo simultáneas que se ejecutarán secuencialmente de forma predeterminada. Puede ajustar la configuración predeterminada para el número máximo de ejecuciones de flujo de trabajo simultáneas enviando un ticket al Servicio de atención al cliente.

Acciones relacionadas con la ejecución (inicio, parada, pausa, etc.) son procesos **asincrónicos** : el comando se guarda y se hará efectivo cuando el servidor esté disponible para aplicarlo.

En un flujo de trabajo, el resultado de cada actividad generalmente se envía a la siguiente actividad mediante una transición, representada por una flecha.

Una transición no termina si no está vinculada a una actividad de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Se puede seguir ejecutando un flujo de trabajo que contenga transiciones sin terminar: se generará un mensaje de advertencia y el flujo de trabajo se pausará una vez que alcance la transición, pero esto no generará un error. También puede iniciar un flujo de trabajo sin haber terminado completamente el diseño y puede completarlo a medida que avanza.

Una vez ejecutada una actividad, el número de registros enviados en la transición se muestra encima.

![](assets/wkf_transition_count.png)

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Puede ver los datos y la estructura de datos.

De forma predeterminada, solo se puede acceder a los detalles de la última transición del flujo de trabajo. Para poder acceder a los resultados de las actividades anteriores, debe comprobar la **[!UICONTROL Keep interim results]**opción de la**[!UICONTROL Execution]** sección de las propiedades del flujo de trabajo antes de iniciar el flujo de trabajo.

>[!NOTE]
>
>Esta opción consume mucha memoria y está diseñada para ayudar a construir un flujo de trabajo y garantizar que esté correctamente configurado y se comporte. Deje sin marcar las instancias de producción.

Cuando una transición está abierta, puede editar su imagen **[!UICONTROL Label]**o vincularla**[!UICONTROL Segment code]** . Para ello, edite los campos correspondientes y confirme las modificaciones.

## Control de un flujo de trabajo desde la API de REST {#controlling-a-workflow-from-the-rest-api}

Con la API de REST, puede **iniciar**, **pausar**, **reanudar** y **detener** un flujo de trabajo.

Puede encontrar más detalles y ejemplos de llamadas REST en la documentación de la [API.](../../api/using/controlling-a-workflow.md)

## Ciclo de vida {#life-cycle}

El ciclo de vida de un flujo de trabajo incluye tres pasos principales y cada paso está vinculado a un estado y un color:

* **Edición** (gris)

   Esta es la fase de diseño inicial de un flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow)). El servidor aún no gestiona el flujo de trabajo y se puede modificar sin ningún riesgo.

* **En curso** (azul)

   Una vez finalizada la fase de diseño inicial, el servidor puede iniciar y gestionar el flujo de trabajo.

* **Finalizado** (verde)

   Un flujo de trabajo finaliza cuando ya no hay tareas en curso o cuando un operador ha detenido explícitamente la instancia.

Una vez iniciado, un flujo de trabajo también puede tener otros dos estados:

* **Advertencia** (amarillo)

   El flujo de trabajo no pudo finalizar o se detuvo con los botones ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png) .

* **Erróneo** (rojo)

   Error al ejecutar un flujo de trabajo. El flujo de trabajo se detuvo y el usuario debe realizar una acción. Para obtener más información sobre este error, utilice el ![](assets/printpreview_darkgrey-24px.png) botón para acceder al registro del flujo de trabajo (consulte [Supervisión](#monitoring)).

La lista de actividades de marketing le permite mostrar todos los flujos de trabajo, así como sus estados. Para obtener más información sobre esto, consulte [Administración de actividades](../../start/using/marketing-activities.md#about-marketing-activities)de marketing.

![](assets/wkf_execution_3.png)

## Comandos de ejecución {#execution-commands}

Los iconos de la barra de acciones le permiten iniciar, rastrear y modificar la ejecución de un flujo de trabajo. Consulte Barra [de acciones](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Inicio**

El ![](assets/play_darkgrey-24px.png) botón comienza a ejecutar un flujo de trabajo y, a continuación, adopta el estado **En curso** (azul). Si el flujo de trabajo estaba en pausa, se reanuda; de lo contrario, se inicia y las actividades iniciales se activan.

>[!NOTE]
>
>El inicio es un proceso asincrónico: la solicitud se guarda y el motor de ejecución del flujo de trabajo la procesará lo antes posible.

**Pausar**

El ![](assets/pause_darkgrey-24px.png) botón pone en pausa la ejecución. El flujo de trabajo adopta el estado **Advertencia** (amarillo). No se activarán nuevas actividades hasta que se reanuden, pero las operaciones en curso no se suspenden.

**Detener**

El ![](assets/stop_darkgrey-24px.png) botón detiene un flujo de trabajo que se está ejecutando y que luego pasará al estado **Finalizado** (verde). Las operaciones en curso se interrumpen si es posible y las importaciones o consultas SQL en curso se cancelan inmediatamente. No se puede reanudar desde el flujo de trabajo desde el mismo lugar en que se detuvo.

**Reiniciar**

El ![](assets/pauseplay_darkgrey-24px.png) botón implica detener y, a continuación, reiniciar un flujo de trabajo. En la mayoría de los casos, esto le permite reiniciar más rápido. También puede resultar útil automatizar el reinicio una vez que la detención tarde una cierta cantidad de tiempo, ya que el ![](assets/play_darkgrey-24px.png) botón solo está disponible cuando la detención es efectiva.

Cuando se seleccionan una o varias actividades de un flujo de trabajo, se pueden realizar otras acciones, como:

**Ejecución inmediata**

El ![](assets/pending_darkgrey-24px.png) botón inicia las actividades pendientes seleccionadas lo antes posible.

**Ejecución normal**

El ![](assets/check_darkgrey-24px.png) botón reactiva cualquier actividad pausada o desactivada.

**Ejecución suspendida**

El ![](assets/check_pause_darkgrey-24px.png) botón pone en pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todas las que la siguen (en la misma rama), no se ejecutan.

**Sin ejecución**

El ![](assets/checkdisable.png) botón desactiva las actividades seleccionadas.

>[!NOTE]
>
>Las acciones rápidas le permiten acceder a diferentes acciones relacionadas con una actividad en particular y aparecen cuando se selecciona una actividad.

## Monitoreo {#monitoring}

El ![](assets/printpreview_darkgrey-24px.png) icono abre el registro del flujo de trabajo y el menú de tareas.

El historial de flujo de trabajo se guarda durante el tiempo especificado en las opciones de ejecución de flujo de trabajo (consulte las propiedades [de](#workflow-properties)flujo de trabajo). Durante este período, todos los mensajes se guardan, incluso después de un reinicio. Si no desea guardar los mensajes de una ejecución anterior, debe depurar el historial haciendo clic en el ![](assets/delete_darkgrey-24px.png) botón.

La **[!UICONTROL Log]**ficha contiene el historial de ejecución de todas las actividades o de cualquier actividad seleccionada. Indice las operaciones realizadas y los errores de ejecución por orden cronológico.

![](assets/wkf_execution_4.png)

La **[!UICONTROL Tasks]**ficha detalla la secuencia de ejecución de las actividades. Haga clic en una tarea para obtener más información.

![](assets/wkf_execution_5.png)

En estas dos listas:

* Haga clic en el contador para ver el número total de actividades según el filtro aplicado. El contador se muestra de forma predeterminada si el número de elementos de la lista es menor que 30.
* El **[!UICONTROL Configure list]**botón permite elegir la información mostrada, definir el orden de las columnas y ordenar la lista.
* Puede utilizar filtros para encontrar la información que necesita más rápidamente. Utilice el campo de búsqueda para buscar un texto específico en los nombres de actividades de flujo de trabajo (por ejemplo: &quot;query&quot;) y registros.

## Gestión de errores {#error-management}

Cuando se produce un error, el flujo de trabajo se pone en pausa y la actividad que se estaba ejecutando cuando se encontró el error se parpadea en rojo.

El estado del flujo de trabajo cambia a rojo y el error se registra en el registro.

Puede configurar el flujo de trabajo para que no se detenga y continúe ejecutándose sin errores. Para ello, vaya a las propiedades del flujo de trabajo mediante el ![](assets/edit_darkgrey-24px.png) botón y, en la **[!UICONTROL Execution]**sección , seleccione la opción** Ignorar **en el campo** En caso de error **.

En este caso, se anula la tarea errónea. Este modo es especialmente adecuado para flujos de trabajo diseñados para volver a intentar la operación más adelante (acciones periódicas).

>[!NOTE]
>
>Puede aplicar esta configuración individualmente para cada actividad. Para ello, seleccione una actividad y ábrala con la acción rápida ![](assets/edit_darkgrey-24px.png). A continuación, seleccione el modo de administración de errores en la ficha Opciones **de** ejecución. Consulte Opciones [de ejecución de actividades](#activity-execution-options).

La **[!UICONTROL Execution]**sección de las propiedades del flujo de trabajo también le permite definir un número de**[!UICONTROL Consecutive errors]** ellas autorizadas antes de que la ejecución del flujo de trabajo se suspenda automáticamente. Mientras no se alcance este número, se ignorarán los elementos erróneos y las demás ramas del flujo de trabajo se ejecutarán normalmente. Si se alcanza este número, el flujo de trabajo se suspende y se notifica automáticamente a los supervisores del flujo de trabajo (notificación por correo electrónico y en la aplicación). Consulte Propiedades [](#workflow-properties) del flujo de trabajo y notificaciones [de](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

Los supervisores también se pueden definir en las propiedades de ejecución del flujo de trabajo.

## Propiedades del flujo de trabajo {#workflow-properties}

Para modificar las opciones de ejecución de un flujo de trabajo, utilice el ![](assets/edit_darkgrey-24px.png) botón para acceder a las propiedades del flujo de trabajo y seleccione la **[!UICONTROL Execution]**sección.

El **[!UICONTROL Default affinity]**campo permite forzar la ejecución de un flujo de trabajo o una actividad de flujo de trabajo en un equipo concreto.

En el **[!UICONTROL History in days]**campo, especifique la duración después de la cual se debe purgar el historial.

Si es necesario, puede seleccionar las opciones **[!UICONTROL Save SQL queries in the log]**y**[!UICONTROL Execute in the engine (do not use in production)]** .

Marque la **[!UICONTROL Keep interim results]**opción si desea ver el detalle de las transiciones. Advertencia: esta opción puede ralentizar considerablemente la ejecución del flujo de trabajo.

El **[!UICONTROL Severity]**campo permite especificar un nivel de prioridad para la ejecución de flujos de trabajo en la instancia de Adobe Campaign. Los flujos de trabajo críticos se ejecutarán primero.

En el **[!UICONTROL Supervisors]**campo se puede definir el grupo de personas a las que se debe notificar (correo electrónico y notificaciones en la aplicación) si el flujo de trabajo encuentra un error. Si no se define ningún grupo, no se notificará a nadie. Para obtener más información sobre las notificaciones de Adobe Campaign, consulte las notificaciones[de](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

El **[!UICONTROL In case of error]**campo permite especificar la acción que se realizará en caso de que la actividad encuentre un error. Hay dos opciones disponibles para esto:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y, por lo tanto, tampoco lo son las actividades que le siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un programador colocado en la secuencia de inicio, esto debería activarse en la siguiente fecha de ejecución.

   Al seleccionar esta opción, también puede definir un número de **[!UICONTROL Consecutive errors]**personas autorizadas:

   * Si el número especificado es **[!UICONTROL 0]**o si no se alcanza el número especificado, se omiten las actividades con errores. Las otras ramas del flujo de trabajo se ejecutan normalmente.
   * Si se alcanza el número especificado, todo el flujo de trabajo se suspende y se convierte en **[!UICONTROL Erroneous]**. Si se han definido supervisores, se les notifica automáticamente por correo electrónico.

![](assets/wkf_execution_6.png)

## Propiedades de la actividad {#activity-properties}

### Propiedades generales de una actividad {#general-properties-of-an-activity}

Cada actividad tiene una **[!UICONTROL Properties]**ficha. Esta ficha permite modificar los parámetros generales de la actividad, en particular la etiqueta y el ID. La configuración de esta ficha es opcional.

### Administración de las transiciones de salida de una actividad {#managing-an-activity-s-outbound-transitions}

De forma predeterminada, determinadas actividades no tienen una transición de salida. Puede agregar uno desde la **[!UICONTROL Transitions]**ficha o desde la ficha de la actividad**[!UICONTROL Properties]** para aplicar otros procesos a la población del mismo flujo de trabajo.

Según las actividades, puede agregar varios tipos de transiciones de salida:

* Transición estándar: población calculada por la actividad
* Transición sin población: este tipo de transición saliente se puede agregar para continuar con el flujo de trabajo y no contiene ninguna población para no consumir ningún espacio innecesario en el sistema.
* Rechaza: población rechazada. Por ejemplo, si los datos de entrada de la actividad no se pudieron procesar porque eran incorrectos o estaban incompletos.
* Complemento: población restante después de ejecutar la actividad. Por ejemplo, si una actividad de segmentación está configurada para guardar solo un porcentaje de la población entrante.

Si corresponde, especifique un **[!UICONTROL Segment code]**para la transición de salida de la actividad. Este código de segmento le permitirá identificar de dónde provienen los subconjuntos de la población objetivo y, posteriormente, podrá servir para fines de personalización de mensajes.

### Opciones de ejecución de actividades {#activity-execution-options}

En la pantalla de propiedades de la actividad, hay una **[!UICONTROL Advanced options]**ficha que permite definir el modo y el comportamiento de ejecución de la actividad en caso de que se produzcan errores.

Para acceder a estas opciones, seleccione una actividad en un flujo de trabajo y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de la barra de acciones.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]**field allows you to define the action to be carried out when the task is started. Existen tres opciones para esto:

* **Normal**: la actividad se ejecuta normalmente.
* **Habilitar pero no ejecutar**: la actividad se pone en pausa y, como consecuencia, también lo hacen los procesos futuros que se produzcan a continuación. Esto puede resultar útil si desea estar presente cuando se inicie la tarea.
* **No habilitar**: la actividad no se ejecuta y, en consecuencia, tampoco todas las actividades siguientes (en la misma rama).

El **[!UICONTROL In case of error]**campo permite especificar la acción que se realizará en caso de que la actividad encuentre un error. Hay dos opciones disponibles para esto:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y, por lo tanto, tampoco lo son las actividades que le siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un programador colocado en la secuencia de inicio, esto debería activarse en la siguiente fecha de ejecución.

El **[!UICONTROL Behavior]**campo permite definir el procedimiento que se debe seguir si se utilizan tareas asincrónicas. Hay dos opciones disponibles para esto:

* **Múltiples tareas autorizadas**: se pueden ejecutar varias tareas al mismo tiempo, aunque la primera no haya finalizado.
* **La tarea actual tiene prioridad**: una vez que una tarea está en curso, se da prioridad. Mientras una tarea siga en curso, no se ejecutará ninguna otra.

El **[!UICONTROL Max. execution duration]**campo permite especificar una duración como &quot;30&quot; o &quot;1 h&quot;. Si la actividad no finaliza una vez transcurrido el tiempo especificado, se activa una alerta. Esto no afecta al funcionamiento del flujo de trabajo.

El **[!UICONTROL Affinity]**campo permite forzar la ejecución de un flujo de trabajo o una actividad de flujo de trabajo en un equipo concreto. Para ello, debe especificar una o varias afinidades para el flujo de trabajo o la actividad en cuestión.

El **[!UICONTROL Time zone]**campo permite seleccionar el huso horario de la actividad. Adobe Campaign permite administrar las diferencias horarias entre varios países en la misma instancia. La configuración aplicada se configura cuando se crea la instancia.

>[!NOTE]
>
>De forma predeterminada, si no hay ningún huso horario seleccionado, la actividad utilizará el huso horario definido en las propiedades del flujo de trabajo.

El campo **Comentario** es un campo gratuito que permite agregar una nota.

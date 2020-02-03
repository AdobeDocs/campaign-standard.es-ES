---
title: Prácticas recomendadas de flujos de trabajo
description: Aprenda a aplicar las prácticas recomendadas a los flujos de trabajo.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Prácticas recomendadas del flujo de trabajo{#workflow-best-practices}

Con Adobe Campaign, puede configurar todos los tipos de flujo de trabajo para realizar un gran número de tareas. Sin embargo, al diseñar y ejecutar los flujos de trabajo, debe ser muy prudente, ya que una implementación incorrecta puede provocar errores de rendimiento, errores y problemas de plataforma. A continuación encontrará una lista de prácticas recomendadas y sugerencias para la solución de problemas.

>[!NOTE]
>
>Un usuario avanzado de Adobe Campaign debe realizar el diseño y la ejecución del flujo de trabajo.

## Asignación de nombres{#naming}

Para facilitar la solución de problemas del flujo de trabajo, Adobe recomienda nombrar y etiquetar los flujos de trabajo de forma explícita. Rellene el campo de descripción del flujo de trabajo para resumir el proceso que se va a realizar de modo que el operador pueda comprenderlo fácilmente.
Si el flujo de trabajo forma parte de un proceso que implica varios flujos de trabajo, puede utilizar los números al introducir una etiqueta para ordenarlos con claridad.

Por ejemplo:

* 001: Importación: Importar destinatarios
* 002: Importación: Importar ventas
* 003: Importación: Importar detalles de ventas
* 010: Exportación: Exportar “logs” de envío
* 011: Exportación: Exportar “logs” de seguimiento

## Duplicar flujos de trabajo{#duplicating-workflows}

Puede duplicar flujos de trabajo. En la página **[!UICONTROL Marketing Activities]**, pase el ratón sobre el flujo de trabajo y haga clic en**[!UICONTROL Duplicate element]**. Una vez duplicadas, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo. Se puede editar la copia del flujo de trabajo.

![](assets/duplicating_workflow.png)

## Ejecución{#execution}

### Número de flujos de trabajo

De forma predeterminada, se recomienda no ejecutar más de 20 ejecuciones de flujos de trabajo activos simultáneamente. Después de alcanzar ese límite, los flujos de trabajo se colocarán en la cola para no afectar al rendimiento. Del mismo modo, Adobe recomienda que extienda la ejecución del flujo de trabajo con el paso del tiempo.
En contextos específicos, es posible que necesite ejecutar más de 20 flujos de trabajo. No se aplica a los flujos de trabajo que esperan una ejecución programada.  Si es así, debe consultar los casos de uso con un experto en campañas y ponerse en contacto con el Servicio de atención al cliente de Adobe para aumentar el límite.

### Frecuencia

Un flujo de trabajo no se puede ejecutar automáticamente más de una vez cada diez minutos.
La frecuencia de repetición de la actividad no puede ser inferior a 10 minutos. Si la frecuencia de repetición está establecida en 0 (también el valor predeterminado), esta opción no se tiene en cuenta y el flujo de trabajo se ejecutará según la frecuencia de ejecución.

### Flujos de trabajo en pausa

Los flujos de trabajo que han estado en pausa o en estado de error durante más de 7 días se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros del flujo de trabajo.

### Transiciones

Se puede seguir ejecutando un flujo de trabajo que contenga transiciones sin terminar: generará un mensaje de advertencia y el flujo de trabajo se pausará una vez que alcance la transición, pero no generará un error. También puede iniciar un flujo de trabajo sin un diseño terminado y completarlo a medida que avanza.

Para obtener más información, consulte [Ejecución de flujos de trabajo](../../automating/using//executing-a-workflow.md).

### Zona horaria

Las propiedades del flujo de trabajo le permiten definir un huso horario específico que se utilizará de forma predeterminada en todas sus actividades. De forma predeterminada, la zona horaria del flujo de trabajo es la definida para el operador de campaña actual.


## Activity{#activity}

### Diseño de flujo de trabajo

Para asegurarse de que el flujo de trabajo termina correctamente, utilice un **[!UICONTROL End activity]**. Evite dejar la última transición de un flujo de trabajo por su cuenta.

Para acceder a la vista de detalles de las transiciones, marque la **[!UICONTROL Keep interim results]**opción en la sección Ejecución de las propiedades del flujo de trabajo.

>[!CAUTION]
>
>Esta opción consume mucho espacio en disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.

![](assets/keep_interim_best_practices.png)


### Actividades de etiquetado{#activity-labeling}

Al desarrollar el flujo de trabajo, se genera un nombre para cada actividad, como para todos los objetos de Adobe Campaign. Aunque la herramienta genera el nombre de una actividad y no se puede editar, se recomienda etiquetarla con un nombre explícito al configurarla.

### Duplicar actividades{#activity-duplicating}

Para duplicar actividades existentes, puede utilizar copiar y pegar. De este modo, se conservan los ajustes que se definieron originalmente. Para obtener más información, consulte [Duplicar actividades](../../automating/using/workflow-interface.md)de flujo de trabajo.

###  Actividad del programador{#acheduler-activity}

Cuando cree el flujo de trabajo, utilice solo uno **[!UICONTROL Scheduler activity]**por rama. Si la misma rama de un flujo de trabajo tiene varios planificadores (vinculados entre sí), el número de tareas que se van a ejecutar se multiplica exponencialmente, lo cual sobrecarga considerablemente la base de datos.

Puede obtener una vista previa de las diez ejecuciones siguientes de los flujos de trabajo haciendo clic en **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Para obtener más información, consulte la actividad [](../../automating/using/scheduler.md)Programador.

## Flujo de trabajo de llamadas con parámetros{#workflow-with-parameters}

Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [Definición de parámetros al llamar al flujo de trabajo](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Los tipos de parámetros también deben ser coherentes con los valores esperados.

Asegúrese de que todos los parámetros se han declarado en la **[!UICONTROL External signal activity]**. De lo contrario, se producirá un error al ejecutar la actividad.

Para obtener más información, consulte [Llamada a un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md)externos.

## Exportación de paquetes{#exporting-packages}

Para exportar paquetes, los recursos exportados no deben contener ID predeterminados. Por lo tanto, los ID de los recursos exportables deben cambiarse utilizando un nombre diferente de las plantillas proporcionadas como estándar por Adobe Campaign Standard.
Para obtener más información, consulte [Administración de paquetes](../../automating/using/managing-packages.md).

## Exportación de listas{#exporting-lists}

La opción de lista de exportación permite exportar un máximo de 100.000 líneas de forma predeterminada y definidas por la opción **** Nms_ExportListLimit. Esta opción la puede administrar el administrador funcional, en **[!UICONTROL Administration]**>**[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
Para obtener más información, consulte[Exportación de listas](../../automating/using/exporting-lists.md).

## Resolución de problemas{#workflow-troubleshooting}

Adobe Campaign ofrece varios registros para comprender mejor los problemas del flujo de trabajo.

### Uso de registros de flujo de trabajo{#using-workflow-logs}

Puede acceder a los registros de flujo de trabajo para supervisar la ejecución de sus actividades. Indice las operaciones realizadas y los errores de ejecución por orden cronológico. La ficha Registros consta del historial de la ejecución de todas o algunas de las actividades seleccionadas.
La ficha Tareas detalla la secuencia de ejecución de las actividades. Para obtener más información sobre una actividad, haga clic en una tarea.
Para obtener más información, consulte [Supervisión de la ejecución](../../automating/using/executing-a-workflow.md#monitoring)del flujo de trabajo.

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

Las consultas SQL se pueden analizar en la ficha Registro.

1. En el espacio de trabajo del flujo de trabajo, haga clic en **[!UICONTROL Edit properties]**.
1. En **[!UICONTROL General]**>**[!UICONTROL Execution]**, marque las opciones **[!UICONTROL Save SQL queries in the log]**y**[!UICONTROL Execute in the engine]** y haga clic en **[!UICONTROL Confirm]**.

**Para ver las consultas SQL en el Registro:**
1. Haga clic **[!UICONTROL Log and Tasks]**.
1. En la **[!UICONTROL Logs]**ficha, abra el**[!UICONTROL Search]** panel.
1. Marque **[!UICONTROL Display SQL logs only]**.

La consulta se muestra en la columna **[!UICONTROL Message]**de los registros.

### Uso de registros de entrega{#using-delivery-logs}

Los registros de envío permiten supervisar el éxito de los envíos. Los registros de exclusión devuelven mensajes excluidos durante la preparación del envío. El envío de registros proporciona el estado de la entrega para cada perfil.
Para obtener más información, consulte [Explicación de los errores](../../sending/using/understanding-delivery-failures.md)de entrega.

### Uso de las alertas de entrega{#delivery-alerting}

La función de alerta de envío es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.
Para obtener más información, consulte [Envío de alertas](../../sending/using/receiving-alerts-when-failures-happen.md).

**Temas relacionados:**

* [Administración de errores](../../automating/using/executing-a-workflow.md#error-management)

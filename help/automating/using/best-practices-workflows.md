---
title: Prácticas recomendadas de Flujos de trabajo
description: Conozca las prácticas recomendadas para aplicar a sus flujos de trabajo.
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
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 8%

---


# Prácticas recomendadas del flujo de trabajo{#workflow-best-practices}

Con Adobe Campaign, puede configurar todos los tipos de flujo de trabajo para realizar una gran variedad de tareas. Sin embargo, cuando diseñe y ejecute sus flujos de trabajo, debe ser muy prudente, ya que una implementación incorrecta puede provocar errores de rendimiento, errores y problemas de plataforma. A continuación encontrará una lista de prácticas recomendadas y sugerencias para la resolución de problemas.

>[!NOTE]
>
>El diseño y la ejecución del flujo de trabajo deben ser realizados por un usuario avanzado de Adobe Campaign.

## Asignación de nombres{#naming}

Para facilitar la solución de problemas del flujo de trabajo, Adobe recomienda nombrar y etiquetar sus flujos de trabajo explícitamente. Rellene el campo de descripción del flujo de trabajo para resumir el proceso que se va a realizar de modo que el operador pueda comprenderlo fácilmente.
Si el flujo de trabajo forma parte de un proceso que involucra varios flujos de trabajo, puede utilizar números al introducir una etiqueta para ordenarlos con claridad.

Por ejemplo:

* 001: Importación: Importar destinatarios
* 002: Importación: Importar ventas
* 003: Importación: Importar detalles de ventas
* 010: Exportación: Exportar “logs” de envío
* 011: Exportación: Exportar “logs” de seguimiento

## Duplicación de flujos de trabajo{#duplicating-workflows}

Puede duplicado de flujos de trabajo. En la página **[!UICONTROL Marketing Activities]**, pase el ratón sobre el flujo de trabajo y haga clic en **[!UICONTROL Duplicate element]**. Una vez duplicados, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo. Se puede editar la copia del flujo de trabajo.

![](assets/duplicating_workflow.png)

## Ejecución{#execution}

### Número de flujos de trabajo

De forma predeterminada, se recomienda no ejecutar más de 20 ejecuciones de flujos de trabajo activos simultáneamente. Después de alcanzar ese límite, los flujos de trabajo se colocarán en la cola para no afectar a las actuaciones. Del mismo modo, Adobe recomienda que extienda la ejecución del flujo de trabajo con el paso del tiempo.
En contextos específicos, es posible que necesite ejecutar más de 20 flujos de trabajo. No se aplica a los flujos de trabajo que esperan una ejecución programada.  Si es así, debe consultar los casos de uso con un experto en Campaña y ponerse en contacto con el Servicio de atención al cliente de Adobe para aumentar el límite.

### Frecuencia

Un flujo de trabajo no se puede ejecutar automáticamente más de una vez cada diez minutos.
La frecuencia de repetición de la actividad no puede ser inferior a 10 minutos. Si la frecuencia de repetición está establecida en 0 (también el valor predeterminado), esta opción no se tiene en cuenta y el flujo de trabajo se ejecutará según la frecuencia de ejecución.

### flujos de trabajo en pausa

Los Flujos de trabajo que han estado en pausa o en estado de error durante más de 7 días se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros del flujo de trabajo.

### Transiciones

Se puede seguir ejecutando un flujo de trabajo que contenga transiciones sin terminar: generará un mensaje de advertencia y el flujo de trabajo se pausará una vez que llegue a la transición pero no generará un error. También puede realizar el inicio de un flujo de trabajo sin un diseño terminado y completarlo a medida que avanza.

Para obtener más información, consulte [Ejecución de flujos de trabajo](../../automating/using/about-workflow-execution.md).

### Zona horaria

Las propiedades del flujo de trabajo le permiten definir un huso horario específico que se utilizará de forma predeterminada en todas sus actividades. De forma predeterminada, el huso horario del flujo de trabajo es el definido para el operador de Campaña actual.


## Activity{#activity}

### Diseño de flujo de trabajo

Para asegurarse de que el flujo de trabajo termina correctamente, utilice un **[!UICONTROL End activity]**. Evite dejar la última transición de un flujo de trabajo por su cuenta.

Para acceder a la vista de detalles de las transiciones, marque la **[!UICONTROL Keep interim results]** opción en la sección Ejecución de las propiedades del flujo de trabajo.

>[!CAUTION]
>
>Esta opción consume mucho espacio en disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.

![](assets/keep_interim_best_practices.png)


### Etiquetado de actividades{#activity-labeling}

Durante el desarrollo del flujo de trabajo, se genera un nombre para cada actividad, como para todos los objetos de Adobe Campaign. Aunque la herramienta genera el nombre de una actividad y no se puede editar, se recomienda etiquetarla con un nombre explícito al configurarla.

### Duplicar actividades{#activity-duplicating}

Para duplicado de actividades existentes, puede utilizar copiar y pegar. De este modo, se conservan los ajustes que se definieron originalmente. Para obtener más información, consulte [Duplicar actividades](../../automating/using/workflow-interface.md)de flujo de trabajo.

### actividad Planificador{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. Si la misma rama de un flujo de trabajo tiene varios planificadores (vinculados entre sí), el número de tareas que se van a ejecutar se multiplica exponencialmente, lo cual sobrecarga considerablemente la base de datos.

Puede previsualización de las siguientes diez ejecuciones de sus flujos de trabajo haciendo clic en **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Para obtener más información, consulte actividad [de](../../automating/using/scheduler.md)Planificador.

## Flujo de trabajo de llamadas con parámetros{#workflow-with-parameters}

Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [Definición de parámetros al llamar al flujo de trabajo](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Los tipos de parámetros también deben ser coherentes con los valores esperados.

Asegúrese de que todos los parámetros se han declarado en la **[!UICONTROL External signal activity]**. De lo contrario, se producirá un error al ejecutar la actividad.

Para obtener más información, consulte [Llamada a un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md)externos.

## Exportación de paquetes{#exporting-packages}

Para exportar paquetes, los recursos exportados no deben contener ID predeterminados. Por lo tanto, las ID de los recursos exportables deben cambiarse utilizando un nombre diferente de las plantillas proporcionadas como estándar por Adobe Campaign Standard.
Para obtener más información, consulte [Administración de paquetes](../../automating/using/managing-packages.md).

## Exportación de listas{#exporting-lists}

La opción de lista de exportación permite exportar un máximo de 100.000 líneas de forma predeterminada y definida por la opción **** Nms_ExportListLimit. Esta opción la puede administrar el administrador funcional, en **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
Para obtener más información, consulte [Exportación de listas](../../automating/using/exporting-lists.md).

## Resolución de problemas{#workflow-troubleshooting}

Adobe Campaign oferta varios registros para comprender mejor los problemas del flujo de trabajo.

### Uso de registros de flujo de trabajo{#using-workflow-logs}

Puede acceder a los registros de flujo de trabajo para supervisar la ejecución de sus actividades. Indice las operaciones realizadas y los errores de ejecución por orden cronológico. La ficha Registros consta del historial de ejecución de todas o algunas actividades seleccionadas.
La ficha Tareas detalla la secuencia de ejecución de las actividades. Para obtener más información sobre una actividad, haga clic en una tarea.
Para obtener más información, consulte [Supervisión de la ejecución](../../automating/using/monitoring-workflow-execution.md)del flujo de trabajo.

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

Puede analizar consultas SQL en la ficha Registro.

1. En el espacio de trabajo del flujo de trabajo, haga clic en **[!UICONTROL Edit properties]**.
1. En **[!UICONTROL General]** > **[!UICONTROL Execution]**, marque las opciones **[!UICONTROL Save SQL queries in the log]** y **[!UICONTROL Execute in the engine]** y haga clic en **[!UICONTROL Confirm]**.

**Para ver consultas SQL en el registro:**
1. Haga clic **[!UICONTROL Log and Tasks]**.
1. En la **[!UICONTROL Logs]** ficha, abra el **[!UICONTROL Search]** panel.
1. Marque **[!UICONTROL Display SQL logs only]**.

La consulta se muestra en la **[!UICONTROL Message]** columna de los registros.

### Uso de registros de envío{#using-delivery-logs}

Los Registros de envío permiten supervisar el éxito de sus envíos. Los registros de exclusión devuelven mensajes excluidos durante la preparación del envío. El envío de registros proporciona el estado del envío para cada perfil.
Para obtener más información, consulte [Explicación de los errores](../../sending/using/understanding-delivery-failures.md)de envío.

### Uso de las alertas de envío{#delivery-alerting}

La función de alerta de Envío es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.
Para obtener más información, consulte Alertas de [Envío](../../sending/using/receiving-alerts-when-failures-happen.md).

**Temas relacionados:**

* [Administración de errores](../../automating/using/monitoring-workflow-execution.md)

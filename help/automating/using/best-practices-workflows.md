---
title: Prácticas recomendadas de flujos de trabajo
seo-title: Prácticas recomendadas de flujos de trabajo
description: Prácticas recomendadas de flujos de trabajo
seo-description: Conozca cómo se aplican a sus flujos de trabajo.
page-status-flag: no activado nunca
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: flujo de trabajo general operation
context-tags: flujo de trabajo, información general; flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e02ca92032c298fe1b5dbc7094de201d0a106be5

---


# Workflow best practices{#workflow-best-practices}

Con Adobe Campaign, puede configurar todos los tipos de flujo de trabajo para realizar un amplio ámbito de tareas. Sin embargo, al diseñar y ejecutar sus flujos de trabajo, debe ser muy cauteloso como una implementación errónea que puede producir errores, errores y resultados incorrectos. Puede encontrar una lista de prácticas recomendadas y sugerencias para la solución de problemas.

>[!NOTE]
>
>El diseño y la ejecución de flujo de trabajo debe realizarlo un usuario avanzado de Adobe Campaign.

## Naming{#naming}

Para facilitar la resolución de problemas de flujo de trabajo, Adobe recomienda asignar un nombre a los flujos de trabajo y etiquetarlos explícitamente. Rellene el campo de descripción del flujo de trabajo para resumir el proceso que se realizará para que el operador pueda comprenderlo fácilmente.
Si el flujo de trabajo forma parte de un proceso relacionado con varios flujos de trabajo, puede utilizar números al introducir una etiqueta para ordenarlos claramente.

Por ejemplo:

* 001 - Importar - Importar destinatarios
* 002 - Importar - Importar ventas
* 003 - Importar - Importar detalles de ventas
* 010 - Exportar - Registros de entrega de exportación
* 011 - Exportar - Registros de seguimiento de exportación

## Duplicating workflows{#duplicating-workflows}

Puede duplicar flujos de trabajo. In the **[!UICONTROL Marketing Activities]**, hover over the workflow and click **[!UICONTROL Duplicate element]**. Una vez duplicados, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo. Se puede editar la copia del flujo de trabajo.

![](assets/duplicating_workflow.png)

## Execution{#execution}

### Número de flujos de trabajo

De forma predeterminada, se recomienda no ejecutar simultáneamente más de 20 ejecuciones de flujos de trabajo activos. Después de alcanzar ese límite, los flujos de trabajo se ponen en cola para no afectar al rendimiento. Del mismo modo, Adobe recomienda que distribuya su flujo de trabajo a lo largo del tiempo.
En contextos específicos, es posible que tenga que ejecutar más de 20 flujos de trabajo. No se aplica a los flujos de trabajo que esperan una ejecución programada. Si es así, debe comprobar los casos de uso con un experto de campaña y ponerse en contacto con el Servicio de atención al cliente de Adobe para aumentar el límite.

### Frecuencia

Un flujo de trabajo no se puede ejecutar automáticamente con más frecuencia que una vez cada diez minutos.
La frecuencia de repetición de la actividad no puede ser inferior a 10 minutos. Si la frecuencia de repetición se establece en 0 (también el valor predeterminado), esta opción no se tiene en cuenta y el flujo de trabajo se ejecutará según la frecuencia de ejecución.

### Flujos de trabajo en pausa

Los flujos de trabajo que han estado en pausa o en errores durante más de 7 días se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros de flujo de trabajo.

### Transiciones

Se puede ejecutar un flujo de trabajo que contenga transiciones inagotadas: generará un mensaje de advertencia y el flujo de trabajo se pausará una vez alcanzado la transición pero no generará un error. También puede iniciar un flujo de trabajo sin un diseño terminado y completarlo a medida que avanza.

For more information, refer to [Executing workflows](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### Diseño de flujo de trabajo

To ensure that the workflow ends properly, use an **[!UICONTROL End activity]**. Evite dejar la última transición de un flujo de trabajo por sí mismo.

To access the detail view of the transitions, check the **[!UICONTROL Keep interim results]** option in the Execution section of the workflow properties.

>[!CAUTION]
>
>Esta opción consume mucho espacio en disco y está diseñado para ayudarle a crear un flujo de trabajo y garantizar la correcta configuración y comportamiento. Déjelo desactivado en las instancias de producción.

![](assets/keep_interim_best_practices.png)


### Labelling activities{#activity-labeling}

Al desarrollar el flujo de trabajo, se genera un nombre para cada actividad, como para todos los objetos de Adobe Campaign. Aunque la herramienta genera el nombre de una actividad y no se puede editar, recomendamos etiquetarla con un nombre explícito al configurarla.

### Duplicating activities{#activity-duplicating}

Para duplicar actividades existentes, puede utilizar Copiar-pegar. De esta forma, mantiene la configuración definida originalmente. For more information, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md).

### Scheduler activity{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. Si la misma ramificación de un flujo de trabajo tiene varios programadores (vinculados entre sí), el número de tareas que se ejecutará se multiplicará exponencialmente, lo que sobrecargaría considerablemente la base de datos.

You can preview the next ten executions of your workflows by clicking **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

For more information, refer to [Scheduler activity](../../automating/using/scheduler.md).

## Calling workflow with parameters{#workflow-with-parameters}

Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Los tipos de parámetros también deben ser coherentes con los valores esperados.

Make sure that all the parameters have been declared in the **[!UICONTROL External signal activity]**. De lo contrario, se producirá un error al ejecutar la actividad.

For more information, see [Calling a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exporting packages{#exporting-packages}

Para exportar paquetes, los recursos exportados no deben contener ID predeterminados. Por lo tanto, los ID de recursos exportables deben cambiarse con un nombre diferente de las plantillas proporcionadas como estándar por Adobe Campaign Standard.
For more information, see [Managing packages](../../automating/using/managing-packages.md).

## Exporting lists{#exporting-lists}

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit option**. This option can be managed by the functional administrator, under **Administration** &gt; **Application settings** &gt; **Options**.
For more information, see [Exporting lists](../../automating/using/exporting-lists.md).

## Troubleshooting{#workflow-troubleshooting}

Adobe Campaign ofrece varios registros para comprender mejor los problemas de flujo de trabajo.

### Using workflow logs{#using-workflow-logs}

Puede acceder a los registros de flujo de trabajo para controlar la ejecución de las actividades. Indexa las operaciones realizadas y los errores de ejecución por orden cronológico.
For more information, refer to [Monitoring workflow execution](../../automating/using/executing-a-workflow.md#monitoring).

### Using delivery logs{#using-delivery-logs}

Los registros de entrega permiten supervisar el éxito de los envíos. Los registros de exclusión devuelven mensajes excluidos durante la preparación del envío. El envío de registros proporciona el estado de la entrega para cada perfil.
For more information, refer to [Understanding delivery failures](../../sending/using/understanding-delivery-failures.md).

### Using delivery alerting{#delivery-alerting}

La función de alerta de envío es un sistema de administración de alertas que permite que un grupo de usuarios reciba notificaciones automáticamente que contengan información sobre la ejecución de sus envíos.
For more information, refer to [Delivery alerting](../../sending/using/receiving-alerts-when-failures-happen.md).

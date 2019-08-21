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
source-git-commit: fd44c6e6d0f6a4ca75b01c99fbae6d9072dd7736

---


# Prácticas recomendadas del flujo de trabajo{#workflow-best-practices}

Con Adobe Campaign, puede configurar todos los tipos de flujo de trabajo para realizar un amplio ámbito de tareas. Sin embargo, al diseñar y ejecutar sus flujos de trabajo, debe ser muy cauteloso como una implementación errónea que puede producir errores, errores y resultados incorrectos. Puede encontrar una lista de prácticas recomendadas y sugerencias para la solución de problemas.

>[!NOTE]
>
>El diseño y la ejecución de flujo de trabajo debe realizarlo un usuario avanzado de Adobe Campaign.

## Nombre{#naming}

Para facilitar la resolución de problemas de flujo de trabajo, Adobe recomienda asignar un nombre a los flujos de trabajo y etiquetarlos explícitamente. Rellene el campo de descripción del flujo de trabajo para resumir el proceso que se realizará para que el operador pueda comprenderlo fácilmente.
Si el flujo de trabajo forma parte de un proceso relacionado con varios flujos de trabajo, puede utilizar números al introducir una etiqueta para ordenarlos claramente.

Por ejemplo:

* 001 - Importar - Importar destinatarios
* 002 - Importar - Importar ventas
* 003 - Importar - Importar detalles de ventas
* 010 - Exportar - Registros de entrega de exportación
* 011 - Exportar - Registros de seguimiento de exportación

## Duplicación de flujos de trabajo{#duplicating-workflows}

Puede duplicar flujos de trabajo. En, **[!UICONTROL Marketing Activities]** pase el ratón sobre el flujo de trabajo y haga clic **[!UICONTROL Duplicate element]** en. Una vez duplicados, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo. Se puede editar la copia del flujo de trabajo.

![](assets/duplicating_workflow.png)

## Ejecución{#execution}

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

Para obtener más información, consulte [Ejecución de flujos de trabajo](../../automating/using//executing-a-workflow.md).

## Actividad{#activity}

### Diseño de flujo de trabajo

Para asegurarse de que el flujo de trabajo termina correctamente, utilice **[!UICONTROL End activity]** un. Evite dejar la última transición de un flujo de trabajo por sí mismo.

Para acceder a la vista de detalles de las transiciones, marque **[!UICONTROL Keep interim results]** la opción en la sección Ejecución de las propiedades del flujo de trabajo.

>[!CAUTION]
>
>Esta opción consume mucho espacio en disco y está diseñado para ayudarle a crear un flujo de trabajo y garantizar la correcta configuración y comportamiento. Déjelo desactivado en las instancias de producción.

![](assets/keep_interim_best_practices.png)


### Actividades de Labelling{#activity-labeling}

Al desarrollar el flujo de trabajo, se genera un nombre para cada actividad, como para todos los objetos de Adobe Campaign. Aunque la herramienta genera el nombre de una actividad y no se puede editar, recomendamos etiquetarla con un nombre explícito al configurarla.

### Duplicación de actividades{#activity-duplicating}

Para duplicar actividades existentes, puede utilizar Copiar-pegar. De esta forma, mantiene la configuración definida originalmente. Para obtener más información, consulte [Duplicación de actividades de flujo de trabajo](../../automating/using/workflow-interface.md).

### Actividad del programador{#acheduler-activity}

Al crear el flujo de trabajo, utilice sólo uno **[!UICONTROL Scheduler activity]** por rama. Si la misma ramificación de un flujo de trabajo tiene varios programadores (vinculados entre sí), el número de tareas que se ejecutará se multiplicará exponencialmente, lo que sobrecargaría considerablemente la base de datos.

Puede obtener una vista preliminar de las diez ejecuciones siguientes de sus flujos de trabajo haciendo clic **[!UICONTROL Preview next executions]** en.

![](assets/preview_scheduler.png)

Para obtener más información, consulte Actividad [Programador](../../automating/using/scheduler.md).

## Llamada de flujo de trabajo con parámetros{#workflow-with-parameters}

Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [Definición de los parámetros al llamar al flujo de trabajo](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Los tipos de parámetros también deben ser coherentes con los valores esperados.

Asegúrese de haber declarado todos los parámetros en **[!UICONTROL External signal activity]** la. De lo contrario, se producirá un error al ejecutar la actividad.

Para obtener más información, consulte [Llamada a un flujo de trabajo con parámetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exportación de paquetes{#exporting-packages}

Para exportar paquetes, los recursos exportados no deben contener ID predeterminados. Por lo tanto, los ID de recursos exportables deben cambiarse con un nombre diferente de las plantillas proporcionadas como estándar por Adobe Campaign Standard.
Para obtener más información, consulte [Administración de paquetes](../../automating/using/managing-packages.md).

## Exportación de listas{#exporting-lists}

La opción de lista de exportación permite exportar un máximo de 100 000 líneas de forma predeterminada y definir la opción **Nms_ exportlistlimit**. Esta opción puede ser administrada por el administrador funcional, en **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
Para obtener más información, consulte [Exportación de listas](../../automating/using/exporting-lists.md).

## Solución de problemas{#workflow-troubleshooting}

Adobe Campaign ofrece varios registros para comprender mejor los problemas de flujo de trabajo.

### Uso de registros de flujo de trabajo{#using-workflow-logs}

Puede acceder a los registros de flujo de trabajo para controlar la ejecución de las actividades. Indexa las operaciones realizadas y los errores de ejecución por orden cronológico. La ficha Registros consta del historial de ejecución de todas o algunas de las actividades seleccionadas.
La ficha Tareas detalla la secuencia de ejecución de las actividades. Para obtener más información sobre una actividad, haga clic en una tarea.
Para obtener más información, consulte [Supervisión del flujo de trabajo de monitoreo](../../automating/using/executing-a-workflow.md#monitoring).

#### Solución de problemas de las actividades de administración de datos{#troubleshooting-data-management-activities}

Puede analizar las consultas SQL en la ficha Registro.

1. En el espacio de trabajo del flujo de trabajo, haga clic **[!UICONTROL Edit properties]** en.
1. En **[!UICONTROL General]** &gt; **[!UICONTROL Execution]**, compruebe las opciones **[!UICONTROL Save SQL queries in the log]** y **[!UICONTROL Execute in the engine]** las opciones y haga clic **[!UICONTROL Confirm]** en.

**Para ver consultas SQL en Registro:**
1. Click **[!UICONTROL Log and Tasks]**.
1. En la **[!UICONTROL Logs]** ficha, abra **[!UICONTROL Search]** el panel.
1. Compruebe.**[!UICONTROL Display SQL logs only]**

La consulta se muestra en **[!UICONTROL Message]** la columna de los registros.

### Uso de registros de entrega{#using-delivery-logs}

Los registros de entrega permiten supervisar el éxito de los envíos. Los registros de exclusión devuelven mensajes excluidos durante la preparación del envío. El envío de registros proporciona el estado de la entrega para cada perfil.
Para obtener más información, consulte [Explicación de los fallos de entrega](../../sending/using/understanding-delivery-failures.md).

### Uso de las alertas de envío{#delivery-alerting}

La función de alerta de envío es un sistema de administración de alertas que permite que un grupo de usuarios reciba notificaciones automáticamente que contengan información sobre la ejecución de sus envíos.
Para obtener más información, consulte Alerta [de envío](../../sending/using/receiving-alerts-when-failures-happen.md).

**Temas relacionados:**

* [Gestión de errores](../../automating/using/executing-a-workflow.md#error-management)

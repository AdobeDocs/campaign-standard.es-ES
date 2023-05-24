---
title: Administración de propiedades de actividades
description: Obtenga información sobre cómo administrar las propiedades de las actividades de flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Administración de propiedades de actividades {#activity-properties}

## Propiedades globales de una actividad {#global-properties-of-an-activity}

Cada actividad tiene un **[!UICONTROL General]** , que permite modificar los parámetros generales específicos de la actividad.

![](assets/activity-properties.png)

El **[!UICONTROL Properties]** permite modificar los parámetros globales de la actividad, especialmente la etiqueta y el ID. La configuración de esta pestaña es opcional.

![](assets/activity-properties2.png)

## Administración de las transiciones salientes de una actividad {#managing-an-activity-s-outbound-transitions}

De forma predeterminada, determinadas actividades no tienen una transición saliente. Puede añadir una desde el **[!UICONTROL Transitions]** pestaña o desde el **[!UICONTROL Properties]** para aplicar otros procesos a la población en el mismo flujo de trabajo.

Según las actividades, puede añadir varios tipos de transiciones salientes:

* **Transición estándar**: población calculada por la actividad
* **Transición sin población**: este tipo de transición saliente se puede añadir para continuar el flujo de trabajo y no contiene ninguna población para no consumir espacio innecesario en el sistema.
* **Rechazos**: población rechazada. Por ejemplo, si los datos de entrada de la actividad no se han podido procesar porque son incorrectos o están incompletos.
* **Complemento**: población restante después de ejecutar la actividad. Por ejemplo, si una actividad de segmentación está configurada para guardar solo un porcentaje de la población entrante.

Si procede, especifique un **[!UICONTROL Segment code]** para la transición saliente de la actividad. Este código de segmento le permite identificar de dónde provienen los subconjuntos de la población de destinatarios y, posteriormente, puede servir para personalizar mensajes.

## Opciones de ejecución de actividades {#activity-execution-options}

En la pantalla de propiedades de la actividad, hay un **[!UICONTROL Advanced options]** que permite definir el modo de ejecución y el comportamiento de la actividad en caso de errores.

Para acceder a estas opciones, seleccione una actividad en un flujo de trabajo y ábrala con el ![](assets/edit_darkgrey-24px.png) de la barra de acciones.

![](assets/wkf_advanced_parameters.png)

El **[!UICONTROL Execution]** permite definir la acción que se lleva a cabo cuando se inicia la tarea. Hay tres opciones para esto:

* **Normal**: la actividad se ejecuta normalmente.
* **Habilitar pero no ejecutar**: la actividad está en pausa y, como consecuencia, también lo están los procesos futuros que siguen. Esto puede resultar útil si desea estar presente cuando se inicia la tarea.
* **No habilitar**: la actividad no se ejecuta y, como consecuencia, tampoco lo son todas las actividades siguientes (en la misma rama).

El **[!UICONTROL In case of error]** Este campo permite especificar la acción que se debe llevar a cabo si la actividad experimenta un error. Hay dos opciones disponibles para esto:

* **Suspender el proceso**: el flujo de trabajo se suspende automáticamente. El estado del flujo de trabajo es **Erróneo** y el color asociado se vuelve rojo. Una vez resuelto el problema, reinicie el flujo de trabajo.
* **Ignorar**: la actividad no se ejecuta y, como resultado, ninguna de las actividades que la siguen (en la misma rama). Esto puede resultar útil para tareas recurrentes. Si la rama tiene un planificador en una posición anterior, el déclencheur debería ser la siguiente fecha de ejecución.

El **[!UICONTROL Behavior]** permite definir el procedimiento que se debe seguir si se utilizan tareas asincrónicas. Hay dos opciones disponibles para esto:

* **Varias tareas autorizadas**: se pueden ejecutar varias tareas al mismo tiempo, incluso si no ha finalizado la primera.
* **La tarea actual tiene prioridad**: una vez que una tarea está en curso, esto tiene prioridad. Mientras una tarea esté en curso, no se ejecutará ninguna otra tarea.

El **[!UICONTROL Max. execution duration]** permite especificar una duración como &quot;30 segundos&quot; o &quot;1h&quot;. Si la actividad no termina después de que haya transcurrido la duración especificada, se activa una alerta. Esto no afecta al funcionamiento del flujo de trabajo.

El **[!UICONTROL Affinity]** Este campo permite forzar la ejecución de un flujo de trabajo o una actividad de flujo de trabajo en un equipo concreto. Para ello, debe especificar una o varias afinidades para el flujo de trabajo o actividad en cuestión.

El **[!UICONTROL Time zone]** Este campo permite seleccionar la zona horaria de la actividad. Adobe Campaign le permite administrar las diferencias horarias entre varios países en la misma instancia. La configuración aplicada se configura cuando se crea la instancia.

>[!NOTE]
>
>De forma predeterminada, si no se selecciona ninguna zona horaria, la actividad utilizará la definida en las propiedades del flujo de trabajo.

El **Comentario** field es un campo libre que le permite agregar una nota.

---
title: Comandos de ejecución
description: Aprenda a utilizar los comandos de ejecución de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---

# Comandos de ejecución {#execution-commands}

Los iconos de la barra de acciones permiten iniciar, rastrear y modificar la ejecución de un flujo de trabajo. Consulte [Barra de acciones](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Start**

La variable ![](assets/play_darkgrey-24px.png) inicia la ejecución de un flujo de trabajo, que a continuación inicia el **En curso** (azul). Si el flujo de trabajo estaba en pausa, se reanuda, de lo contrario se inicia y las actividades iniciales se activan.

>[!NOTE]
>
>El inicio es un proceso asincrónico: la solicitud se guarda y el motor de ejecución del flujo de trabajo la procesa lo antes posible.

**Pause**

La variable ![](assets/pause_darkgrey-24px.png) pone en pausa la ejecución. El flujo de trabajo utiliza la variable **Advertencia** (amarillo). No se activará ninguna actividad nueva hasta que se reanude, pero las operaciones en curso no se suspenderán.

**Stop**

La variable ![](assets/stop_darkgrey-24px.png) detiene un flujo de trabajo que se está ejecutando y que luego se ejecuta en **Finalizado** (verde). Las operaciones en curso se interrumpen si es posible y las importaciones o consultas SQL en curso se cancelan inmediatamente. No se puede reanudar desde el flujo de trabajo desde el mismo lugar en que se detuvo.

**Restart**

La variable ![](assets/pauseplay_darkgrey-24px.png) implica detener y, a continuación, reiniciar un flujo de trabajo. En la mayoría de los casos, esto le permite reiniciar más rápido. También puede resultar útil automatizar el reinicio una vez que la detención tarde una cierta cantidad de tiempo, ya que la variable ![](assets/play_darkgrey-24px.png) sólo está disponible cuando la parada es efectiva.

Cuando se seleccionan una o varias actividades de un flujo de trabajo, hay otras acciones que puede realizar, como:

**Ejecución inmediata**

La variable ![](assets/pending_darkgrey-24px.png) inicia las actividades pendientes seleccionadas lo antes posible.

**Ejecución normal**

La variable ![](assets/check_darkgrey-24px.png) reactiva cualquier actividad pausada o desactivada.

**Ejecución suspendida**

La variable ![](assets/check_pause_darkgrey-24px.png) pone en pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todas las que la siguen (en la misma rama), no se ejecutan.

**Sin ejecución**

La variable ![](assets/checkdisable.png) desactiva las actividades seleccionadas.

>[!NOTE]
>
>Las acciones rápidas permiten acceder a diferentes acciones relacionadas con una actividad en particular y aparecen cuando se selecciona una actividad.

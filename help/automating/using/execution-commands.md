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
ht-degree: 5%

---

# Comandos de ejecución {#execution-commands}

Los iconos de la barra de acciones permiten iniciar, rastrear y modificar la ejecución de un flujo de trabajo. Consulte [Barra de acciones](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Start**

El ![](assets/play_darkgrey-24px.png) comienza a ejecutar un flujo de trabajo, que luego asume la función **En curso** Estado (azul). Si el flujo de trabajo estaba en pausa, se reanuda, pero de lo contrario se inicia y las actividades iniciales se activan.

>[!NOTE]
>
>El inicio es un proceso asíncrono: la solicitud se guarda y el motor de ejecución del flujo de trabajo la procesa lo antes posible.

**Pause**

El ![](assets/pause_darkgrey-24px.png) pausa la ejecución. El flujo de trabajo asume la función **Advertencia** Estado (amarillo). No se activará ninguna actividad nueva hasta que se reanude, pero las operaciones en curso no se suspenden.

**Stop**

El ![](assets/stop_darkgrey-24px.png) detiene un flujo de trabajo que se está ejecutando y que, a continuación, asume la función **Finalizado** Estado (verde). Las operaciones en curso se interrumpen si es posible y las consultas SQL o de importación en curso se cancelan inmediatamente. No puede reanudar desde el flujo de trabajo desde el mismo lugar en el que se detuvo.

**Restart**

El ![](assets/pauseplay_darkgrey-24px.png) Este botón implica detener y reiniciar un flujo de trabajo. En la mayoría de los casos, esto le permite reiniciarse más rápido. También puede resultar útil automatizar el reinicio una vez que la detención lleva una determinada cantidad de tiempo, ya que la variable ![](assets/play_darkgrey-24px.png) solo está disponible cuando la parada es efectiva.

Cuando se seleccionan una o varias actividades en un flujo de trabajo, hay otras acciones que puede realizar, como las siguientes:

**Ejecución inmediata**

El ![](assets/pending_darkgrey-24px.png) inicia cualquier actividad pendiente seleccionada lo antes posible.

**Ejecución normal**

El ![](assets/check_darkgrey-24px.png) reactiva cualquier actividad pausada o desactivada.

**Ejecución suspendida**

El ![](assets/check_pause_darkgrey-24px.png) button pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todas las que la siguen (en la misma rama), no se ejecutan.

**Sin ejecución**

El ![](assets/checkdisable.png) El botón desactiva las actividades seleccionadas.

>[!NOTE]
>
>Las acciones rápidas permiten acceder a diferentes acciones relacionadas con una actividad concreta y aparecen cuando se selecciona una actividad.

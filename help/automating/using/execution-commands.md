---
solution: Campaign Standard
product: campaign
title: Comandos de ejecución
description: Aprenda a utilizar comandos de ejecución de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Comandos de ejecución {#execution-commands}

Los iconos de la barra de acciones le permiten realizar el inicio, el seguimiento y la modificación de la ejecución de un flujo de trabajo. Consulte Barra [de acciones](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Start**

El ![](assets/play_darkgrey-24px.png) botón inicio la ejecución de un flujo de trabajo y, a continuación, adopta el estado **En curso** (azul). Si el flujo de trabajo se ha pausado, se reanuda; de lo contrario, se inicia y se activan las actividades iniciales.

>[!NOTE]
>
>El inicio es un proceso asincrónico: la solicitud se guarda y el motor de ejecución del flujo de trabajo la procesará lo antes posible.

**Pause**

El ![](assets/pause_darkgrey-24px.png) botón pone en pausa la ejecución. El flujo de trabajo adopta el estado **Advertencia** (amarillo). No se activarán nuevas actividades hasta que se reanude, pero las operaciones en curso no se suspenden.

**Stop**

El ![](assets/stop_darkgrey-24px.png) botón detiene un flujo de trabajo que se está ejecutando y que luego pasará al estado **Finalizado** (verde). Las operaciones en curso se interrumpen si es posible y las importaciones o consultas SQL en curso se cancelan inmediatamente. No se puede reanudar desde el flujo de trabajo desde el mismo lugar en que se detuvo.

**Restart**

El ![](assets/pauseplay_darkgrey-24px.png) botón implica detener y, a continuación, reiniciar un flujo de trabajo. En la mayoría de los casos, esto le permite reiniciar más rápido. También puede resultar útil automatizar el reinicio una vez que la detención tarde una cierta cantidad de tiempo, ya que el ![](assets/play_darkgrey-24px.png) botón solo está disponible cuando la detención es efectiva.

Cuando se seleccionan una o varias actividades de un flujo de trabajo, se pueden realizar otras acciones, como:

**Ejecución inmediata**

El ![](assets/pending_darkgrey-24px.png) botón inicio cualquier actividad pendiente seleccionada lo antes posible.

**Ejecución normal**

El ![](assets/check_darkgrey-24px.png) botón reactiva cualquier actividad pausada o desactivada.

**Ejecución suspendida**

El ![](assets/check_pause_darkgrey-24px.png) botón pone en pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todas las que la siguen (en la misma rama), no se ejecutan.

**Sin ejecución**

El ![](assets/checkdisable.png) botón desactiva las actividades seleccionadas.

>[!NOTE]
>
>Las acciones rápidas le permiten acceder a diferentes acciones relacionadas con una actividad en particular y aparecen cuando se selecciona una actividad.

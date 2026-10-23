---
title: Comandos de ejecución
description: Aprenda a utilizar los comandos de ejecución de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
TQID: 'https://experienceleague.adobe.com/jDS-3Rz--h6N17JfbijrtOaj8jVDPDW9HiOoiLwPHSY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%
---
# Comandos de ejecución {#execution-commands}

Los iconos de la barra de acciones permiten iniciar, rastrear y modificar la ejecución de un flujo de trabajo. Ver [Barra de acciones](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Las acciones disponibles son las siguientes:

**Start**

El botón ![](assets/play_darkgrey-24px.png) comienza a ejecutar un flujo de trabajo, que luego adquiere el estado **En curso** (azul). Si el flujo de trabajo estaba en pausa, se reanuda, pero de lo contrario se inicia y las actividades iniciales se activan.

>[!NOTE]
>
>El inicio es un proceso asíncrono: la solicitud se guarda y el motor de ejecución del flujo de trabajo la procesa lo antes posible.

**Pause**

El botón ![](assets/pause_darkgrey-24px.png) pausa la ejecución. El flujo de trabajo adquiere el estado **Advertencia** (amarillo). No se activará ninguna actividad nueva hasta que se reanude, pero las operaciones en curso no se suspenden.

**Stop**

El botón ![](assets/stop_darkgrey-24px.png) detiene un flujo de trabajo que se está ejecutando y que luego pasará al estado **Finalizado** (verde). Las operaciones en curso se interrumpen si es posible y las consultas SQL o de importación en curso se cancelan inmediatamente. No puede reanudar desde el flujo de trabajo desde el mismo lugar en el que se detuvo.

**Restart**

El botón ![](assets/pauseplay_darkgrey-24px.png) implica detener y reiniciar un flujo de trabajo. En la mayoría de los casos, esto le permite reiniciarse más rápido. También puede resultar útil automatizar el reinicio una vez que la detención lleva una cierta cantidad de tiempo, ya que el botón ![](assets/play_darkgrey-24px.png) solo está disponible cuando la detención es efectiva.

Cuando se seleccionan una o varias actividades en un flujo de trabajo, hay otras acciones que puede realizar, como las siguientes:

**Ejecución inmediata**

El botón ![](assets/pending_darkgrey-24px.png) inicia cualquier actividad pendiente seleccionada lo antes posible.

**Ejecución normal**

El botón ![](assets/check_darkgrey-24px.png) reactiva cualquier actividad pausada o desactivada.

**Ejecución suspendida**

El botón ![](assets/check_pause_darkgrey-24px.png) pausa el flujo de trabajo en la actividad seleccionada: esta tarea, así como todas las que la siguen (en la misma rama), no se ejecutan.

**Sin ejecución**

El botón ![](assets/checkdisable.png) desactiva las actividades seleccionadas.

>[!NOTE]
>
>Las acciones rápidas permiten acceder a diferentes acciones relacionadas con una actividad concreta y aparecen cuando se selecciona una actividad.

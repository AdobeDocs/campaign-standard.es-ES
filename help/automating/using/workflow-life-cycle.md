---
solution: Campaign Standard
product: campaign
title: Ciclo de vida del flujo de trabajo
description: Más información sobre el ciclo de vida del flujo de trabajo
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# Ciclo de vida del flujo de trabajo {#life-cycle}

El ciclo de vida de un flujo de trabajo incluye tres pasos principales y cada paso está vinculado a un estado y un color:

* **Edición** (gris)

   Esta es la fase de diseño inicial de un flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow)). El servidor aún no gestiona el flujo de trabajo y se puede modificar sin ningún riesgo.

* **En curso** (azul)

   Una vez finalizada la fase de diseño inicial, el servidor puede iniciar y gestionar el flujo de trabajo.

* **Finalizado** (verde)

   Un flujo de trabajo finaliza cuando ya no hay ninguna tarea en curso o cuando un operador ha detenido explícitamente la instancia.

Una vez iniciado, un flujo de trabajo también puede tener otros dos estados:

* **Advertencia** (amarillo)

   El flujo de trabajo no pudo finalizar o se detuvo con los botones ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png) .

* **Erróneo** (rojo)

   Error al ejecutar un flujo de trabajo. El flujo de trabajo se detuvo y el usuario debe realizar una acción. Para obtener más información sobre este error, utilice el ![](assets/printpreview_darkgrey-24px.png) botón para acceder al registro del flujo de trabajo (consulte [Supervisión](../../automating/using/monitoring-workflow-execution.md)).

La lista de actividades de marketing permite mostrar todos los flujos de trabajo, así como sus estados. For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

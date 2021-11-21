---
title: Ciclo de vida del flujo de trabajo
description: Descubra más información sobre el ciclo de vida del flujo de trabajo
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Ciclo de vida del flujo de trabajo {#life-cycle}

El ciclo de vida de un flujo de trabajo incluye tres pasos principales y cada paso está vinculado a un estado y a un color:

* **Edición** (gris)

   Esta es la fase de diseño inicial de un flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow)). El flujo de trabajo aún no se gestiona mediante el servidor y se puede modificar sin ningún riesgo.

* **En curso** (azul)

   Una vez finalizada la fase de diseño inicial, el flujo de trabajo se puede iniciar y el servidor lo gestiona.

* **Finalizado** (verde)

   Un flujo de trabajo finaliza cuando ya no hay tareas en curso o cuando un operador ha detenido explícitamente la instancia.

Una vez iniciado, un flujo de trabajo también puede tener otros dos estados:

* **Advertencia** (amarillo)

   El flujo de trabajo no pudo finalizar o se pausó con la función ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png) botones.

* **Erróneo** (rojo)

   Error al ejecutar un flujo de trabajo. El flujo de trabajo se detuvo y el usuario debe realizar una acción. Para obtener más información sobre este error, utilice el ![](assets/printpreview_darkgrey-24px.png) para acceder al registro de flujo de trabajo (consulte [Monitorización](../../automating/using/monitoring-workflow-execution.md)).

La lista de actividades de marketing permite mostrar todos los flujos de trabajo, así como sus estados. Para obtener más información, consulte [Administración de actividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

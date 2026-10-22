---
title: Ciclo de vida del flujo de trabajo
description: Descubra más información sobre el ciclo de vida del flujo de trabajo
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
TQID: 'https://experienceleague.adobe.com/nWv8hOZa2JQgiO2CEnffriIqb6czIA7Gh0AwWCTwRAA'
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
source-wordcount: '200'
ht-degree: 3%
---
# Ciclo de vida del flujo de trabajo {#life-cycle}

El ciclo de vida de un flujo de trabajo incluye tres pasos principales y cada paso está vinculado a un estado y a un color:

* **Edición** (gris)

  Esta es la fase de diseño inicial de un flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow)). El flujo de trabajo aún no se gestiona mediante el servidor y puede modificarse sin ningún riesgo.

* **En curso** (azul)

  Una vez finalizada la fase de diseño inicial, se puede iniciar el flujo de trabajo y el servidor lo gestiona.

* **Finalizado** (verde)

  Un flujo de trabajo finaliza una vez que ya no hay ninguna tarea en curso o cuando un operador ha detenido explícitamente la instancia.

Una vez iniciado, un flujo de trabajo también puede tener otros dos estados:

* **Advertencia** (amarillo)

  El flujo de trabajo no pudo finalizar o se pausó usando los botones ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png).

* **Erróneo** (rojo)

  Se ha producido un error al ejecutar un flujo de trabajo. El flujo de trabajo se ha detenido y el usuario debe llevar a cabo una acción. Para obtener más información sobre este error, use el botón ![](assets/printpreview_darkgrey-24px.png) para acceder al registro de flujo de trabajo (consulte [Supervisión](../../automating/using/monitoring-workflow-execution.md)).

La lista de actividades de marketing permite mostrar todos los flujos de trabajo, así como sus estados. Para obtener más información, consulte [Administración de actividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

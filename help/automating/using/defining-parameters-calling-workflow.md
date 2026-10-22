---
title: Definición de los parámetros al invocar al flujo de trabajo
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
TQID: 'https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%
---
# Definición de los parámetros al invocar al flujo de trabajo {#defining-the-parameters-when-calling-the-workflow}

Esta sección detalla cómo definir parámetros al invocar a un flujo de trabajo. Para obtener más información sobre cómo realizar esta operación desde una llamada de API, consulte la [documentación de las API de REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir los parámetros, asegúrese de que:

* Los parámetros se han declarado en la actividad **[!UICONTROL External Signal]**. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* Se está ejecutando el flujo de trabajo que contiene la actividad de señal.

Para configurar la actividad **[!UICONTROL End]**, siga los pasos a continuación:

1. Abra la actividad **[!UICONTROL End]** y seleccione la pestaña **[!UICONTROL External signal]**.
1. Seleccione el flujo de trabajo y la actividad de señal externa a la que desee llamar.
1. Haga clic en el botón **[!UICONTROL Create element]** para agregar un parámetro y, a continuación, rellene su nombre y valor.

   * **[!UICONTROL Name]**: el nombre que se ha declarado en la actividad **[!UICONTROL External signal]** (consulte [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: el valor que desea asignar al parámetro. El valor debe seguir la **sintaxis estándar**, descrita en [esta sección](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Asegúrese de que todos los parámetros se han declarado en la actividad **[!UICONTROL External signal]**. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y guarde el flujo de trabajo.

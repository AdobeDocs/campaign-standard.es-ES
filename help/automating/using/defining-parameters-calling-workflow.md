---
title: Invocación de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# Definición de los parámetros al invocar al flujo de trabajo {#defining-the-parameters-when-calling-the-workflow}

Esta sección detalla cómo definir parámetros al invocar a un flujo de trabajo. Para obtener más información sobre cómo realizar esta operación desde una llamada a la API, consulte la [documentación de las API de REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir los parámetros, asegúrese de que:

* Los parámetros se han declarado en la actividad **[!UICONTROL External Signal]**. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* El flujo de trabajo que contiene la actividad de señal se está ejecutando.

Para configurar la actividad **[!UICONTROL End]**, siga los pasos a continuación:

1. Abra la actividad **[!UICONTROL End]** y seleccione la pestaña **[!UICONTROL External signal]** .
1. Seleccione el flujo de trabajo y la actividad de señal externa a la que desea llamar.
1. Haga clic en el botón **[!UICONTROL Create element]** para añadir un parámetro y rellene su nombre y valor.

   * **[!UICONTROL Name]**: el nombre que se ha declarado en la  **[!UICONTROL External signal]** actividad (consulte  [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: el valor que desea asignar al parámetro . El valor debe seguir la **sintaxis estándar**, descrita en [esta sección](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Asegúrese de que todos los parámetros se hayan declarado en la actividad **[!UICONTROL External signal]**. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y guarde el flujo de trabajo.

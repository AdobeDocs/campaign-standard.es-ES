---
title: Definición de los parámetros al invocar al flujo de trabajo
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Definición de los parámetros al invocar al flujo de trabajo {#defining-the-parameters-when-calling-the-workflow}

Esta sección detalla cómo definir parámetros al invocar a un flujo de trabajo. Para obtener más información sobre cómo realizar esta operación desde una llamada de API, consulte la [Documentación de API de REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir los parámetros, asegúrese de que:

* Los parámetros se han declarado en **[!UICONTROL External Signal]** actividad. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* Se está ejecutando el flujo de trabajo que contiene la actividad de señal.

Para configurar la variable **[!UICONTROL End]** actividad, siga los pasos a continuación:

1. Abra el **[!UICONTROL End]** actividad, luego seleccione la **[!UICONTROL External signal]** pestaña.
1. Seleccione el flujo de trabajo y la actividad de señal externa a la que desee llamar.
1. Haga clic en **[!UICONTROL Create element]** para agregar un parámetro y, a continuación, rellene su nombre y valor.

   * **[!UICONTROL Name]**: el nombre que se ha declarado en la variable **[!UICONTROL External signal]** actividad (consulte [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: el valor que desea asignar al parámetro. El valor debe ir después de **Sintaxis estándar**, descrito en [esta sección](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Asegúrese de que todos los parámetros se han declarado en **[!UICONTROL External signal]** actividad. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y guarde el flujo de trabajo.

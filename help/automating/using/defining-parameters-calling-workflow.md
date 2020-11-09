---
title: Invocación de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 121b36056317cc89909607220f988c02ae470f08
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---


# Definición de los parámetros al invocar al flujo de trabajo {#defining-the-parameters-when-calling-the-workflow}

En esta sección se explica cómo definir parámetros al llamar a un flujo de trabajo. Para obtener más información sobre cómo realizar esta operación desde una llamada de API, consulte la documentación [de las API de](../../api/using/triggering-a-signal-activity.md)REST.

Antes de definir los parámetros, asegúrese de que:

* Los parámetros se han declarado en la **[!UICONTROL External Signal]** actividad. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* Se está ejecutando el flujo de trabajo que contiene la actividad de señal.

Para configurar la **[!UICONTROL End]** actividad, siga los pasos a continuación:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Seleccione el flujo de trabajo y la actividad de señal externa que desea llamar.
1. Haga clic en el **[!UICONTROL Create element]** botón para agregar un parámetro y luego complete su nombre y valor.

   * **[!UICONTROL Name]**:: el nombre que se declaró en la **[!UICONTROL External signal]** actividad (consulte [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**:: el valor que desea asignar al parámetro. El valor debe seguir la sintaxis **** estándar descrita en [esta sección](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y guarde el flujo de trabajo.

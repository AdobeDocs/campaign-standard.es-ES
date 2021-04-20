---
solution: Campaign Standard
product: campaign
title: Invocación de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 6%

---


# Declaración de los parámetros en la actividad Señal externa {#declaring-the-parameters-in-the-external-signal-activity}

El primer paso para llamar a un flujo de trabajo con parámetros es declararlos en una actividad **[!UICONTROL External signal]**.

1. Abra la actividad **[!UICONTROL External signal]** y seleccione la pestaña **[!UICONTROL Parameters]** .
1. Haga clic en el botón **[!UICONTROL Create element]** y luego especifique el nombre y el tipo de cada parámetro.

   >[!CAUTION]
   >
   >Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez declarados los parámetros, finalice la configuración del flujo de trabajo y, a continuación, ejecútelo.

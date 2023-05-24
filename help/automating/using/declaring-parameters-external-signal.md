---
title: Declaración de los parámetros en la actividad Señal externa
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Declaración de los parámetros en la actividad Señal externa {#declaring-the-parameters-in-the-external-signal-activity}

El primer paso para llamar a un flujo de trabajo con parámetros es declararlos en un **[!UICONTROL External signal]** actividad.

1. Abra el **[!UICONTROL External signal]** actividad, luego seleccione la **[!UICONTROL Parameters]** pestaña.
1. Haga clic en **[!UICONTROL Create element]** y, a continuación, especifique el nombre y el tipo de cada parámetro.

   >[!CAUTION]
   >
   >Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al invocar al flujo de trabajo (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez declarados los parámetros, finalice la configuración del flujo de trabajo y, a continuación, ejecútela.

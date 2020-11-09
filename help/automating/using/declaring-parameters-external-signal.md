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
source-wordcount: '108'
ht-degree: 5%

---


# Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

El primer paso para llamar a un flujo de trabajo con parámetros es declararlos en una **[!UICONTROL External signal]** actividad.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Haga clic en el **[!UICONTROL Create element]** botón y luego especifique el nombre y el tipo de cada parámetro.

   >[!CAUTION]
   >
   >Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez declarados los parámetros, finalice la configuración del flujo de trabajo y, a continuación, ejecútela.

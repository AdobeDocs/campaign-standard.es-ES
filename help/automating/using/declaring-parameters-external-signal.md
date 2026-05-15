---
title: Declaración de los parámetros en la actividad Señal externa
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
TQID: https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 0%

---

# Declaración de los parámetros en la actividad Señal externa {#declaring-the-parameters-in-the-external-signal-activity}

El primer paso para llamar a un flujo de trabajo con parámetros es declararlos en una actividad **[!UICONTROL External signal]**.

1. Abra la actividad **[!UICONTROL External signal]** y seleccione la pestaña **[!UICONTROL Parameters]**.
1. Haga clic en el botón **[!UICONTROL Create element]** y, a continuación, especifique el nombre y el tipo de cada parámetro.

   >[!CAUTION]
   >
   >Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez declarados los parámetros, finalice la configuración del flujo de trabajo y, a continuación, ejecútela.

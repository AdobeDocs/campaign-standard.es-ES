---
solution: Campaign Standard
product: campaign
title: Segmentación según grupos de edad
description: Esta página presenta una segmentación de los perfiles de la base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# Segmentación según grupos de edad {#segmentation-age-groups}

El siguiente ejemplo muestra una segmentación de los perfiles de base de datos según su grupo de edad.

El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad. Teniendo en cuenta que este flujo de trabajo forma parte de una campaña de prueba, cada segmento solo puede contener un máximo de 100 perfiles seleccionados al azar para utilizar audiencias limitadas y representativas a la vez.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo se compone de los siguientes elementos:

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. Los segmentos se definen según los siguientes parámetros:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro de edad para definir el grupo de edad del segmento.

      ![](assets/wkf_segment_new_segment.png)

   * Un límite de tipo **[!UICONTROL Random sampling]** vinculado a un límite **[!UICONTROL Maximum size]** de 100.

      ![](assets/wkf_segment_example_1.png)

* Una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico por segmento.

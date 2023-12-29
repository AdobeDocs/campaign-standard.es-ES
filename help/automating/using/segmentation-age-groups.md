---
title: Segmentación según grupos de edad
description: Esta página presenta una segmentación de los perfiles de base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 51%

---

# Segmentación según grupos de edad {#segmentation-age-groups}

El siguiente ejemplo muestra una segmentación de los perfiles de base de datos según su grupo de edad.

El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad. Teniendo en cuenta que este flujo de trabajo forma parte de una campaña de prueba, cada segmento solo puede contener un máximo de 100 perfiles seleccionados al azar para utilizar audiencias limitadas y representativas a la vez.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo se compone de los siguientes elementos:

* A [Actividad del planificador](../../automating/using/segmentation.md) para especificar la fecha de ejecución del flujo de trabajo.
* A [Consulta](../../automating/using/query.md) actividad para dirigirse a perfiles de personas cuyo cumpleaños y dirección de correo electrónico han sido especificados.
* A [Segmentación](../../automating/using/segmentation.md) actividad para crear 3 segmentos divididos en diferentes transiciones salientes: 18 a 25 años, 26 a 32 años y perfiles mayores de 32 años. Los segmentos se definen según los siguientes parámetros:

  ![](assets/wkf_segment_example_3.png)

   * Un filtro de edad para definir el grupo de edad del segmento.

     ![](assets/wkf_segment_new_segment.png)

   * Un límite de tipo **[!UICONTROL Random sampling]** vinculado a un límite **[!UICONTROL Maximum size]** de 100.

     ![](assets/wkf_segment_example_1.png)

* Un [Envío de correo electrónico](../../automating/using/email-delivery.md) actividad por segmento.

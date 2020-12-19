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

* Una [actividad de Planificador](../../automating/using/segmentation.md) para especificar la fecha de ejecución del flujo de trabajo.
* Una [Consulta](../../automating/using/query.md) actividad a perfiles de destinatarios de personas cuyo cumpleaños y dirección de correo electrónico se han ingresado.
* Una [actividad de segmentación](../../automating/using/segmentation.md) para crear 3 segmentos divididos en diferentes transiciones de salida: 18 a 25 años, 26 a 32 años y perfiles mayores de 32 años. Los segmentos se definen según los siguientes parámetros:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro de edad para definir el grupo de edad del segmento.

      ![](assets/wkf_segment_new_segment.png)

   * Un límite de tipo **[!UICONTROL Random sampling]** vinculado a un límite **[!UICONTROL Maximum size]** de 100.

      ![](assets/wkf_segment_example_1.png)

* Una actividad [envío de correo electrónico](../../automating/using/email-delivery.md) por segmento.

---
title: Segmentación según grupos de edad
description: Esta página presenta una segmentación de los perfiles de base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
TQID: 'https://experienceleague.adobe.com/LkH1qmElMwEn6JGmUaWj7Qpv7arSvLAZixbfJYTi2NQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 58%
---
# Segmentación según grupos de edad {#segmentation-age-groups}

El siguiente ejemplo muestra una segmentación de los perfiles de base de datos según su grupo de edad.

El objetivo del flujo de trabajo es enviar un correo electrónico específico a cada grupo de edad. Teniendo en cuenta que este flujo de trabajo forma parte de una campaña de prueba, cada segmento solo puede contener un máximo de 100 perfiles seleccionados al azar para utilizar públicos limitados y representativos a la vez.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo se compone de los siguientes elementos:

* Una [actividad de planificador](../../automating/using/segmentation.md) para especificar la fecha de ejecución del flujo de trabajo.
* Una actividad [Query](../../automating/using/query.md) para segmentar perfiles de personas cuyo cumpleaños y dirección de correo electrónico han sido especificados.
* Una actividad [Segmentation](../../automating/using/segmentation.md) para crear 3 segmentos divididos en diferentes transiciones salientes: 18 a 25 años, 26 a 32 años y perfiles mayores de 32 años. Los segmentos se definen según los siguientes parámetros:

  ![](assets/wkf_segment_example_3.png)

  * Un filtro de edad para definir el grupo de edad del segmento.

    ![](assets/wkf_segment_new_segment.png)

  * Un límite de tipo **[!UICONTROL Random sampling]** vinculado a un límite **[!UICONTROL Maximum size]** de 100.

    ![](assets/wkf_segment_example_1.png)

* Una actividad de [envío de correo electrónico](../../automating/using/email-delivery.md) por segmento.

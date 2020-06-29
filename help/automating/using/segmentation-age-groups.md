---
title: Segmentación según grupos de edad
description: Esta página presenta una segmentación de los perfiles de la base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico para cada grupo de edad.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# Segmentación según grupos de edad {#segmentation-age-groups}

El siguiente ejemplo muestra una segmentación de los perfiles de base de datos según su grupo de edad.

El objetivo del flujo de trabajo es enviar un correo electrónico específico para cada grupo de edad. Teniendo en cuenta que este flujo de trabajo es parte de una campaña de prueba, cada segmento sólo puede contener un máximo de 100 perfiles seleccionados al azar para utilizar audiencias limitadas y representativas al mismo tiempo.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo se compone de los siguientes elementos:

* Una actividad [de](../../automating/using/segmentation.md) Planificador para especificar la fecha de ejecución del flujo de trabajo.
* actividad de [Consulta](../../automating/using/query.md) a perfiles de destinatarios de personas cuyos cumpleaños y direcciones de correo electrónico se han introducido.
* Una actividad [de segmentación](../../automating/using/segmentation.md) para crear 3 segmentos divididos en diferentes transiciones de salida: 18 a 25 años, 26 a 32 años y perfiles mayores de 32 años. Los segmentos se definen según los siguientes parámetros:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro en la edad para definir el grupo de edad del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Límite de **[!UICONTROL Random sampling]** tipo vinculado a un **[!UICONTROL Maximum size]** límite de 100

      ![](assets/wkf_segment_example_1.png)

* Una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico por segmento.

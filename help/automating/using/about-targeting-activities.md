---
title: Acerca de las actividades de segmentación
description: Se puede acceder a las actividades de objetivo desde el lado izquierdo de la pantalla.
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 52%

---


# Acerca de las actividades de segmentación{#about-targeting-activities}

En la paleta, en el lado izquierdo de la pantalla, despliegue la sección **[!UICONTROL Targeting]**.

Estas actividades son específicas de la segmentación, manipulación de datos de población y filtrado de actividades. Permiten crear uno o más destinatarios definiendo conjuntos y dividiendo o combinando estos conjuntos mediante intersecciones, uniones u operaciones de exclusión.

![](assets/wkf_targeting_activities.png)

La sección **[!UICONTROL Targeting]** ofrece las siguientes actividades:

* [Consulta](../../automating/using/query.md)
* [Consulta incremental](../../automating/using/incremental-query.md)
* [Unión](../../automating/using/union.md)
* [Intersección](../../automating/using/intersection.md)
* [Exclusión](../../automating/using/exclusion.md)
* [Segmentación](../../automating/using/segmentation.md)
* [Leer audiencia](../../automating/using/read-audience.md)
* [Guardar audiencia](../../automating/using/save-audience.md)
* [Deduplicación](../../automating/using/deduplication.md)
* [Enriquecimiento](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** actividades permite definir **códigos de segmento** para sus transiciones salientes. Puede crear informes basados en estos códigos de segmento para medir la eficacia de sus campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

## Selección de datos {#selecting-data}

Puede seleccionar datos mediante las siguientes actividades:

* La actividad **[!UICONTROL Query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Consulte la sección [Consulta](../../automating/using/query.md) .
* La actividad **[!UICONTROL Incremental query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite realizar destinatarios solo en elementos nuevos. Consulte el. [Consulta incremental](../../automating/using/incremental-query.md) .
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmentación de datos {#segmenting-data}

Adobe Campaign permite procesar conjuntos en datos de entrada. De este modo, puede combinar varias poblaciones, excluir parte de ellas o mantener los datos en común con varios destinatarios.

* La actividad **[!UICONTROL Union]** le permite agrupar el resultado de varias actividades en un solo destino. Consulte la sección [Unión](../../automating/using/union.md) .
* La actividad **[!UICONTROL Intersection]** permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad. Consulte la sección [Intersección](../../automating/using/intersection.md) .
* La actividad **[!UICONTROL Exclusion]** permite excluir elementos de una población según determinados criterios. Consulte la sección [Exclusión](../../automating/using/exclusion.md) .
* La actividad **[!UICONTROL Segmentation]** le permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una sola transición o en transiciones diferentes. Consulte la sección [Segmentación](../../automating/using/segmentation.md) .

## Enriquecimiento de datos {#enriching-data}

Los datos identificados y recopilados se pueden enriquecer, añadir y manipular para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de determinación de objetivos incluyendo datos que no estén modelados en el data mart.

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. En particular, puede agregar lo siguiente:

* Datos simples
* Agregados
* Colecciones

**Temas relacionados:**

* [Caso de uso: Personalización de un correo electrónico con datos adicionales](../../automating/using/personalizing-email-with-additional-data.md)

---
solution: Campaign Standard
product: campaign
title: Acerca de las actividades de segmentación
description: Se puede acceder a las actividades de objetivo desde el lado izquierdo de la pantalla.
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

**[!UICONTROL Targeting]** actividades le permite definir  **el** código de segmento para sus transiciones salientes. Puede crear informes basados en estos códigos de segmento para medir la eficacia de sus campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

## Selección de datos {#selecting-data}

Puede seleccionar datos mediante las siguientes actividades:

* La actividad **[!UICONTROL Query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Consulte la sección [Consulta](../../automating/using/query.md).
* La actividad **[!UICONTROL Incremental query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite realizar destinatarios solo en elementos nuevos. Consulte el. [Sección ](../../automating/using/incremental-query.md) de consulta incremental.
* La actividad **[!UICONTROL Read audience]** le permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.Consulte la sección [audiencia de lectura](../../automating/using/read-audience.md).

## Segmentación de datos {#segmenting-data}

Adobe Campaign permite procesar conjuntos en datos de entrada. De este modo, puede combinar varias poblaciones, excluir parte de ellas o mantener los datos en común con varios destinatarios.

* La actividad **[!UICONTROL Union]** le permite agrupar el resultado de varias actividades en un solo destino. Consulte la sección [Unión](../../automating/using/union.md).
* La actividad **[!UICONTROL Intersection]** permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad. Consulte la sección [Intersección](../../automating/using/intersection.md).
* La actividad **[!UICONTROL Exclusion]** permite excluir elementos de una población según determinados criterios. Consulte la sección [Exclusión](../../automating/using/exclusion.md).
* La actividad **[!UICONTROL Segmentation]** le permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una sola transición o en transiciones diferentes. Consulte la sección [Segmentación](../../automating/using/segmentation.md).

## Enriquecimiento de datos {#enriching-data}

Los datos identificados y recopilados se pueden enriquecer, añadir y manipular para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de determinación de objetivos incluyendo datos que no estén modelados en el data mart.

La ficha **[!UICONTROL Additional data]** de las actividades **[!UICONTROL Query]** y **[!UICONTROL Incremental query]** le permite enriquecer los datos dirigidos por la consulta y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se pueden utilizar. En particular, puede agregar lo siguiente:

* Datos simples
* Agregados
* Colecciones

**Temas relacionados:**

* [Caso de uso: Personalización de un correo electrónico con datos adicionales](../../automating/using/personalizing-email-with-additional-data.md)

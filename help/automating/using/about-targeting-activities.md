---
title: Crear un flujo de trabajo de segmentación
description: Se puede acceder a las actividades de segmentación desde la parte izquierda de la pantalla.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 58%

---

# Crear un flujo de trabajo de segmentación{#about-targeting-activities}

En la paleta, en el lado izquierdo de la pantalla, despliegue la sección **[!UICONTROL Targeting]**.

Estas actividades son específicas para la segmentación, la manipulación de datos de población y el filtrado de actividades. Permiten crear uno o más objetivos definiendo conjuntos y dividiendo o combinando estos conjuntos mediante operaciones de intersección, unión o exclusión.

![](assets/wkf_targeting_activities.png)

La sección **[!UICONTROL Targeting]** ofrece las siguientes actividades:

* [Consulta](../../automating/using/query.md)
* [Consulta incremental](../../automating/using/incremental-query.md)
* [Unión](../../automating/using/union.md)
* [Intersección](../../automating/using/intersection.md)
* [Exclusión](../../automating/using/exclusion.md)
* [Segmentación](../../automating/using/segmentation.md)
* [Lectura de audiencia](../../automating/using/read-audience.md)
* [Guardado de audiencia](../../automating/using/save-audience.md)
* [Anulación de duplicación](../../automating/using/deduplication.md)
* [Enriquecimiento](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** Las actividades de le permiten definir lo siguiente **códigos de segmento** para sus transiciones salientes. Puede crear informes basados en estos códigos de segmento para medir la eficacia de sus campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

## Selección de datos {#selecting-data}

Puede seleccionar datos mediante las siguientes actividades:

* La actividad **[!UICONTROL Query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Consulte la [Consulta](../../automating/using/query.md) sección.
* La actividad **[!UICONTROL Incremental query]** permite filtrar y extraer una recopilación de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite dirigirse únicamente a los elementos nuevos Consulte. [Consulta incremental](../../automating/using/incremental-query.md) sección.
* El **[!UICONTROL Read audience]** La actividad de le permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales. Consulte la [Leer audiencia](../../automating/using/read-audience.md) sección.

## Segmentación de datos {#segmenting-data}

Adobe Campaign permite procesar conjuntos de datos entrantes. Por lo tanto, puede combinar varias poblaciones, excluir parte de ellas o solo mantener datos comunes para varios públicos destinatarios.

* La actividad **[!UICONTROL Union]** le permite agrupar el resultado de varias actividades en un solo destino. Consulte la sección [Unión](../../automating/using/union.md).
* La actividad **[!UICONTROL Intersection]** permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad. Consulte la sección [Intersección](../../automating/using/intersection.md).
* La actividad **[!UICONTROL Exclusion]** permite excluir elementos de una población según determinados criterios. Consulte la [Exclusión](../../automating/using/exclusion.md) sección.
* La actividad **[!UICONTROL Segmentation]** le permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una sola transición o en transiciones diferentes. Consulte la [Segmentación](../../automating/using/segmentation.md) sección.

## Enriquecimiento de datos {#enriching-data}

Los datos identificados y recopilados se pueden enriquecer, añadir y manipular para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de segmentación incluyendo datos que no están modelados en el data mart.

El **[!UICONTROL Additional data]** de la pestaña **[!UICONTROL Query]** y **[!UICONTROL Incremental query]** Las actividades de le permiten enriquecer los datos segmentados por la consulta y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se pueden utilizar. En particular, puede agregar lo siguiente:

* Datos simples
* Agregados
* Colecciones

**Temas relacionados:**

* [Caso de uso: Personalización de un correo electrónico con datos adicionales](../../automating/using/personalizing-email-with-additional-data.md)

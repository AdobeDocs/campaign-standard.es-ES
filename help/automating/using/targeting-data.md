---
title: Datos de objetivos
description: Conozca las diferentes maneras de dirigir y seleccionar los datos que necesita.
page-status-flag: nunca activado
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: workflow-general-operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Datos de objetivos{#targeting-data}

## Selección de datos {#selecting-data}

Puede seleccionar datos mediante las siguientes actividades:

* La **[!UICONTROL Query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Consulte la sección [Consulta](../../automating/using/query.md) .
* La **[!UICONTROL Incremental query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite dirigirse únicamente a los nuevos elementos Vea el. [Sección de consulta](../../automating/using/incremental-query.md) incremental.
* La **[!UICONTROL Read audience]** actividad le permite recuperar una audiencia existente y refinarla aplicando condiciones de filtrado adicionales.Consulte la sección [Leer audiencia](../../automating/using/read-audience.md) .

## Segmentación de datos {#segmenting-data}

Adobe Campaign permite procesar conjuntos en datos de entrada. De este modo, puede combinar varias poblaciones, excluir parte de ellas o mantener los datos comunes a varios objetivos.

* La **[!UICONTROL Union]** actividad le permite agrupar el resultado de varias actividades en un único objetivo. Consulte la sección [Unión](../../automating/using/union.md) .
* La **[!UICONTROL Intersection]** actividad permite mantener solo los elementos comunes a las distintas poblaciones entrantes de la actividad. Consulte la sección [Intersección](../../automating/using/intersection.md) .
* La **[!UICONTROL Exclusion]** actividad permite excluir elementos de una población según determinados criterios. Consulte la sección [Exclusión](../../automating/using/exclusion.md) .
* La **[!UICONTROL Segmentation]** actividad permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una única transición o en distintas transiciones. Consulte la sección [Segmentación](../../automating/using/segmentation.md) .

## Enriquecimiento de datos {#enriching-data}

Los datos identificados y recopilados se pueden enriquecer, añadir y manipular para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de determinación de objetivos incluyendo datos que no estén modelados en el data mart.

La **[!UICONTROL Additional data]** ficha de las actividades **[!UICONTROL Query]** y **[!UICONTROL Incremental query]** permite enriquecer los datos dirigidos por la consulta y transferirlos a las siguientes actividades de flujo de trabajo, donde se pueden utilizar. En particular, puede agregar:

* Datos simples
* Acumulados
* Colecciones

**Temas relacionados**

* [Caso de uso: Crear un envío de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso:Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía una nueva entrega a no abridores](../../automating/using/workflow-cross-channel-retargeting.md)

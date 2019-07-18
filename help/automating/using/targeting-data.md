---
title: Datos de objetivo
seo-title: Datos de objetivo
description: Datos de objetivo
seo-description: Obtenga información sobre las distintas formas de destinar y seleccionar los datos que necesita.
page-status-flag: no activado nunca
uuid: 0645 d 6 e 5-6 a 7 e -4917-874 a -7 e 7725 f 06 abd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: flujo de trabajo general operation
discoiquuid: 382 ea 74 e -1662-4 c 64-96 d 7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Targeting data{#targeting-data}

## Selecting data {#selecting-data}

Puede seleccionar los datos mediante las siguientes actividades:

* The **[!UICONTROL Query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. See the [Query](../../automating/using/query.md) section.
* The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite segmentar solo los nuevos elementos Ver el. [Se incrementa](../../automating/using/incremental-query.md) la sección de consulta.
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmenting data {#segmenting-data}

Adobe Campaign permite procesar conjuntos en datos de entrada. Por lo tanto, puede combinar varias poblaciones, excluir parte de ella o mantener los datos comunes a varios objetivos.

* The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target. See the [Union](../../automating/using/union.md) section.
* The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity. See the [Intersection](../../automating/using/intersection.md) section.
* The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria. See the [Exclusion](../../automating/using/exclusion.md) section.
* **[!UICONTROL Segmentation]** La actividad permite crear uno o varios segmentos a partir de una población calculada por actividades colocadas anteriormente en el flujo de trabajo. Al finalizar la actividad, pueden procesarse en una sola transición o en distintas transiciones. See the [Segmentation](../../automating/using/segmentation.md) section.

## Enriching data {#enriching-data}

Los datos identificados y recopilados pueden enriquecerse, agregarse y manipularse para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de segmentación, incluyendo datos que no se modelan en la mart de datos.

**[!UICONTROL Additional data]** La ficha y **[!UICONTROL Query]****[!UICONTROL Incremental query]** las actividades permiten enriquecer los datos dirigidos a la consulta y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se puede utilizar. En particular, puede agregar:

* Datos simples
* Agrega
* Colecciones


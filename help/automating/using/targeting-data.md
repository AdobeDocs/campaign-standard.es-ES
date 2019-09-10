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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Datos de objetivo{#targeting-data}

## Selección de datos {#selecting-data}

Puede seleccionar los datos mediante las siguientes actividades:

* La **[!UICONTROL Query]** actividad le permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Consulte la sección [Consulta](../../automating/using/query.md) .
* La **[!UICONTROL Incremental query]** actividad le permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite segmentar solo los nuevos elementos Ver el. [Se incrementa](../../automating/using/incremental-query.md) la sección de consulta.
* La **[!UICONTROL Read audience]** actividad le permite recuperar una audiencia existente y refinarla aplicando condiciones de filtrado adicionales. Consulte la sección [Leer audiencia](../../automating/using/read-audience.md) .

## Segmentación de datos {#segmenting-data}

Adobe Campaign permite procesar conjuntos en datos de entrada. Por lo tanto, puede combinar varias poblaciones, excluir parte de ella o mantener los datos comunes a varios objetivos.

* La **[!UICONTROL Union]** actividad permite reagrupar el resultado de varias actividades en un solo objetivo. Consulte la sección [Unión](../../automating/using/union.md) .
* La **[!UICONTROL Intersection]** actividad permite mantener solo los elementos comunes a las diferentes poblaciones entrantes de la actividad. Consulte la sección [Intersección](../../automating/using/intersection.md) .
* La **[!UICONTROL Exclusion]** actividad permite excluir elementos de una población según determinados criterios. Consulte la sección [Exclusión](../../automating/using/exclusion.md) .
* **[!UICONTROL Segmentation]** La actividad permite crear uno o varios segmentos a partir de una población calculada por actividades colocadas anteriormente en el flujo de trabajo. Al finalizar la actividad, pueden procesarse en una sola transición o en distintas transiciones. Consulte la sección [Segmentación](../../automating/using/segmentation.md) .

## Enriquecimiento de datos {#enriching-data}

Los datos identificados y recopilados pueden enriquecerse, agregarse y manipularse para optimizar la construcción de objetivos. Puede simplificar y optimizar los procesos de segmentación, incluyendo datos que no se modelan en la mart de datos.

**[!UICONTROL Additional data]** La ficha y **[!UICONTROL Query]****[!UICONTROL Incremental query]** las actividades permiten enriquecer los datos dirigidos a la consulta y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se puede utilizar. En particular, puede agregar:

* Datos simples
* Agrega
* Colecciones

**Temas relacionados**

* [Caso de uso: Crear una entrega de correo electrónico una sola semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en la ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Volver a configurar el flujo de trabajo envío de una nueva entrega a no abiertos](../../automating/using/workflow-cross-channel-retargeting.md)

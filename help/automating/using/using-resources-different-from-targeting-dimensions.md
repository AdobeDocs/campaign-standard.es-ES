---
solution: Campaign Standard
product: campaign
title: Uso de recursos diferentes de dimensiones de segmentación
description: Aprenda a utilizar un recurso que sea diferente a la dimensión de segmentación.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 81%

---


# Uso de recursos diferentes de dimensiones de segmentación {#using-resources-different-from-targeting-dimensions}

Estos casos de uso presentan cómo utilizar un recurso que es diferente de la dimensión de segmentación, por ejemplo, para buscar un registro específico en una tabla distante.

Para obtener más información sobre dimensiones y recursos de segmentación, consulte [esta sección](../../automating/using/query.md#targeting-dimensions-and-resources)

**Ejemplo 1: identificación de perfiles segmentados por el envío con la etiqueta &quot;Bienvenido de nuevo&quot;**.

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. Por lo tanto, estableceremos el recurso en **[!UICONTROL Delivery logs]**. De esta manera, estamos filtrando directamente en la tabla de registro de envíos, lo que da mejores resultados.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Ejemplo 2: identificación de perfiles segmentados por el envío con la etiqueta &quot;Bienvenido de nuevo&quot;**.

En el ejemplo anterior, se utilizaba un recurso distinto de la dimensión de segmentación. Esta operación solo es posible si desea buscar un registro que **esté presente** en la tabla distante (registros de envío en nuestro ejemplo).

Si queremos encontrar un registro que **no está presente** en la tabla distante (por ejemplo, perfiles que no fueron segmentados por un envío específico), debe utilizar el mismo recurso y dimensión de segmentación, ya que el registro no estará presente en la tabla distante (registros de envío).

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. No es posible filtrar directamente los registros de envío, ya que buscamos un registro que no esté presente en la tabla de registros de envío. Por lo tanto, estableceremos el recurso en **[!UICONTROL Profile (profile)]** y construiremos nuestra consulta en la mesa de perfiles.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

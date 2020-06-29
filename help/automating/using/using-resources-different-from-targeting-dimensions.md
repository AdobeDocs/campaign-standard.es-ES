---
title: Uso de recursos diferentes de dimensiones de segmentación
description: Aprenda a utilizar un recurso que sea diferente de la dimensión de segmentación.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Uso de recursos diferentes de dimensiones de segmentación {#using-resources-different-from-targeting-dimensions}

Estos casos de uso muestran cómo utilizar un recurso que es diferente de la dimensión de segmentación, por ejemplo, para buscar un registro específico en una tabla distante.

Para obtener más información sobre dimensiones de segmentación y recursos, consulte [esta sección](../../automating/using/query.md#targeting-dimensions-and-resources)

**Ejemplo 1: identificando perfiles dirigidos por el envío con la etiqueta &quot;Bienvenido de nuevo&quot;**.

* En este caso, queremos destinatario de perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. Por lo tanto, estableceremos el recurso en **[!UICONTROL Delivery logs]**. De esta manera, estamos filtrando directamente en la tabla de registro de envíos, lo que oferta mejores resultados.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Ejemplo 2: identificar a los perfiles que no fueron blanco del envío con la etiqueta &quot;Bienvenido de nuevo&quot;**

En el ejemplo anterior, se utilizaba un recurso distinto de la dimensión de segmentación. Esta operación solo es posible si desea buscar un registro que **esté presente** en la tabla distante (registros de envío en nuestro ejemplo).

Si queremos encontrar un registro que no **está presente** en la tabla distante (por ejemplo, perfiles que no fueron dirigidos por un envío específico), debe utilizar el mismo recurso y dimensión de segmentación, ya que el registro no estará presente en la tabla distante (registros de envío).

* En este caso, queremos destinatario de perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. No es posible filtrar directamente los registros de envío, ya que buscamos un registro que no esté presente en la tabla de registros de envío. Por lo tanto, estableceremos el recurso **[!UICONTROL Profile (profile)]** y construiremos nuestra consulta sobre la mesa de perfiles.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

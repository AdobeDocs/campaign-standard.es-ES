---
title: Uso de recursos diferentes de dimensiones de segmentación
description: Aprenda a utilizar un recurso que sea diferente de la dimensión de segmentación.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: 'https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4'
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
source-wordcount: '295'
ht-degree: 76%
---
# Uso de recursos diferentes de dimensiones de segmentación {#using-resources-different-from-targeting-dimensions}

En estos casos de uso se presenta cómo utilizar un recurso que es diferente de la dimensión de segmentación, por ejemplo, para buscar un registro específico en una tabla distante.

Para obtener más información sobre recursos y dimensiones de segmentación, consulte [esta sección](../../automating/using/query.md#targeting-dimensions-and-resources)

**Ejemplo 1: identificación de perfiles segmentados por el envío con la etiqueta &quot;Bienvenido de nuevo&quot;**.

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. Por lo tanto, estableceremos el recurso en **[!UICONTROL Delivery logs]**. De este modo, estamos filtrando directamente en la tabla de registro de envíos, lo que ofrecerá un mejor rendimiento.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Ejemplo 2: identificación de perfiles segmentados por el envío con la etiqueta &quot;Bienvenido de nuevo&quot;**.

En el ejemplo anterior, se utilizaba un recurso distinto de la dimensión de segmentación. Esta operación solo es posible si desea buscar un registro que **esté presente** en la tabla distante (registros de envío en nuestro ejemplo).

Si queremos encontrar un registro que **no está presente** en la tabla distante (por ejemplo, perfiles que no fueron segmentados por un envío específico), debe utilizar el mismo recurso y dimensión de segmentación, ya que el registro no estará presente en la tabla distante (registros de envío).

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de segmentación en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de envío. No es posible filtrar directamente los registros de envío, ya que buscamos un registro que no esté presente en la tabla de registros de envío. Por lo tanto, estableceremos el recurso en **[!UICONTROL Profile (profile)]** y construiremos nuestra consulta en la tabla de perfiles.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

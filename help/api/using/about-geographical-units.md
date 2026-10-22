---
title: Acerca de unidades geográficas
description: Obtenga más información sobre las unidades geográficas y las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 6%
---

# Acerca de unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>La función de unidad geográfica ha quedado obsoleta con la versión 18.7 de Campaign Standard.
>
>Como resultado, las nuevas instancias de Campaign Standard, así como las instancias existentes sin crear unidades geográficas, no pueden tener esta capacidad implementada a partir de la versión 18.7.
>
>Para obtener más información, consulte la página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">Funciones obsoletas</a>.

El extremo **geoUnitBase** le permite interactuar con unidades geográficas, lo que le permite, por ejemplo, actualizar sus atributos o actualizar la unidad de un perfil.

El campo **Unidad geográfica** se agrega a un perfil al ampliar el recurso de perfil. Como resultado, recuerde usar siempre el extremo **profileAndServicesExt** para interactuar con las unidades geográficas. Para obtener más información sobre la extensión de recursos del perfil, consulte la [documentación de Campaign](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

---
solution: Campaign Standard
product: campaign
title: Acerca de las unidades geográficas
description: Obtenga más información sobre las unidades geográficas y las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Acerca de las unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>La función de unidad geográfica ha quedado obsoleta con la versión 18.7 del Campaign Standard.
>
>Como resultado, las nuevas instancias de Campaign Standard, así como las instancias existentes sin crear unidades geográficas, no pueden tener implementada esta capacidad a partir de la versión 18.7.
>
>Para obtener más información sobre esto, consulte la página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">Funciones obsoletas</a>.

El extremo **geoUnitBase** permite interactuar con unidades geográficas, lo que le permite, por ejemplo, actualizar sus atributos o actualizar la unidad de un perfil.

El campo **Unidad geográfica** se agrega a un perfil al ampliar el recurso de perfil. Como resultado, recuerde utilizar siempre el extremo **profileAndServicesExt** para interactuar con las unidades geográficas. Para obtener más información sobre la extensión de recursos del perfil, consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

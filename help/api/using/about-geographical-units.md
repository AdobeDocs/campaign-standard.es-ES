---
title: Acerca de las unidades geográficas
description: Obtenga más información sobre las unidades geográficas y las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Acerca de las unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>La función Unidad geográfica se ha desaprobado con la versión 18.7 del Campaign Standard.
>
>Como resultado, las nuevas instancias de Campaign Standard, así como las instancias existentes sin crear unidades geográficas, no pueden tener implementada esta capacidad a partir de la versión 18.7.
>
>Para obtener más información, consulte la página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">Funciones obsoletas</a>.

El extremo **geoUnitBase** permite interactuar con unidades geográficas, por ejemplo, para actualizar sus atributos o la unidad de un perfil.

El campo **Geographic unit** se agrega a un perfil al ampliar el recurso de perfil. Como resultado, recuerde utilizar siempre el extremo **profileAndServicesExt** para interactuar con las unidades geográficas. Para obtener más información sobre la extensión de recursos del perfil, consulte la [documentación de Campaign](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

---
solution: Campaign Standard
product: campaign
title: Actualización de la unidad geográfica de un perfil
description: Aprenda a administrar las unidades geográficas con las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---


# Actualización de la unidad geográfica de un perfil {#updating-a-geographical-unit}

1. Realice una solicitud de GET en el recurso **geoUnitBase** para recuperar la unidad geográfica PKey.
1. Realice una solicitud de PATCH en el PKey de perfil, con la unidad geográfica deseada PKey en la carga útil.

<br/>

***Solicitud de muestra***

Recuperar la lista de unidades geográficas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve todas las unidades geográficas. Recupere el PKey de la unidad a la que desea asignar el perfil.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Realice una solicitud de PATCH en el perfil, con el PKey de la unidad geográfica deseada en la carga útil.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->

---
title: Actualización de los atributos de la unidad geográfica
description: Obtenga información sobre cómo actualizar los atributos de una unidad geográfica con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 86810821-6f62-46ab-ba0b-2175797fe9dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 11%

---

# Actualización de los atributos de la unidad geográfica {#managing-geographical-units}

1. Realice una solicitud de GET en el **geoUnitBase** recurso para recuperar la PKey de la unidad geográfica.
1. Realice una solicitud de PATCH en la unidad geográfica, con los atributos que desea actualizar en la carga útil.

<br/>

***Solicitud de ejemplo***

Recupere la lista de unidades geográficas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve todas las unidades geográficas. Recupere la clave PK de la unidad deseada.

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

Realice una solicitud de PATCH en la unidad geográfica, con los atributos que desea actualizar en la carga útil.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->

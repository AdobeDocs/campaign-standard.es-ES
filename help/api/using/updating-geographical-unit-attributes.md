---
solution: Campaign Standard
product: campaign
title: Actualización de los atributos de la unidad geográfica
description: Obtenga información sobre cómo actualizar los atributos de una unidad geográfica con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 12%

---


# Actualización de los atributos de la unidad geográfica {#managing-geographical-units}

1. Realice una solicitud de GET en el recurso **geoUnitBase** para recuperar la PKey de la unidad geográfica.
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

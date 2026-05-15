---
title: Actualización de los atributos de la unidad geográfica
description: Obtenga información sobre cómo actualizar los atributos de una unidad geográfica con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 86810821-6f62-46ab-ba0b-2175797fe9dd
TQID: https://experienceleague.adobe.com/NQoeChz9CMFQEYy8LrNu1FQLGFy5Vgad8l8hmXiIPSU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 0%

---

# Actualización de los atributos de la unidad geográfica {#managing-geographical-units}

1. Realice una petición GET en el recurso **geoUnitBase** para recuperar la clave principal de la unidad geográfica.
1. Realice una solicitud PATCH en la unidad geográfica, con los atributos que desea actualizar en la carga útil.

<br/>

***Solicitud de muestra***

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

Realice una solicitud PATCH en la unidad geográfica, con los atributos que desea actualizar en la carga útil.

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

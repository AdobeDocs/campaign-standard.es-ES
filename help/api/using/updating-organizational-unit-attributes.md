---
title: Actualización de los atributos de una unidad organizativa
description: Obtenga información sobre cómo actualizar los atributos de una unidad organizativa
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 90841afd-ebc2-4b6a-895e-a96ef65740d7
TQID: https://experienceleague.adobe.com/VxXrw8RbDRqNAy14j-302n0mjx0JBOSvsjwfSjAqKAI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 84
ht-degree: 0%

---

# Actualización de los atributos de una unidad organizativa {#updating-organizational-unit-attributes}

1. Realice una petición GET en el recurso **orgUnitBase** para recuperar la clave principal de la unidad organizativa.
1. Realice una petición PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

<br/>

***Solicitud de muestra***

Recupere la lista de unidades organizativas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve todas las unidades organizativas. Recupere la clave PK de la unidad deseada.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Realice una petición PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->

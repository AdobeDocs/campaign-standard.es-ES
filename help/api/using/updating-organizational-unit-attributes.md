---
solution: Campaign Standard
product: campaign
title: Actualización de los atributos de una unidad organizativa
description: Obtenga información sobre cómo actualizar los atributos de una unidad organizativa
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%

---


# Actualización de los atributos de una unidad organizativa {#updating-organizational-unit-attributes}

1. Realice una solicitud de GET en el recurso **orgUnitBase** para recuperar la unidad organizativa PKey.
1. Realice una solicitud de PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

<br/>

***Solicitud de muestra***

Recuperar la lista de unidades organizativas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve todas las unidades organizativas. Recupere el PKey de la unidad deseada.

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

Realice una solicitud de PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

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

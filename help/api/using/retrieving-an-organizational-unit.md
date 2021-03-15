---
solution: Campaign Standard
product: campaign
title: Recuperación de la unidad organizativa de un perfil
description: Aprenda a la unidad organizativa de un perfil con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

---


# Recuperación de la unidad organizativa de un perfil {#retrieving-organizational-units}

1. Realice una solicitud de GET en el PKey de perfil para recuperar la URL **orgUnit**.
1. Realice una solicitud de GET en la dirección URL para recuperar más detalles sobre la unidad organizativa.

<br/>

***Solicitud de ejemplo***

Recupere el registro de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la URL orgUnit del perfil.

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Realice una solicitud de GET en la dirección URL para recuperar más información.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve detalles sobre la unidad organizativa.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```

---
title: Administración de las dependencias orgánicas
description: Obtenga información sobre cómo administrar las unidades organizativas con las API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Administración de las dependencias orgánicas {#managing-organizational-units}

El punto final **orgUnitBase** le permite interactuar con unidades organizativas, por ejemplo, para actualizar sus atributos o la unidad organizativa de un perfil. Para obtener más información sobre las unidades organizativas en Campaign, consulte la documentación [de](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html)Campaign.

El campo Unidad **** organizativa se agrega a un perfil al ampliar el recurso de perfil. Como resultado, recuerde utilizar siempre el punto final **profileAndServicesExt** para interactuar con las unidades geográficas. Para obtener más información sobre la extensión de recursos del perfil, consulte la documentación [de la](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)campaña.

## Recuperación de la unidad organizativa de un perfil

1. Realice una solicitud GET en el perfil PKey para recuperar la dirección URL de **orgUnit** .
1. Realice una solicitud GET en la URL para obtener más detalles sobre la unidad organizativa.

<br/>

***Solicitud de muestra***

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

Realice una solicitud GET en la dirección URL para obtener más información.

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

## Actualización de la unidad organizativa de un perfil

1. Realice una solicitud GET en el recurso **orgUnitBase** para recuperar la unidad organizativa PKey
1. Realice una solicitud PATCH en el PKey del perfil, con la unidad organizativa deseada PKey en la carga útil.

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

Devuelve todas las unidades organizativas. Recupere el PKey de la unidad a la que desea asignar el perfil.

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

Realice una solicitud PATCH en el perfil, con el PKey de la unidad organizativa deseada en la carga útil.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->

## Actualización de atributos de unidad organizativa

1. Realice una solicitud GET en el recurso **orgUnitBase** para recuperar la unidad organizativa PKey.
1. Realice una solicitud PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

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

Realice una solicitud PATCH en la unidad organizativa, con los atributos que desea actualizar en la carga útil.

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

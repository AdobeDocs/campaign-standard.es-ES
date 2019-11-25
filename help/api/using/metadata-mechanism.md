---
title: Mecanismo de metadatos
description: Obtenga más información sobre el mecanismo de metadatos.
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


# Mecanismo de metadatos {#metadata-mechanism}

Puede recuperar los metadatos de recursos mediante **resourceType** en una solicitud GET:

`GET /profileAndServices/resourceType/<resourceName>`

La respuesta devuelve los metadatos principales del recurso (todos los demás campos son descriptivos o internos):

* El nodo **Contenido** devuelve los campos del recurso. Para cada campo del nodo de **contenido** , se pueden encontrar los campos siguientes:

   * "apiName": nombre del atributo utilizado en las API.
   * "type": es la definición de tipo de alto nivel (cadena, número, vínculo, colección, enumeración...).
   * "dataPolicy": el valor del campo debe seguir las reglas de política dadas. Por ejemplo, si la regla dataPolicy se establece en "email", el valor debe ser un correo electrónico válido. Durante un PARCH o un POST, dataPolicy puede comprobar el valor o modificarlo para transformarlo (por ejemplo, smartCase).
   * "category": proporciona la categoría del campo en el editor de consultas.
   * "resType": este es el tipo técnico.

      Si "type" se completa con el valor "link" o "collection", el valor de resTarget es el nombre del recurso dirigido por el vínculo.
Si "type" se completa con el valor "enumeration", se agrega un campo "values" y cada valor de enumeración se detalla en el nodo **values** .

* El nodo **Filtros** devuelve la dirección URL para recuperar los filtros asociados. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Solicitud de muestra***

Realice una solicitud GET en el recurso.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la descripción completa del recurso de perfil.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```

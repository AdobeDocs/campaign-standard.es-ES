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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Mecanismo de metadatos {#metadata-mechanism}

Puede recuperar los metadatos de recursos mediante **resourceType** en una solicitud de GET:

`GET /profileAndServices/resourceType/<resourceName>`

La respuesta devuelve los metadatos principales del recurso (todos los demás campos son descriptivos o internos):

* El nodo **Contenido** devuelve los campos del recurso. Para cada campo del nodo de **contenido** , se pueden encontrar los campos siguientes:

   * &quot;apiName&quot;: nombre del atributo utilizado en las API.
   * &quot;type&quot;: es la definición de tipo de alto nivel (cadena, número, vínculo, colección, lista desglosada...).
   * &quot;dataPolicy&quot;: el valor del campo debe seguir las reglas de política dadas. Por ejemplo, si la regla dataPolicy se establece en &quot;email&quot;, el valor debe ser un correo electrónico válido. Durante un PATCH o un POST, dataPolicy puede comprobar el valor o modificarlo para transformarlo (por ejemplo, smartCase).
   * &quot;categoría&quot;: proporciona la categoría del campo en el editor de consultas.
   * &quot;resType&quot;: este es el tipo técnico.

      Si &quot;type&quot; se completa con el valor &quot;link&quot; o &quot;collection&quot;, el valor de resTarget es el nombre del recurso dirigido por el vínculo.
Si &quot;type&quot; se completa con el valor &quot;lista desglosada&quot;, se agrega un campo &quot;valores&quot; y cada valor de lista desglosada se detalla en el nodo **valores** .

* El nodo **Filtros** devuelve la dirección URL para recuperar los filtros asociados. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Solicitud de muestra***

Realice una solicitud de GET en el recurso.

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

---
solution: Campaign Standard
product: campaign
title: Mecanismo de metadatos
description: Obtenga más información sobre el mecanismo de metadatos.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# Mecanismo de metadatos {#metadata-mechanism}

Puede recuperar los metadatos de recursos mediante **resourceType** en una solicitud de GET:

`GET /profileAndServices/resourceType/<resourceName>`

La respuesta devuelve los metadatos principales del recurso (los demás campos son descriptivos o internos):

* El nodo **Content** devuelve los campos del recurso. Para cada campo del nodo **content**, se pueden encontrar los siguientes campos:

   * &quot;apiName&quot;: nombre del atributo utilizado en las API.
   * &quot;type&quot;: esta es la definición de tipo de alto nivel (cadena, número, vínculo, colección, enumeración...).
   * &quot;dataPolicy&quot;: el valor del campo debe seguir las reglas de directiva dadas. Por ejemplo, si la regla dataPolicy se establece en &quot;correo electrónico&quot;, el valor debe ser un correo electrónico válido. Durante un PATCH o un POST, dataPolicy puede comprobar el valor o modificar el valor que se va a transformar (smartCase, por ejemplo).
   * &quot;categoría&quot;: proporciona la categoría del campo en el editor de consultas.
   * &quot;resType&quot;: este es el tipo técnico.

      Si &quot;type&quot; se completa con el valor &quot;link&quot; o &quot;collection&quot;, el valor resTarget es el nombre del recurso al que se dirige el vínculo.
Si &quot;type&quot; se completa con el valor &quot;enumeration&quot;, se agrega un campo &quot;values&quot; y cada valor de enumeración se detalla en el nodo **values**.

* El nodo **Filters** devuelve la dirección URL para recuperar los filtros asociados. Para obtener más información sobre los filtros, consulte la sección [esta sección](../../api/using/filtering.md).

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Solicitud de ejemplo***

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

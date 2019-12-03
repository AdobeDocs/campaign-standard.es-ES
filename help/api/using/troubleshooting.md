---
title: Resolución de problemas
description: Obtenga más información sobre problemas comunes relacionados con las API de Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Resolución de problemas {#troubleshooting}

* **Al ir a la consola Adobe.io, aparece el siguiente error: "La consola de Adobe I/O solo está disponible para seleccionar miembros de cuentas de empresa. Si cree que debe tener acceso, póngase en contacto con el administrador del sistema."**

Solo puede crear claves de API para las organizaciones de IMS que administra. Si se muestra este mensaje y desea crear claves de API, y desea preguntar a un administrador de la organización de IMS.

* **Al realizar una solicitud a Adobe.io, se obtiene {"error_code":"403023","message":"El perfil no es válido"}**

Esto significa que existe un problema con el aprovisionamiento de IMS del producto específico de la campaña: el equipo de IMS necesita arreglarlo.

Para obtener más información, puede llamar a la API de IMS con su token para ver el aspecto del perfil de IMS: Debe tener un prodCtx en el que el identificador de organización sea el mismo que el que introdujo para que Adobe.io pueda enrutar la solicitud.
Si falta el aprovisionamiento de IMS, debe corregirse.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve el siguiente error.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Consulte su perfil de IMS con esta solicitud.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

En la respuesta, el valor ORGANIZATION_ID debe ser el mismo en la primera solicitud GET.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Al realizar una solicitud a Adobe.io, se obtiene {"code":500, "message":"Ups. Algo salió mal. Compruebe su URI e inténtelo de nuevo."}**

Adobe.io declara su URI no válido: lo más probable es que el URI que solicita no sea válido. En Adobe.io, al seleccionar el servicio Campaign, se obtiene un selector con una lista de posibles valores de Organization_ids. Debe comprobar que el que elija es el que introdujo en la dirección URL.

* **Al realizar una solicitud a Adobe.io, se obtiene {"error_code":"401013","message":"El autentificador de autenticación no es válido"}**

El token no es válido (se usa una llamada IMS incorrecta para generar un token) o el token ha caducado.

* **No veo mi perfil después de la creación**

Según la configuración de instancia, el perfil creado debe asociarse a una **orgUnit**. Para comprender cómo agregar este campo en la creación, consulte [esta sección](../../api/using/creating-profiles.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->

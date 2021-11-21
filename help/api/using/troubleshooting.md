---
title: Resolución de problemas
description: Obtenga más información sobre problemas comunes relacionados con las API de Campaign Standard.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Resolución de problemas {#troubleshooting}

* **Al ir a la consola Adobe.io, aparece el siguiente error: &quot;La consola Adobe I/O solo está disponible para miembros seleccionados de cuentas de empresa. Si cree que debe tener acceso, póngase en contacto con el administrador del sistema.&quot;**

Solo puede crear claves de API para las organizaciones de IMS de las que es administrador. Si este mensaje se muestra y desea crear claves de API y desea solicitar al administrador de la organización IMS.

* **Al realizar una solicitud a Adobe.io, se obtiene {&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;El perfil no es válido&quot;}**

Esto significa que existe un problema con el aprovisionamiento IMS de su producto específico de Campaign: el equipo de IMS debe solucionarlo.

Para obtener más información, puede llamar a la API de IMS con su token para ver el aspecto que tiene su perfil de IMS: Debe tener un prodCtx en el que el identificador de organización sea el mismo que el que introdujo en la URL de Adobe.io para poder enrutar la solicitud.
Si falta, es necesario corregir el aprovisionamiento de IMS.

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

Compruebe el perfil de IMS con esta solicitud.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

En la respuesta, el valor ORGANIZATION_ID debe ser el mismo en la primera solicitud de GET.

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

* **Al realizar una solicitud a Adobe.io, obtienes {&quot;code&quot;:500, &quot;message&quot;:&quot;Oops. Algo salió mal. Compruebe su URI e inténtelo de nuevo.&quot;}**

Adobe.io declara su URI no válido: lo más probable es que el URI que solicita no sea válido. En Adobe.io, al seleccionar el servicio de Campaign, se obtiene un selector con una lista de posibles valores de Organization_ids. Debe comprobar que el que elija es el que introdujo en su URL.

* **Al realizar una solicitud a Adobe.io, se obtiene {&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

El token no es válido (se usa una llamada IMS incorrecta para generar un token) o su token ha caducado.

* **No veo mi perfil después de la creación**

Según la configuración de la instancia, el perfil creado debe asociarse a un **orgUnit**. Para comprender cómo añadir este campo en la creación, consulte [esta sección](../../api/using/creating-profiles.md).

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

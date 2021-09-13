---
title: Recuperación de suscripciones
description: Obtenga información sobre cómo recuperar suscripciones con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Recuperación de suscripciones {#retrieving-subscriptions}

## Recuperación de los perfiles suscritos a un servicio

Este es un procedimiento de dos pasos.

1. Recupere la URL de suscripciones del servicio deseado.
1. Realice una solicitud de GET en la URL de suscripciones. Devuelve la lista de suscripciones para el servicio, con cada perfil asociado.

>[!CAUTION]
>
>La API de REST devuelve la propiedad &quot;href&quot;, que contiene la dirección URL que se va a usar. <b>Utilice siempre la URL contenida en la respuesta para realizar la siguiente solicitud</b> de API.

<br/>

***Solicitud de ejemplo***

Realice una solicitud de GET para recuperar el servicio.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la URL de suscripciones del servicio.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Realice una solicitud de GET en la URL de suscripciones.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Se muestra la lista de suscripciones para el servicio, con cada perfil asociado.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Recuperación de los servicios a los que se suscribió un perfil

Este es un procedimiento de dos pasos.

1. Recupere la URL de suscripciones de un perfil determinado.
1. Realice una solicitud de GET en la dirección URL. Devuelve la lista de suscripciones para el perfil, con cada servicio asociado.

<br/>

***Solicitud de ejemplo***

Realice una solicitud de GET para recuperar el perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la URL de suscripciones del perfil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Realice una solicitud de GET en la URL de suscripciones.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de servicios a los que se suscribió el perfil.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```

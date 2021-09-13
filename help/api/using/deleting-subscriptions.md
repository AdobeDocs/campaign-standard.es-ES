---
title: Eliminación de suscripciones
description: Obtenga información sobre cómo eliminar suscripciones con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 76e2d102-c877-41a6-af87-2f407201a572
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Eliminación de suscripciones {#mdeleting-subscriptions}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Eliminación de una suscripción de servicio para un perfil específico {#deleting-service-subscription}

Este es un procedimiento de tres pasos.

1. Recupere la URL de suscripciones para el perfil deseado.
1. Realice una solicitud de GET en la URL de suscripciones.
1. Realice una solicitud de DELETE en la dirección URL de servicio deseada.

Si la solicitud de eliminación se realiza correctamente, el estado de la respuesta es 204 Sin contenido.

<br/>

***Solicitud de ejemplo***

Las cargas útiles de ejemplo que se muestran a continuación muestran cómo cancelar la suscripción de un perfil de un servicio. En primer lugar, realice una solicitud de GET para recuperar el perfil.

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

Devuelve la lista de suscripciones para el perfil seleccionado, con una URL para cada servicio suscrito.

```
...
"service": {
  "PKey": "<PKEY>",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
  "label": "Sport Newsletter",
  "name": "SVC1",
  "title": "Sport Newsletter (SVC1)"
},
...
```

Realice una solicitud de DELETE en la dirección URL de servicio deseada.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Eliminación de una suscripción de servicio para un perfil específico

Este es un procedimiento de tres pasos.

1. Recupere el servicio deseado y su URL de suscripción.
1. Realice una solicitud de GET en la URL de suscripciones para recuperar todas las suscripciones de perfiles.
1. Realice una solicitud de DELETE en la URL de suscripción de perfil deseada.

Si la solicitud de eliminación se realiza correctamente, el estado de la respuesta es 204 Sin contenido.

<br/>

***Solicitud de ejemplo***

Recupere el registro de servicio.

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
  "mode": "newsletter",
  "name": "SVC3",
  "subScenarioEventType": "subscriptionEvent",
  "subscriptions": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
  },
  "targetResource": "profile",
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

Devuelve la lista de suscripciones para el servicio seleccionado, con una URL (href) para cada suscripción de perfil.

```
{
  "PKey": "<PKEY>",
  "created": "2019-03-26 08:58:04.764Z",
  "email": "",
  "expirationDate": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY>",
  "metadata": "subscriptionRcp",
  "service": ...,
  "serviceName": "SVC3",
  "subscriber": ...,
  ...
}
```

Realice una solicitud de DELETE en la URL de suscripción de perfil deseada.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

---
title: Interactuar con el historial de marketing
description: Aprenda a interactuar con el historial de marketing de los perfiles
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Interactuar con el historial de marketing{#interacting-with-marketing-history}

El **historia** el punto de conexión permite interactuar con el historial de marketing de un perfil.
De este modo, puede, por ejemplo, recuperar fácilmente la página espejo de una entrega enviada a un perfil. Para realizar esto, siga los pasos a continuación:

1. Realice una GET con **historia** extremo y clave principal del perfil.
1. Realice una solicitud de GET en **eventos** href devuelto.
1. Devuelve la lista de eventos del perfil con vínculos a páginas espejo en el **mirrorPage** nodo.

<br/>

***Solicitud de ejemplo***

Recupere el historial de marketing del perfil con una solicitud de GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

El nodo &quot;events&quot; devuelve la dirección URL que le permite acceder a los eventos del perfil.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Realice una solicitud de GET sobre los eventos href devueltos.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de eventos para el perfil con vínculos a páginas espejo en el nodo &quot;mirrorPage&quot;.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```

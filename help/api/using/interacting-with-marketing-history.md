---
solution: Campaign Standard
product: campaign
title: Interacción con el historial de marketing
description: Obtenga información sobre cómo interactuar con el historial de marketing de los perfiles.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 10%

---


# Interacción con el historial de marketing {#interacting-with-marketing-history}

El extremo **history** permite interactuar con el historial de marketing de un perfil.
De este modo, puede, por ejemplo, recuperar fácilmente la página espejo para una entrega que se envió a un perfil. Para realizar esto, siga los pasos a continuación:

1. Realice una GET con el extremo **history** y la clave principal del perfil.
1. Realice una solicitud de GET en el href **events** devuelto.
1. Devuelve la lista de eventos para el perfil con vínculos a páginas espejo en el nodo **mirrorPage**.

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

El nodo &quot;events&quot; devuelve la URL que le proporciona acceso a los eventos del perfil.

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

Realice una solicitud de GET en los eventos href devueltos.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de eventos del perfil con vínculos a páginas espejo en el nodo &quot;mirrorPage&quot;.

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

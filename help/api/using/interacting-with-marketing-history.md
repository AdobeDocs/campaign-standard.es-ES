---
title: Interactuar con el historial de marketing
description: Aprenda a interactuar con el historial de marketing de los perfiles
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Interactuar con el historial de marketing{#interacting-with-marketing-history}

El extremo **history** le permite interactuar con el historial de marketing de un perfil.
De este modo, puede, por ejemplo, recuperar fácilmente la página espejo de una entrega enviada a un perfil. Para realizar esto, siga los pasos a continuación:

1. Realice una GET con el extremo **history** y la clave principal del perfil.
1. Realizar una petición GET en los **eventos** href devueltos.
1. Devuelve la lista de eventos del perfil con vínculos a páginas espejo en el nodo **mirrorPage**.

<br/>

***Solicitud de muestra***

Recupere el historial de marketing del perfil con una petición GET.

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

Realizar una petición GET en los eventos href devueltos.

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

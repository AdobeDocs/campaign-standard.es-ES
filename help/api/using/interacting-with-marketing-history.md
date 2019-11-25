---
title: Interactuar con el historial de mercadotecnia
description: Descubra cómo interactuar con el historial de marketing de los perfiles.
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


# Interactuar con el historial de mercadotecnia {#interacting-with-marketing-history}

El punto final del **historial** le permite interactuar con el historial de mercadotecnia de un perfil.
De este modo, puede, por ejemplo, recuperar fácilmente la página reflejada para una entrega que se envió a un perfil. Para realizar esto, siga los pasos a continuación:

1. Realice una operación GET con el extremo del **historial** y la clave principal del perfil.
1. Realice una solicitud GET en el **evento** href devuelto.
1. Devuelve la lista de eventos del perfil con vínculos a páginas reflejadas en el nodo **mirrorPage** .

<br/>

***Solicitud de muestra***

Recupere el historial de marketing del perfil con una solicitud GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/History/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

El nodo "events" devuelve la dirección URL que le permite acceder a los eventos del perfil.

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

Realice una solicitud GET en los eventos href devueltos.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de eventos del perfil con vínculos a páginas reflejadas en el nodo "mirrorPage".

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

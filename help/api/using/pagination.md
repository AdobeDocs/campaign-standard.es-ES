---
title: Paginación
description: Aprenda a realizar operaciones de paginación.
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


# Paginación

De forma predeterminada, se cargan 25 recursos en una lista.

El parámetro **_lineCount** permite limitar el número de recursos enumerados en la respuesta.  A continuación, puede utilizar el nodo **siguiente** para mostrar los resultados siguientes.

>[!NOTE]&gt;
>
>Utilice siempre el valor de URL devuelto en el **siguiente** nodo para realizar una solicitud de paginación.
>
>La solicitud **_lineStart** se calcula y siempre debe usarse dentro de la dirección URL devuelta en el nodo **siguiente** .

<!-- serverside pagination. quand table très longue (au delà de 100.000), on peut plus faire de next. doit utiliser à la place les trucs type lineStart etc. si false: voudra dirre que ça a atteint la limite-->

<br/>

***Solicitud de muestra***

Ejemplo de solicitud GET para mostrar 1 registro del recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- dans l'exemple, avoir le node "next"-->

Respuesta a la solicitud.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    ...
}
```

---
solution: Campaign Standard
product: campaign
title: Paginación
description: Aprenda a realizar operaciones de paginación.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Paginación

De forma predeterminada, se cargan 25 recursos en una lista.

El parámetro **_lineCount** permite limitar el número de recursos enumerados en la respuesta.  A continuación, puede utilizar el nodo **siguiente** para mostrar los resultados siguientes.

>[!NOTE]
>
>Utilice siempre el valor de URL devuelto en el **siguiente** nodo para realizar una solicitud de paginación.
>
>La solicitud **_lineStart** se calcula y siempre debe usarse dentro de la dirección URL devuelta en el nodo **siguiente** .

<br/>

***Solicitud de muestra***

Muestra de una solicitud de GET para mostrar 1 registro del recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Respuesta a la solicitud, con el **siguiente** nodo para realizar la paginación.

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
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

De forma predeterminada, el **siguiente** nodo no está disponible al interactuar con tablas con una gran cantidad de datos. Para poder realizar la paginación, debe agregar el parámetro **_forcePagination=true** a la dirección URL de la llamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>El número de registros por encima del cual una tabla se considera grande se define en la opción **XtkBigTableThreshold** Campaign Standard. El valor predeterminado es 100.000 registros.

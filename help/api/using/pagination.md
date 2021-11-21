---
title: Paginación
description: Aprenda a realizar operaciones de paginación.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Paginación

De forma predeterminada, se cargan 25 recursos en una lista.

La variable **_lineCount** le permite limitar el número de recursos que aparecen en la respuesta.  A continuación, puede usar la variable **next** para mostrar los siguientes resultados.

>[!NOTE]
>
>Utilice siempre el valor de URL devuelto en la variable **next** para realizar una solicitud de paginación.
>
>La variable **_lineStart** se calcula y siempre debe utilizarse dentro de la URL devuelta en la variable **next** nodo .

<br/>

***Solicitud de ejemplo***

Solicitud de GET de ejemplo para mostrar 1 registro del recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Respuesta a la solicitud, con la variable **next** para realizar la paginación.

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

De forma predeterminada, la variable **next** no está disponible cuando interactúa con tablas con una gran cantidad de datos. Para poder realizar la paginación, debe añadir la variable **_forcePagination=true** a la dirección URL de la llamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>El número de registros por encima de los cuales una tabla se considera grande se define en el Campaign Standard **XtkBigTableThreshold** . El valor predeterminado es 100 000 registros.

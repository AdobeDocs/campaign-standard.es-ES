---
title: Creación de perfiles
description: Obtenga más información sobre cómo crear perfiles con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación de perfiles con API {#creating-profiles-api}

La creación de perfiles se realiza con un **POST** en el recurso de perfil.

>[!CAUTION]
>
>Si desea asociar un <b>orgUnit</b> al perfil creado, debe ampliar el recurso de perfil con este campo y, después de la publicación de la extensión, realizar una solicitud de POST en la variable <b>ProfileAndServicesExt</b> punto final.
>
>Para obtener más información sobre la extensión de recursos del perfil, consulte la <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Documentación de Campaign</a>.

<br/>

***Solicitud de ejemplo***

Ejemplo de solicitud de POST para crear un perfil con el correo electrónico &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Devuelve el perfil recién creado, con la dirección de correo electrónico &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```

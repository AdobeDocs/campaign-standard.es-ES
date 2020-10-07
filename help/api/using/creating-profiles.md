---
title: Creación de perfiles
description: Obtenga más información sobre cómo crear perfiles con API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Creación de perfiles {#creating-profiles}

La creación de perfiles se realiza con una solicitud de **POST** en el recurso de perfil.

>[!CAUTION]
>
>Si desea asociar una <b>orgUnit</b> al perfil creado, debe ampliar el recurso de perfil con este campo y, después de la publicación de la extensión, realizar una solicitud de POST en el extremo <b>ProfileAndServicesExt</b> .
>
>Para obtener más información sobre la extensión de recursos del perfil, consulte la documentación <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">de la</a>Campaña.

<br/>

***Solicitud de muestra***

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

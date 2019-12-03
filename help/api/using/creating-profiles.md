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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Creación de perfiles {#creating-profiles}

La creación de perfiles se realiza con una solicitud **POST** en el recurso de perfil.

>[!CAUTION]
>
>Si desea asociar una <b>orgUnit</b> al perfil creado, debe extender el recurso de perfil a este campo y, después de la publicación de la extensión, realizar una solicitud POST en el extremo <b>ProfileAndServicesExt</b> .
>
>Para obtener más información sobre la extensión de recursos del perfil, consulte la documentación <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">de la</a>campaña.

<br/>

***Solicitud de muestra***

Ejemplo de solicitud POST para crear un perfil con el correo electrónico "john.doe@mail.com".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Devuelve el perfil recién creado, con la dirección de correo electrónico "john.doe@mail.com".

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

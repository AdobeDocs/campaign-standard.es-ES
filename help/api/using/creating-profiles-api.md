---
title: Creación de perfiles con API
description: Obtenga más información sobre cómo crear perfiles con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
TQID: 'https://experienceleague.adobe.com/2oXCyiODHkmEMNaJ2VThbfp0ht0XWhKGd13S9zBhdig'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%
---
# Creación de perfiles con API {#creating-profiles-api}

La creación de perfiles se realiza con una solicitud **POST** en el recurso de perfil.

>[!CAUTION]
>
>Si desea asociar una <b>orgUnit</b> al perfil creado, debe ampliar el recurso de perfil con este campo y, después de la publicación de la extensión, realizar una petición POST en el extremo <b>ProfileAndServicesExt</b>.
>
>Para obtener más información sobre la extensión de recursos del perfil, consulte la <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentación de Campaign</a>.

<br/>

***Solicitud de muestra***

Ejemplo de solicitud POST para crear un perfil con el correo electrónico &quot;john.doe@mail.com&quot;.

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

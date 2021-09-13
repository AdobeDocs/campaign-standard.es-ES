---
title: Administración de la exclusión de CCPA
description: Obtenga información sobre cómo administrar la exclusión de CCPA con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# Administración de la exclusión de CCPA {#managing-ccpa-optout}

El estado de exclusión de la CCPA de un perfil se puede supervisar y administrar utilizando el atributo de perfil **ccpaOptOut** y los valores &quot;true&quot; o &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**: prohíbe la venta de información personal.
* **false**: autoriza la venta de información personal.

>[!CAUTION]
>
>El atributo de exclusión de CCPA solo está disponible a partir de la versión 19.4. Para los entornos de la versión 19.3, debe ampliar el recurso Perfiles y agregar un campo booleano. Este campo se añade a la API con la etiqueta elegida. Le sugerimos que utilice &quot;Exclusión de la CCPA&quot;.
>
>Para obtener más información, consulte [Administración de solicitudes de privacidad](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

<br/>

***Solicitudes de muestra***

* Solicitud de GET de ejemplo para recuperar el estado de exclusión de la CCPA de un perfil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Respuesta a la solicitud de GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Solicitud de POST de muestra para marcar un perfil de exclusión de CCPA.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Respuesta a la solicitud de GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Solicitud del PATCH de muestra para actualizar un perfil de exclusión de CCPA.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Respuesta a la solicitud de GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

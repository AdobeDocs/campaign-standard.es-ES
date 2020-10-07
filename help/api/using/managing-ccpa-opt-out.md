---
title: Administración de la exclusión de CCPA
description: Obtenga información sobre cómo administrar la exclusión de CCPA con las API
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
source-wordcount: '153'
ht-degree: 3%

---


# Administración de la exclusión de CCPA {#managing-ccpa-optout}

El estado de exclusión de CCPA de un perfil se puede supervisar y administrar usando el atributo de perfil **ccpaOptOut** y los valores &quot;true&quot; o &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**:  prohíbe la venta de información personal.
* **false**: autoriza la venta de información personal.

>[!CAUTION]
>
>El atributo de exclusión de CCPA solo está disponible a partir de la versión 19.4. Para los entornos 19.3, debe ampliar el recurso Perfiles y agregar un campo booleano. Este campo se agregará a la API con la etiqueta seleccionada. Le sugerimos que utilice &quot;Opción de exclusión para CCPA&quot;.
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Solicitudes de muestra***

* Muestra de una solicitud de GET para recuperar el estado de exclusión de CCPA de un perfil.

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

* Muestra de una solicitud de POST para marcar un perfil para la exclusión de CCPA.

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

* Muestra de una solicitud de PATCH para actualizar un perfil para la exclusión de CCPA.

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

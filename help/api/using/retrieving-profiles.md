---
title: Recuperación de perfiles
description: Obtenga más información sobre cómo recuperar perfiles con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---

# Recuperación de perfiles {#retrieving-profiles}

La recuperación de perfiles se realiza con un **GET** solicitud.

A continuación, puede restringir la búsqueda utilizando filtros, pedidos y paginación. Para obtener más información, consulte [Operaciones adicionales](../../api/using/sorting.md) para obtener más información.

Además, las API de Campaign Standard permiten buscar perfiles en función de uno de estos campos: correo electrónico, nombre, apellidos o cualquier campo personalizado. Para obtener más información, consulte [esta sección](#searching-field).

<br/>

***Solicitudes de muestra***

* Ejemplo de solicitud de GET para recuperar todos los perfiles.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

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
           },
           ...
   }
   ```

* Ejemplo de solicitud de GET para recuperar los primeros 10 valores de correo electrónico.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Respuesta a la solicitud. El nodo &quot;next&quot; devuelve la URL que le proporciona acceso a los 10 siguientes valores de correo electrónico.

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```

## Búsqueda de perfiles basados en un campo {#searching-field}

La variable **[!UICONTROL filterType]** permite recuperar perfiles en función de uno de estos campos: correo electrónico, nombre, apellidos o cualquier campo personalizado que se haya añadido en Filtro avanzado al ampliar el recurso de perfil.

>[!NOTE]
>
>Las búsquedas distinguen entre mayúsculas y minúsculas y se realizan únicamente en prefijos. Por ejemplo, no podrá buscar un perfil con las últimas letras de su apellido.

***Solicitudes de muestra***

* Solicitud de muestra para filtrar perfiles según el nombre.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitud de muestra para filtrar perfiles según el apellido.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitud de ejemplo para filtrar perfiles por correo electrónico.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitud de ejemplo para filtrar perfiles según el campo personalizado &quot;Hobby&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

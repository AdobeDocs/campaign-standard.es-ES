---
solution: Campaign Standard
product: campaign
title: Ordenar
description: Más información sobre cómo realizar operaciones de ordenación
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# Ordenar

La ordenación está disponible en orden ascendente o descendente. Para ello, utilice el parámetro **%20desc** o **%20asc** en la solicitud.

Para saber si se puede ordenar un campo, compruebe el parámetro &quot;ordenable&quot; en los metadatos del recurso. Para obtener más información, consulte [esta sección](../../api/using/metadata-mechanism.md).

<br/>

***Solicitudes de muestra***

* Muestra de una solicitud de GET para recuperar correos electrónicos en la base de datos ordenados alfabéticamente.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Respuesta a la solicitud.

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* Muestra de una solicitud de GET para recuperar el correo electrónico en la base de datos en un orden alfa descendente.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Respuesta a la solicitud.

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```

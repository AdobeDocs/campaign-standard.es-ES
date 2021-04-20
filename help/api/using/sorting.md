---
solution: Campaign Standard
product: campaign
title: Ordenar
description: Obtenga más información sobre cómo realizar operaciones de ordenación
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%

---


# Ordenar

La ordenación está disponible en orden ascendente o descendente. Para ello, utilice el parámetro **%20desc** o **%20asc** de la solicitud.

Para saber si un campo se puede ordenar, compruebe el parámetro &quot;ordenable&quot; en los metadatos del recurso. Para obtener más información, consulte [esta sección](../../api/using/metadata-mechanism.md).

<br/>

***Solicitudes de muestra***

* Ejemplo de solicitud de GET para recuperar correos electrónicos en la base de datos ordenados alfabéticamente.

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

* Solicitud de GET de ejemplo para recuperar el correo electrónico de la base de datos en un orden alfa descendente.

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

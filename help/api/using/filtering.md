---
solution: Campaign Standard
product: campaign
title: Filtrar
description: Obtenga información sobre cómo realizar operaciones de filtrado.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---


# Filtrar {#filtering}

## Recuperación de metadatos de filtros

Hay filtros disponibles para cada recurso. Para identificar los filtros asociados a un recurso, debe realizar una solicitud de GET en los metadatos del recurso. Esta solicitud devuelve la dirección URL donde se definen todos los filtros para un recurso determinado. Para obtener más información sobre los metadatos, consulte [esta sección](../../api/using/metadata-mechanism.md).

Para identificar los metadatos de un filtro y determinar cómo utilizarlo, debe realizar una solicitud de GET en la URL devuelta anteriormente.

<br/>

***Solicitud de muestra***

Las cargas útiles de ejemplo siguientes muestran cómo recuperar los metadatos del filtro &quot;byText&quot; para el recurso &quot;perfil&quot;. En primer lugar, realice una solicitud de GET en el recurso de &quot;perfil&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la dirección URL donde se describen los filtros.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Realice una solicitud de GET en la dirección URL. Devuelve la lista de filtros para el recurso de perfil, con los metadatos asociados a cada filtro.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## Estructura de metadatos de filtros

La misma estructura de metadatos está disponible para cada filtro:

* Los campos **@formType** y **@webPage** son campos técnicos.
* El campo **data** proporciona una muestra de cómo utilizar el filtro.
* El nodo **metadata** describe los parámetros del filtro.
* El nodo **condición** describe el objetivo del filtro. Los parámetros de filtro descritos en el nodo de metadatos se utilizan para crear condiciones de filtro. Para cada condición de filtro, si **enabledSi** es verdadero, se aplicará la **expresión**.

<br/>

Muestra de estructura de metadatos de filtro:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## Uso de filtros

El filtrado se realiza con la siguiente solicitud:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

Es posible combinar varios filtros en una sola solicitud:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Solicitudes de muestra***

* Muestra de una solicitud de GET para recuperar los recursos de &quot;servicio&quot; con el tipo &quot;correo electrónico&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* Ejemplo de solicitud de GET para recuperar los recursos &quot;perfil&quot; que contienen &quot;Doe&quot; en
los campos Correo electrónico o Apellido (el filtro porTexto busca en los campos Correo electrónico y Apellido).

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
           }
           ...
       ],
       ...
   }
   ```

* Ejemplo de solicitud de GET para recuperar los recursos de servicios con el tipo &quot;correo electrónico&quot; y la etiqueta &quot;deporte&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## Filtros personalizados

Si desea utilizar un filtro personalizado, debe crearlo y personalizarlo en la interfaz de Adobe Campaign Standard. El filtro personalizado tendrá el mismo comportamiento que los filtros predeterminados:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Para obtener más información sobre esto, consulte la documentación del Campaign Standard:

* [Configuración de la definición del filtro](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [Caso de uso: Llamar a un recurso mediante una clave](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html) de identificación compuesta.

<br/>

***Solicitud de muestra***

Muestra de la solicitud de GET para recuperar los recursos de &quot;perfil&quot; con cantidades de transacción de 100$ o más. Tenga en cuenta que el filtro &quot;byAmount&quot; se ha definido primero en la interfaz de Adobe Campaign Standard y se ha vinculado a la tabla personalizada &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->

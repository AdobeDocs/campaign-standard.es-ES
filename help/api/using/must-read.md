---
solution: Campaign Standard
product: campaign
title: Lectura obligatoria
description: Debe leerse antes de usar API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## Requisitos técnicos

* Las API de Adobe Campaign deben usarse solo de servidor a servidor.
* Consulte siempre con el contacto técnico de su Adobe si el caso de uso que desea implementar está alineado con la escala permitida por las API de Adobe Campaign.
* La configuración de un acceso de AdobeIO requiere permisos específicos, póngase en contacto con la asistencia técnica de Adobe para cualquier problema.

## Representación de recursos

Todos los recursos de API están disponibles en **JSON** con una extensión URL o dentro de un encabezado de aceptación HTTP:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Sin extensión en la URL, el formato **json es el formato predeterminado** para el tipo de contenido.

<br/>

***muestra de solicitud***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Clave principal y direcciones URL

* No intente crear una dirección URL usted mismo. La API devuelve todas las direcciones URL. Sin embargo, es posible crear una URL basada en el nombre del recurso de nivel superior.

* Los valores de clave principal automática (PKey) que ilustran los ejemplos no están pensados para funcionar en otra implementación específica. Son producidos por la API de Adobe Campaign.

* Los valores de clave principal automática generados por Adobe Campaign nunca deben almacenarse en una base de datos o sitio web externo. Debe generar campos clave específicos en la definición de la base de datos y utilizarlos durante los desarrollos.

## Claves personalizadas {#custom-keys}

Si el recurso de perfil se ha ampliado con un campo de clave personalizada, puede utilizar este campo como clave en lugar de la clave principal automática generada por Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Las claves personalizadas no se pueden modificar con una operación de PATCH si el valor clave es diferente de la clave de origen o si está utilizando su propia clave comercial como URI en lugar de la proporcionada por Adobe.

Utilice una clave personalizada solo para los recursos **de perfil de nivel** superior. Las direcciones URL son devueltas por la API y nunca las debe crear usted mismo.

<br/>

***Solicitud de muestra***

Para recuperar las suscripciones de un perfil mediante una clave personalizada, realice una operación de GET en la clave personalizada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Realice una solicitud de GET en la URL de suscripciones devuelta.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de suscripciones para el perfil.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```

---
solution: Campaign Standard
product: campaign
title: Lectura obligatoria
description: Lectura obligatoria antes de usar API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# Lectura obligatoria {#must-read}

## Requisitos técnicos

* Las API de Adobe Campaign deben usarse solo de servidor a servidor.
* Compruebe siempre con el contacto técnico de su Adobe si el caso de uso que desea implementar está alineado con la escala permitida por las API de Adobe Campaign.
* Para configurar un acceso de Adobe IO se necesitan permisos específicos, póngase en contacto con el servicio de asistencia técnica de Adobe si tiene algún problema.

## Representación de recursos

Todos los recursos de API están disponibles en **JSON** con una extensión URL o dentro de un encabezado de aceptación HTTP:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Sin extensión en la URL, el formato **json es el predeterminado** para el tipo de contenido.

<br/>

***ejemplo de solicitud***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Clave principal y direcciones URL

* No intente crear una URL por su cuenta. La API devuelve todas las direcciones URL. Sin embargo, es posible crear una URL basada en el nombre de recurso de nivel superior.

* Los valores de clave principal automática (PKey) que ilustran los ejemplos no están pensados para funcionar en otra implementación específica. Son producidos por la API de Adobe Campaign.

* Los valores de clave principal automática generados por Adobe Campaign nunca se deben almacenar en una base de datos o sitio web externos. Debe generar campos clave específicos en la definición de la base de datos y utilizarlos durante los desarrollos.

## Claves personalizadas {#custom-keys}

Si el recurso de perfil se ha ampliado con un campo de clave personalizada, puede utilizar este campo como clave en lugar de la clave principal automática generada por Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Las claves personalizadas no se pueden modificar con una operación de PATCH si el valor de clave es diferente de la clave de origen o si está utilizando su propia clave comercial como URI en lugar de la proporcionada por Adobe.

Utilice una clave personalizada solo para **recursos de perfil de nivel superior**. La API devuelve las direcciones URL, que usted mismo nunca debe crear.

<br/>

***Solicitud de ejemplo***

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

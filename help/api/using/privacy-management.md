---
title: Administración de privacidad
description: Más información sobre la administración de la privacidad con las API
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Administración de privacidad {#privacy-management}

Las API de Campaign Standard ofrecen funciones que permiten el proceso automático de solicitudes relacionadas con regulaciones de privacidad como GDPR y CCPA.

Las acciones que puede realizar son las siguientes:

* Crear una nueva solicitud de privacidad,
* Monitorear una solicitud de privacidad,
* Recuperar un archivo de datos de privacidad,
* Administre el estado de exclusión de CCPA de un perfil.

El extremo de la API de privacidad es **/privacy/privacyTool**. La descripción del recurso PrivacyTool y los filtros asociados están disponibles en los metadatos del recurso. Consulte Mecanismo [de metadatos](../../api/using/metadata-mechanism.md).

La exclusión de CCPA se administra mediante el atributo de perfil **ccpaOptOut** .

Para obtener más información sobre Adobe Campaign Standard y la conformidad con la privacidad, consulte la documentación [](https://helpx.adobe.com/campaign/kb/acs-privacy.html)dedicada.

## Creación de una solicitud de privacidad {#creating-a-privacy-request}

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) es el método que debe utilizar para todas las solicitudes de acceso y eliminación. A partir de la versión 19.4, el uso de la API de campaña y la interfaz para acceder y eliminar solicitudes está en desuso. Para obtener más información sobre las funciones obsoletas y eliminadas de Campaign Standard, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Las solicitudes de privacidad se crean mediante una solicitud **POST** .

Antes de crear solicitudes, debe definir el espacio de nombres que utilizará. Para obtener más información sobre esto, consulte la documentación [de administración de](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacidad.

La carga útil debe contener los siguientes parámetros:

* **name**: un nombre interno único
* **namespace**: el nombre de espacio de nombres configurado en la interfaz de Campaign Standard
* **validationValue**: el valor de reconciliación basado en la clave de reconciliación definida en el espacio de nombres
* **label**: la etiqueta de solicitud
* **type**: tipo de solicitud. Los valores aceptados son "access" o "delete".
* **reglamento**: tipo de regulación. Ejemplo: "RGPD", "CCPA". Este parámetro es obligatorio y está disponible a partir de la versión 19.4 de Campaign Standard. Si está en una versión anterior, no necesita agregarla a la carga útil.

<br/>

***Solicitud de muestra***

Esta solicitud POST crea una solicitud de privacidad basada en una clave de reconciliación de correo electrónico definida en el espacio de nombres AMCDS2:

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Respuesta a la solicitud POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```

## Supervisión de una solicitud de privacidad

Puede supervisar la información sobre una solicitud de privacidad creada mediante una solicitud **GET** .

La descripción de la lista de estado está disponible en la documentación [de administración de](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacidad.

<br/>

***Solicitud de muestra***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Respuesta a la solicitud GET.

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## Recuperación de un archivo de datos de privacidad

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) es el método que debe utilizar para todas las solicitudes de acceso y eliminación. A partir de la versión 19.4, el uso de la API de campaña y la interfaz para acceder y eliminar solicitudes está en desuso. Para obtener más información sobre las funciones obsoletas y eliminadas de Campaign Standard, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Para recuperar el archivo que contiene toda la información asociada a un valor de reconciliación, siga este procedimiento de tres pasos:

1. Realice una solicitud **POST** para crear una nueva solicitud con el atributo **type="access"**, consulte [Creación de una nueva solicitud](#creating-a-privacy-request)de privacidad.

1. Realice una solicitud **GET** para recuperar información sobre la solicitud.

1. Recupere el archivo de datos realizando una solicitud **POST** en la URL **privacyRequestData** devuelta, con el nombre interno de la solicitud de privacidad dentro de la carga útil. Por ejemplo: {"name":"PT17"}.

<br/>

***Solicitud de muestra***

Cree una solicitud de privacidad con el atributo type="access".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"access"
}
```

<!-- + réponse -->

Realice una solicitud GET para recuperar información sobre la solicitud.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Devuelve el atributo privacyRequestData con una dirección URL asociada.

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

Realice una solicitud POST en la URL privacyRequestData, con el nombre interno de la solicitud dentro de la carga útil.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

Devuelve el contenido del archivo.

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## Administración de la exclusión de CCPA

El estado de exclusión de CCPA de un perfil se puede supervisar y administrar usando el atributo de perfil **ccpaOptOut** y los valores "true" o "false":

`"ccpaOptOut": <value>`

* **true**:  prohíbe la venta de información personal.
* **false**: autoriza la venta de información personal.

>[!CAUTION]
>
>El atributo de exclusión de CCPA solo está disponible a partir de la versión 19.4. Para los entornos 19.3, debe ampliar el recurso Perfiles y agregar un campo booleano. Este campo se agregará a la API con la etiqueta seleccionada. Le sugerimos que utilice "Opción de exclusión para CCPA".
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Solicitudes de muestra***

* Ejemplo de solicitud GET para recuperar el estado de exclusión de CCPA de un perfil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Respuesta a la solicitud GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Ejemplo de solicitud POST para marcar un perfil para la exclusión de CCPA.

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

   Respuesta a la solicitud GET.

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

* Ejemplo de solicitud de PARCH para actualizar un perfil para la exclusión de CCPA.

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

   Respuesta a la solicitud GET.

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

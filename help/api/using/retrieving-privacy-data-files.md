---
title: Recuperación de archivos de datos de privacidad
description: Obtenga información sobre cómo recuperar archivos de datos de privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: df06cb86-dba2-41e4-81d0-66f3a86e47bd
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%

---

# Recuperación de archivos de datos de privacidad {#retrieving-privacy-data-files}

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) es el método que debería usar para todas las solicitudes de acceso y eliminación. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Para recuperar el archivo que contiene toda la información asociada a un valor de reconciliación, siga este procedimiento de tres pasos:

1. Realice una solicitud de **POST** para crear una nueva solicitud con el atributo **type=&quot;access&quot;**; consulte [Creación de una nueva solicitud de privacidad](../../api/using/creating-a-privacy-request.md).

1. Realice una solicitud **GET** para recuperar información sobre la solicitud.

1. Recupere el archivo de datos realizando una solicitud **POST** en la dirección URL **privacyRequestData** devuelta, con el nombre interno de la solicitud de privacidad dentro de la carga. Por ejemplo: {&quot;name&quot;:&quot;PT17&quot;}.

<br/>

***Solicitud de muestra***

Cree una solicitud de privacidad con el atributo type=&quot;access&quot;.

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

Realice una solicitud de GET para recuperar información sobre la solicitud.

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

Realice una solicitud del POST en la URL privacyRequestData, con el nombre interno de la solicitud dentro de la carga útil.

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

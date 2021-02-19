---
solution: Campaign Standard
product: campaign
title: Creación de una solicitud de privacidad
description: Aprenda a crear una solicitud de privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 14%

---


# Creación de una solicitud de privacidad {#creating-a-privacy-request}

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) es el método que debe utilizar para todas las solicitudes de acceso y eliminación. A partir de la versión 19.4, el uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedarán obsoletas. Para obtener más información sobre las funciones eliminadas y obsoletas del Campaign Standard, consulte [esta página](../../rn/using/deprecated-features.md).

Las solicitudes de privacidad se crean mediante una solicitud **POST**.

Antes de crear solicitudes, debe definir la Área de nombres que utilizará. Para obtener más información sobre esto, consulte la [documentación de administración de privacidad](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

La carga útil debe contener los siguientes parámetros:

* **name**: un nombre interno único
* **Área de nombres**: el nombre de Área de nombres configurado en la interfaz de Campaign Standard
* **validationValue**: el valor de reconciliación basado en la clave de reconciliación definida en la Área de nombres
* **label**: la etiqueta de solicitud
* **type**: tipo de solicitud. Los valores aceptados son &quot;access&quot; o &quot;delete&quot;.
* **reglamento**: tipo de regulación. Ejemplo: &quot;RGPD&quot;, &quot;CCPA&quot;. Este parámetro es obligatorio y está disponible a partir de la versión 19.4 de Campaign Standard. Si está en una versión anterior, no necesita agregarla a la carga útil.

<br/>

***Solicitud de muestra***

Esta solicitud de POST crea una solicitud de privacidad basada en una clave de reconciliación de correo electrónico definida en la Área de nombres AMCDS2:

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

Respuesta a la solicitud del POST.

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

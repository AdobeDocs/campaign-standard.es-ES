---
title: Creación de una solicitud de privacidad
description: Aprenda a crear una solicitud de privacidad con API
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Creación de una solicitud de privacidad {#creating-a-privacy-request}

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

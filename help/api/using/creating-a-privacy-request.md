---
title: Creación de una solicitud de privacidad
description: Obtenga información sobre cómo crear una solicitud de privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: e41667405b54a7ed0e02889e3002807e4bfd3a05
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Creación de una solicitud de privacidad {#creating-a-privacy-request}

>[!CAUTION]
>
>La variable [Servicio principal de privacidad](https://adobe.io/apis/cloudplatform/gdpr.html) La integración es el método que debe utilizar para todas las solicitudes de acceso y eliminación. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Las solicitudes de privacidad se crean mediante un **POST** solicitud.

Antes de crear solicitudes, debe definir el espacio de nombres que va a utilizar. Para obtener más información, consulte [Documentación de administración de la privacidad](../../start/using/privacy-requests.md).

La carga útil debe contener los siguientes parámetros:

* **name**: un nombre interno único
* **namespace**: el nombre de área de nombres configurado en la interfaz de Campaign Standard
* **reconciliationValue**: el valor de reconciliación basado en la clave de reconciliación definida en el espacio de nombres
* **label**: la etiqueta de solicitud
* **type**: el tipo de solicitud. Los valores aceptados son &quot;access&quot; o &quot;delete&quot;.
* **regulación**: el tipo de regulación. Ejemplo: &quot;RGPD&quot;, &quot;CCPA&quot;. Este parámetro es obligatorio y está disponible a partir de la versión 19.4 del Campaign Standard. Si se encuentra en una compilación anterior, no es necesario agregarla a la carga útil.

<br/>

***Solicitud de ejemplo***

Esta solicitud de POST crea una solicitud de privacidad basada en una clave de reconciliación de correo electrónico definida en el área de nombres AMCDS2:

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

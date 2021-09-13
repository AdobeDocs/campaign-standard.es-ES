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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 22%

---

# Creación de una solicitud de privacidad {#creating-a-privacy-request}

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) es el método que debe utilizar para todas las solicitudes de acceso y eliminación. A partir de la versión 19.4, el uso de la API y de la interfaz de Campaign para las solicitudes de acceso y eliminación quedarán obsoletas. Para obtener más información sobre las funciones obsoletas y eliminadas de Campaign Standard, consulte [esta página](../../rn/using/deprecated-features.md).

Las solicitudes de privacidad se crean mediante una solicitud **POST**.

Antes de crear solicitudes, debe definir el espacio de nombres que va a utilizar. Para obtener más información, consulte la [documentación de administración de privacidad](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

La carga útil debe contener los siguientes parámetros:

* **nombre**: un nombre interno único
* **espacio de nombres**: el nombre de área de nombres configurado en la interfaz de Campaign Standard
* **reconciliationValue**: el valor de reconciliación basado en la clave de reconciliación definida en el espacio de nombres
* **etiqueta**: la etiqueta de solicitud
* **tipo**: el tipo de solicitud. Los valores aceptados son &quot;access&quot; o &quot;delete&quot;.
* **reglamento**: el tipo de regulación. Ejemplo: &quot;RGPD&quot;, &quot;CCPA&quot;. Este parámetro es obligatorio y está disponible a partir de la versión 19.4 del Campaign Standard. Si se encuentra en una compilación anterior, no es necesario agregarla a la carga útil.

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

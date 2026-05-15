---
title: Creación de una solicitud de privacidad
description: Obtenga información sobre cómo crear una solicitud de privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
TQID: https://experienceleague.adobe.com/KInaFaQrwA5FKro44yFABqmDDvefY5mhJIl2OtBCrFc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 179
ht-degree: 4%

---

# Creación de una solicitud de privacidad {#creating-a-privacy-request}

>[!CAUTION]
>
>La integración de [Privacy Core Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) es el método que debería usar para todas las solicitudes de acceso y eliminación. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Las solicitudes de privacidad se crean mediante una solicitud **POST**.

Antes de crear solicitudes de, debe definir el área de nombres que utilizará. Para obtener más información, consulte la [documentación de administración de privacidad](../../start/using/privacy-requests.md).

La carga útil debe contener los siguientes parámetros:

* **nombre**: un nombre interno único
* **namespace**: el nombre del área de nombres configurado en la interfaz de Campaign Standard
* **reconciliationValue**: el valor de reconciliación basado en la clave de reconciliación definida en el área de nombres
* **etiqueta**: la etiqueta de solicitud
* **tipo**: el tipo de solicitud. Los valores aceptados son &quot;access&quot; o &quot;delete&quot;.
* **regulación**: el tipo de regulación. Ejemplo: &quot;RGPD&quot;, &quot;CCPA&quot;. Este parámetro es obligatorio y está disponible a partir de la versión 19.4 de Campaign Standard. Si tiene una versión anterior, no es necesario que la añada a la carga útil.

<br/>

***Solicitud de muestra***

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

Respuesta a la solicitud de POST.

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

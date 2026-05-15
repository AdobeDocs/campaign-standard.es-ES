---
title: Supervisión de una solicitud de privacidad
description: Obtenga información sobre cómo supervisar una solicitud de privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 63864f0f-2c22-4a65-86ae-21897031f30a
TQID: https://experienceleague.adobe.com/VO2XcUgDBCaGtqXji550j770iijK8lr0SSw5J8VQtgk
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
source-wordcount: 48
ht-degree: 16%

---

# Supervisión de una solicitud de privacidad {#monitoring-a-privacy-request}

Puede supervisar la información sobre una solicitud de privacidad creada con una solicitud de **GET**.

La descripción de la lista de estado está disponible en [Documentación de administración de privacidad](../../start/using/privacy-requests.md).

<br/>

***Solicitud de muestra***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Respuesta a la solicitud de GET.

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

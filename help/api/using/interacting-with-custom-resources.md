---
title: Interacción con recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%
---
# Interacción con recursos personalizados {#interacting-with-custom-resources}

El extremo **/customResources** le permite exponer los recursos personalizados de Campaign en REST. En función de esta API, hay disponible una integración entre entidades personalizadas y extremos externos.

El extremo /customResources tiene exactamente el mismo comportamiento que el extremo /profileAndServices.

Los recursos personalizados que se exponen dentro de esta API son los siguientes:

* todas las entidades que no se exponen en /profileAndServicesExt
* todas las entidades que no están vinculadas al perfil y, para estas entidades, sus hijos y nietos.
* de forma predeterminada, todas las entidades que no están vinculadas a nada, y sus hijos y nietos.

>[!NOTE]
>Los recursos personalizados disponibles en /profileAndServicesExt no se exponen en la API /customResources.


A continuación, se muestra un ejemplo para recuperar los metadatos de un recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para realizar una creación, actualización o eliminación, se utilizan GET, POST, PATCH y DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>El extremo de la API de privacidad y los flujos de trabajo (/privacy/privacyTool) no administran los recursos personalizados que no están vinculados a la entidad del perfil.
>Tendrá la responsabilidad de administrar y limpiar cualquier PII de estos recursos personalizados. Para obtener más información sobre la herramienta de privacidad, [haga clic aquí](../../api/using/creating-a-privacy-request.md).

---
title: Uso de recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# Uso de recursos personalizados {#interacting-with-custom-resources}

El **/customResources** Este punto de conexión le permite exponer los recursos personalizados de Campaign en REST. En función de esta API, hay disponible una integración entre entidades personalizadas y extremos externos.

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

Para realizar una creación, actualización o eliminación, se utilizan el GET, el POST, el PATCH y el DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>El extremo de la API de privacidad y los flujos de trabajo (/privacy/privacyTool) no administran los recursos personalizados que no están vinculados a la entidad del perfil.
>Tendrá la responsabilidad de administrar y limpiar cualquier PII de estos recursos personalizados. Para obtener más información sobre la herramienta de privacidad, [haga clic aquí](../../api/using/creating-a-privacy-request.md).

---
title: Recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
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
source-git-commit: 5c4d3fc9853bf9bad4efcefaea242fecc9c4c61f

---


# Interactuar con recursos personalizados {#interacting-with-custom-resources}

El extremo **/customResources** permite exponer las entidades personalizadas ACS en REST. En función de esta API, hay disponible una integración entre entidades personalizadas y extremos externos.

El /customResources tiene exactamente el mismo comportamiento que el extremo /profileAndServices.

Las entidades personalizadas que se exponen en esta API son:

* todas las entidades vinculadas a la entidad de perfil
* todas las entidades vinculadas a los elementos secundarios de la entidad de perfil
* todas las entidades que no están vinculadas a perfiles y, para estas entidades, sus hijos y nietos.

>[!NOTE]
>Las entidades personalizadas disponibles en /profileAndServicesExt no están expuestas en la API /customResources.

A continuación se muestra un ejemplo para recuperar los metadatos de un recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para realizar una creación, actualización o eliminación, se utiliza GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>El extremo de la API de privacidad y los flujos de trabajo (/privacy/privacyTool) no están administrando los recursos personalizados que no están vinculados a la entidad de perfil.
>Tendrá la responsabilidad de administrar y limpiar cualquier PII para estos recursos personalizados. Para obtener más información sobre la herramienta de privacidad, [haga clic aquí](../../api/using/privacy-management.md).
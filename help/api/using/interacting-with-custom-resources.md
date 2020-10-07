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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---


# Uso de recursos personalizados {#interacting-with-custom-resources}

El extremo **/customResources** permite exponer los recursos personalizados de ACS en REST. En función de esta API, hay disponible una integración entre entidades personalizadas y extremos externos.

El extremo /customResources tiene exactamente el mismo comportamiento que el extremo /profileAndServices.

Los recursos personalizados que se exponen en esta API son:

* todas las entidades vinculadas a la entidad perfil
* todas las entidades vinculadas a los hijos de la entidad perfil
* todas las entidades que no están vinculadas al perfil y, para estas entidades, sus hijos y nietos.

>[!NOTE]
>Los recursos personalizados disponibles en /profileAndServicesExt no están expuestos en la API /customResources.

A continuación se muestra un ejemplo para recuperar los metadatos de un recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para realizar una creación, actualización o eliminación, se utiliza el GET, el POST, el PATCH y el DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Los flujos de trabajo y el punto final de la API de privacidad (/privacy/privacyTool) no están administrando los recursos personalizados que no están vinculados a la entidad perfil.
>Tendrá la responsabilidad de administrar y limpiar cualquier PII para estos recursos personalizados. Para obtener más información sobre la herramienta de privacidad, [haga clic aquí](../../api/using/creating-a-privacy-request.md).


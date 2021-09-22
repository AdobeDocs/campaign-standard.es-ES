---
title: Recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# Uso de recursos personalizados {#interacting-with-custom-resources}

El extremo **/customResources** le permite exponer los recursos personalizados de Campaign en REST. En función de esta API, hay disponible una integración entre entidades personalizadas y extremos externos.

El extremo /customResources tiene exactamente el mismo comportamiento que el extremo /profileAndServices.

Los recursos personalizados que se exponen dentro de esta API son:

* todas las entidades que no están expuestas en /profileAndServicesExt
* todas las entidades que no están vinculadas a perfiles y, para estas entidades, sus hijos y nietos.
* de forma predeterminada, todas las entidades que no están vinculadas a nada, así como sus hijos y nietos.

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
>El extremo y los flujos de trabajo de la API de privacidad (/privacy/privacyTool) no están administrando los recursos personalizados que no están vinculados a la entidad de perfil.
>Usted tendrá la responsabilidad de administrar y limpiar cualquier PII para estos recursos personalizados. Para obtener más información sobre la herramienta de privacidad, [haga clic aquí](../../api/using/creating-a-privacy-request.md).

---
title: "Paso 3: Verificar la extensión"
description: Obtenga información sobre cómo acceder al campo ampliado con la API de REST.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---

# Paso 3: Verificar la extensión{#step-verify-the-extension}

1. Realice una operación de GET en los metadatos de la API de extensión de perfiles y servicios para comprobar si el campo agregado en el recurso personalizado de perfiles ya está disponible.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Devuelve:

   ![](assets/extendpandsapiview.png)

   El campo ya está disponible para nuevos desarrollos e integraciones.

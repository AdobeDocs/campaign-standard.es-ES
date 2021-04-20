---
solution: Campaign Standard
product: campaign
title: '"Paso 3: Verificar la extensión"'
description: Obtenga información sobre cómo acceder al campo ampliado con la API de Rest.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# Paso 3: Verificar la extensión{#step-verify-the-extension}

1. Realice una operación de GET en los metadatos de la API de extensión de perfiles y servicios para comprobar si el campo añadido en el recurso personalizado Perfiles ya está disponible.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Devuelve:

   ![](assets/extendpandsapiview.png)

   El campo ya está disponible para más desarrollos e integraciones.


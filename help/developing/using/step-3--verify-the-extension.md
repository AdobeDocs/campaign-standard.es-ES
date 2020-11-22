---
solution: Campaign Standard
product: campaign
title: '"Paso 3: Verificar la extensión"'
description: Obtenga información sobre cómo acceder al campo extendido con la API de descanso.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# Paso 3: Verificar la extensión{#step-verify-the-extension}

1. Realice una operación de GET en los metadatos de la API de extensión de Perfiles y servicios para comprobar si el campo agregado en el recurso personalizado de Perfiles ya está disponible.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Devuelve:

   ![](assets/extendpandsapiview.png)

   El campo está ahora disponible para nuevos desarrollos e integraciones.


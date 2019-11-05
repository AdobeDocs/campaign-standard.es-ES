---
title: '"Paso 3: Verificar la extensión"'
description: Obtenga información sobre cómo acceder al campo extendido con la API de descanso.
page-status-flag: nunca activado
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: desarrollo
content-type: referencia
topic-tags: use-case—extension-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Paso 3: Verificar la extensión{#step-verify-the-extension}

1. Realice una operación GET en los metadatos de Profiles &amp; Services Extension API para comprobar si el campo agregado en el recurso personalizado Perfiles ya está disponible.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Devuelve:

   ![](assets/extendpandsapiview.png)

   El campo está ahora disponible para nuevos desarrollos e integraciones.


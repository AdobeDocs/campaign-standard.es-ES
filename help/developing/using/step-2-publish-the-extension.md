---
title: "Paso 2: Publish con la extensión"
description: Obtenga información sobre cómo publicar la extensión en Campaign Standard. Parte 2 de una serie.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 25%

---

# Paso 2: Publicar la extensión{#step-publish-the-extension}

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Publication]**.
1. Haga clic en el botón **[!UICONTROL Prepare Publication]**.
1. Seleccione la opción **[!UICONTROL Create the Profiles & Services Ext API]**.

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >Si la API ya se ha publicado (es decir, si ya ha marcado esta opción una vez, para este recurso u otro), se fuerza la actualización de la API.

1. Seleccione la pestaña **[!UICONTROL Profiles & Services API Preview]**.

   Esto le mostrará los cambios que la publicación de la API aplicará a la versión actual de la API profilesAndServicesExt.

   En este caso, el campo Código de promoción (ID: cusBrand) se inserta en la API.

   ![](assets/extendpandsapi_diff.png)

1. Haga clic en el botón **[!UICONTROL Publish]**.

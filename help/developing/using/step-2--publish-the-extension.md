---
solution: Campaign Standard
product: campaign
title: '"Paso 2: Publicar la extensión"'
description: Obtenga información sobre cómo publicar la extensión en Campaign Standard. Parte 2 de una serie.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Modelo de datos
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
source-git-commit: d3482dfad245807aedee6deb36fd67e43c7a66b9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 28%

---

# Paso 2: Publicar la extensión{#step-publish-the-extension}

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Publication]**.
1. Haga clic en el botón **[!UICONTROL Prepare Publication]**.
1. Seleccione la opción **[!UICONTROL Create the Profiles & Services Ext API]**.

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >Si la API ya se ha publicado (es decir, si ya ha marcado esta opción una vez, para este recurso u otro recurso), se fuerza la actualización de la API.

1. Seleccione la pestaña **[!UICONTROL Profiles & Services API Preview]**.

   Esto le mostrará los cambios que la publicación de la API aplicará a la versión actual de la API profilesAndServicesExt.

   Aquí, el campo Código promocional (ID: cusBrand) se insertará en la API.

   ![](assets/extendpandsapi_diff.png)

1. Haga clic en el botón **[!UICONTROL Publish]**.

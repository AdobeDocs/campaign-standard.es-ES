---
title: 'Paso 2: Publicar la extensión'
description: Obtenga información sobre cómo publicar la extensión en Campaign Standard. Parte 2 de una serie.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
TQID: 'https://experienceleague.adobe.com/BPvEkhFMAe2Xiwllo4RwTzGeXo-IPxYiEp-1sGUzK-A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 30%
---
# Paso 2: Publicar la extensión{#step-publish-the-extension}

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Publication]**.
1. Haga clic en el botón **[!UICONTROL Prepare Publication]**.
1. Seleccione la opción **[!UICONTROL Create the Profiles & Services Ext API]**.

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >Si la API ya se ha publicado (es decir, si ya ha marcado esta opción una vez, para este recurso u otro), se fuerza la actualización de la API.

1. Haga clic en la pestaña **[!UICONTROL Profiles & Services API Preview]**.

   Esto le mostrará los cambios que la publicación de la API aplicará a la versión actual de la API profilesAndServicesExt.

   En este caso, el campo Código de promoción (ID: cusBrand) se inserta en la API.

   ![](assets/extendpandsapi_diff.png)

1. Haga clic en el botón **[!UICONTROL Publish]**.

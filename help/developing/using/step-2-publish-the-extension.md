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
TQID: https://experienceleague.adobe.com/BPvEkhFMAe2Xiwllo4RwTzGeXo-IPxYiEp-1sGUzK-A
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 109
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

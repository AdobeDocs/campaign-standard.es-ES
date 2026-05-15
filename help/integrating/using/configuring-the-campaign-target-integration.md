---
title: Configuración de la integración de Campaign-Target
description: Obtenga información sobre cómo configurar la integración de Adobe Target para que empiece a utilizar contenido dinámico en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 19%

---

# Configuración de la integración de Campaign-Target{#configuring-the-campaign-target-integration}

La integración entre Adobe Campaign y Adobe Target permite insertar contenido dinámico en la entrega.

Primero es necesario configurar Adobe Campaign para utilizar las funcionalidades de integración con Adobe Target y el administrador funcional debe administrarlo.

Se necesitan los siguientes elementos para este procedimiento:

* Un usuario de Adobe Experience Cloud
* Un usuario de Adobe Target
* Un “rawbox” de Adobe Target determinada para establecer la conexión con Adobe Campaign

1. En el menú avanzado, en el logotipo de Adobe Campaign en la esquina superior izquierda, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Para configurar las opciones del servidor y el inquilino de Adobe Target, rellene los campos siguientes según corresponda:

   * **[!UICONTROL TNT_TenantName]**: nombre del usuario de Adobe Target. Este valor corresponde al nombre de **[!UICONTROL Client]** de Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**: servidor de Adobe Target utilizado para la integración. Esta opción ya se proporciona de forma predeterminada. Este valor corresponde al Adobe Target **[!UICONTROL Server Domain]**, seguido del valor **/m2**. Por ejemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Los usuarios ahora pueden añadir imágenes dinámicas en una entrega con Adobe Target.

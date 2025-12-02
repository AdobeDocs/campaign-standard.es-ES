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
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 18%

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

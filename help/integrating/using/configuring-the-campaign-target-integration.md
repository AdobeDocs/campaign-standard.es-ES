---
title: Configuración de la integración de Target-Target
seo-title: Configuración de la integración de Target-Target
description: Configuración de la integración de Target-Target
seo-description: Aprenda a configurar la integración de Adobe Target para empezar a utilizar contenido dinámico en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 0 df 5701 c-dc 26-4 c 30-9 af 9-ebf 92815 d 90 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y objetivo
discoiquuid: f 7 fb 2084-dd 6 f -4 aa 2-940 f-e 48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

La integración entre Adobe Campaign y Adobe Target permite insertar contenido dinámico en la entrega.

Primero se necesita una configuración en Adobe Campaign para utilizar las funcionalidades de integración con Adobe Target y debe gestionarla el administrador funcional.

Para este procedimiento se necesitan los siguientes elementos:

* Un inquilino de Adobe Experience Cloud
* Un inquilino de Adobe Target
* Un rawbox de Adobe Target especificado para establecer la conexión con Adobe Campaign

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Para configurar las opciones de servidor y de inquilino de Adobe Target, rellene los campos siguientes en consecuencia:

   * **[!UICONTROL TNT_TenantName]**: nombre del inquilino de Adobe Target. This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor de Adobe Target utilizado para la integración. Esta opción ya se proporciona de forma predeterminada. This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Ahora los usuarios pueden añadir imágenes dinámicas en una entrega con Adobe Target.

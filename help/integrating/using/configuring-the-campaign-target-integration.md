---
title: Configuración de la integración de Campaign-Target
description: Obtenga información sobre cómo configurar la integración de Adobe Target para empezar a utilizar contenido dinámico en Adobe Campaign.
page-status-flag: nunca activado
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y objetivo
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configuración de la integración de Campaign-Target{#configuring-the-campaign-target-integration}

La integración entre Adobe Campaign y Adobe Target le permite insertar contenido dinámico en la entrega.

En primer lugar, Adobe Campaign necesita una configuración para utilizar las funcionalidades de integración con Adobe Target y debe administrarla el administrador funcional.

Se necesitan los siguientes elementos para este procedimiento:

* Un inquilino de Adobe Experience Cloud
* Un inquilino de Adobe Target
* Un “rawbox” de Adobe Target determinada para establecer la conexión con Adobe Campaign

1. En el menú avanzado, a través del logotipo de Adobe Campaign en la esquina superior izquierda, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Para configurar las opciones de servidor e inquilino para Adobe Target, rellene los siguientes campos de forma correspondiente:

   * **[!UICONTROL TNT_TenantName]**:: nombre del inquilino de Adobe Target. This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**:: Servidor de Adobe Target utilizado para la integración. Esta opción ya se proporciona de forma predeterminada. Este valor corresponde a Adobe Target **[!UICONTROL Server Domain]**, seguido del valor **/m2** .  Por ejemplo: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Los usuarios ahora pueden agregar imágenes dinámicas en una entrega con Adobe Target.

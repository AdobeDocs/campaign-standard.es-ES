---
solution: Campaign Standard
product: campaign
title: Configuración de la integración de Campaign-Target
description: Obtenga información sobre cómo configurar la integración de Adobe Target en inicio mediante contenido dinámico en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 18%

---


# Configuración de la integración de Campaign-Target{#configuring-the-campaign-target-integration}

La integración entre Adobe Campaign y Adobe Target permite insertar contenido dinámico en el envío.

En primer lugar, Adobe Campaign necesita una configuración para utilizar las funcionalidades de integración con Adobe Target y debe ser administrada por el administrador funcional.

Se necesitan los siguientes elementos para este procedimiento:

* Un inquilino de Adobe Experience Cloud
* Un inquilino de Adobe Target
* Un “rawbox” de Adobe Target determinada para establecer la conexión con Adobe Campaign

1. En el menú avanzado, a través del logotipo de Adobe Campaign en la esquina superior izquierda, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Para configurar las opciones de servidor e inquilino para Adobe Target, rellene los campos siguientes en consecuencia:

   * **[!UICONTROL TNT_TenantName]**:: nombre del inquilino de Adobe Target. Este valor corresponde al nombre de **[!UICONTROL Client]** de Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**:: Servidor Adobe Target utilizado para la integración. Esta opción ya se proporciona de forma predeterminada. Este valor corresponde al valor de Adobe Target **[!UICONTROL Server Domain]**, seguido del valor **/m2**. Por ejemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Los usuarios ahora pueden agregar imágenes dinámicas en un envío con Adobe Target.

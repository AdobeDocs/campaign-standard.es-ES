---
title: Configuración de la integración de Campaign-Target
description: Aprenda a configurar la integración de Adobe Target para que empiece a usar contenido dinámico en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 18%

---

# Configuración de la integración de Campaign-Target{#configuring-the-campaign-target-integration}

La integración entre Adobe Campaign y Adobe Target permite insertar contenido dinámico en el envío.

Primero se necesita una configuración en Adobe Campaign para utilizar las funcionalidades de integración con Adobe Target y el administrador funcional debe administrarla.

Se necesitan los siguientes elementos para este procedimiento:

* Un inquilino de Adobe Experience Cloud
* Un inquilino de Adobe Target
* Un “rawbox” de Adobe Target determinada para establecer la conexión con Adobe Campaign

1. En el menú avanzado, en el logotipo de Adobe Campaign, en la esquina superior izquierda, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Para configurar las opciones del servidor y del inquilino para Adobe Target, rellene los siguientes campos como corresponda:

   * **[!UICONTROL TNT_TenantName]**: nombre del inquilino de Adobe Target. Este valor corresponde al nombre de **[!UICONTROL Client]** de Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor de Adobe Target utilizado para la integración. Esta opción ya se proporciona de forma predeterminada. Este valor corresponde a Adobe Target **[!UICONTROL Server Domain]** y, a continuación, **/m2** valor. Por ejemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Los usuarios ahora pueden agregar imágenes dinámicas en un envío con Adobe Target.

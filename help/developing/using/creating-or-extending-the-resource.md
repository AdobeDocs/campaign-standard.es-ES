---
solution: Campaign Standard
product: campaign
title: Creación o ampliación del recurso
description: Descubra cómo definir un recurso desde cero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---


# Creación o ampliación del recurso{#creating-or-extending-the-resource}

Los administradores pueden crear un nuevo recurso desde cero o crear una extensión de un recurso existente si necesita trabajar en datos que no forman parte del modelo de datos integrado.

Sólo se pueden ampliar los siguientes recursos integrados:

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Para crear o ampliar un recurso:

1. En **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, haga clic en el botón **[!UICONTROL Create]**.
1. Elija la acción que desee realizar:

   * **[!UICONTROL Create a new resource]**:: Introduzca los  **[!UICONTROL Label]** campos y  **[!UICONTROL ID]** campos. El campo **[!UICONTROL ID]** es obligatorio. Si deja vacío el campo Etiqueta, se completará automáticamente a partir del ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Utilice un máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**:: Seleccione el recurso que desee ampliar.

      ![](assets/schema_extension_10.png)

1. Haga clic **[!UICONTROL Create]** para crear el recurso, que luego tomará el estado **[!UICONTROL Draft]** en caso de nuevo recurso o el estado **[!UICONTROL Editing]** en caso de extensión.

El nuevo recurso se crea y ahora se puede configurar. Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura de datos del recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

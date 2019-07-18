---
title: Creación o ampliación del recurso
seo-title: Creación o ampliación del recurso
description: Creación o ampliación del recurso
seo-description: Descubra cómo definir un recurso desde cero.
page-status-flag: no activado nunca
uuid: 7 c 26 b 63 d -9587-472 b -804 f-cde 5 c 45 dfb 3 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 8 dc 45 c 37-6908-407 e -8 e 41-4 a 4188 cba 2 b 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Creating or extending the resource{#creating-or-extending-the-resource}

Los administradores pueden crear un nuevo recurso desde cero o crear una extensión de un recurso existente si necesita trabajar en datos que no forman parte del modelo de datos predeterminado.

Solo se pueden ampliar los siguientes recursos predeterminados:

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

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click the **[!UICONTROL Create]** button.
1. Elija la acción que desee realizar:

   * **[!UICONTROL Create a new resource]**: Introduzca los **[!UICONTROL Label]** campos y **[!UICONTROL ID]** los campos. The **[!UICONTROL ID]** field is mandatory. Si deja vacío el campo Etiqueta, se completará automáticamente desde el ID.

      ![](assets/schema_extension_2.png)

   * **[!UICONTROL Extend an existing resource]**: Seleccione el recurso que desee ampliar.

      ![](assets/schema_extension_10.png)

1. Click **[!UICONTROL Create]** to create the resource, which will then take on the **[!UICONTROL Draft]** status in case of new resource or the **[!UICONTROL Editing]** status in case of extension.

El nuevo recurso se crea y ahora se puede configurar. For more on resource configuration, refer to [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

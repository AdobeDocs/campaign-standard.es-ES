---
title: Creación o ampliación del recurso
description: Descubra cómo definir un recurso desde cero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---

# Creación o ampliación del recurso{#creating-or-extending-the-resource}

Los administradores pueden crear un nuevo recurso desde cero o crear una extensión de un recurso existente si necesita trabajar en datos que no forman parte del modelo de datos integrado.

Solo se pueden ampliar los siguientes recursos integrados:

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

1. Desde **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, haga clic en **[!UICONTROL Create]** botón.
1. Elija la acción que desea realizar:

   * **[!UICONTROL Create a new resource]**: introduzca el **[!UICONTROL Label]** y **[!UICONTROL ID]** campos. El campo **[!UICONTROL ID]** es obligatorio. Si deja vacío el campo Label, se rellenará automáticamente a partir del ID.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Utilice un máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: seleccione el recurso que desea ampliar.

     ![](assets/schema_extension_10.png)

1. Clic **[!UICONTROL Create]** para crear el recurso, que luego se encargará de lo siguiente **[!UICONTROL Draft]** estado en caso de un nuevo recurso o de la **[!UICONTROL Editing]** estado en caso de extensión.

El nuevo recurso se crea y ahora se puede configurar. Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura de datos del recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

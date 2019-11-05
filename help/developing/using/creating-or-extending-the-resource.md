---
title: Creación o ampliación del recurso
description: Descubra cómo definir un recurso desde cero.
page-status-flag: nunca activado
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: desarrollo
content-type: referencia
topic-tags: agregar o ampliar un recurso
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación o ampliación del recurso{#creating-or-extending-the-resource}

Los administradores pueden crear un nuevo recurso desde cero o crear una extensión de un recurso existente si necesita trabajar en datos que no forman parte del modelo de datos incorporado.

Sólo se pueden ampliar los siguientes recursos listos para usar:

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

1. En **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, haga clic en el **[!UICONTROL Create]** botón.
1. Elija la acción que desee realizar:

   * **[!UICONTROL Create a new resource]**:: Introduzca los campos **[!UICONTROL Label]** y **[!UICONTROL ID]** . El **[!UICONTROL ID]** campo es obligatorio. Si deja vacío el campo Etiqueta, se completará automáticamente a partir del ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Se recomienda utilizar un máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**:: Seleccione el recurso que desee ampliar.

      ![](assets/schema_extension_10.png)

1. Haga clic en **[!UICONTROL Create]** para crear el recurso, que luego tomará el **[!UICONTROL Draft]** estado en caso de nuevo recurso o el **[!UICONTROL Editing]** estado en caso de extensión.

El nuevo recurso se crea y ahora se puede configurar. Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura](../../developing/using/configuring-the-resource-s-data-structure.md)de datos del recurso.

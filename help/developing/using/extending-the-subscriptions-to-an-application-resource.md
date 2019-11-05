---
title: Ampliación de las suscripciones a un recurso de aplicación
description: null
page-status-flag: nunca activado
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: desarrollo
content-type: referencia
topic-tags: use-cases—extension-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Ampliación de las suscripciones a un recurso de aplicación{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-to-add-a-resource.md).

Este recurso se puede ampliar para recopilar datos que se van a enviar desde el dispositivo móvil a Adobe Campaign.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Custom resources]**.
1. Haga clic **[!UICONTROL Create]** y elija la **[!UICONTROL Extend an existing resource]** opción.
1. Seleccione el **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** recurso y haga clic en **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. En la **[!UICONTROL Fields]** categoría de la **[!UICONTROL Data structure]** ficha, defina los datos del cliente que desea recuperar de la aplicación móvil haciendo clic en el **[!UICONTROL Add field]** botón.

   >[!NOTE]
   >
   >Si está administrando varias aplicaciones móviles, se deben enumerar todos los campos utilizados por todas las aplicaciones. La llamada PII recopilada por iOS o Android define los campos que captura cada aplicación.

   ![](assets/in_app_personal_data.png)

1. Agregue un **[!UICONTROL Label]** y un **[!UICONTROL ID]** al nuevo campo. Seleccione el campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. En la **[!UICONTROL Link to profiles]** categoría, configure la clave de reconciliación utilizada para vincular los perfiles de la base de datos de Adobe Campaign a los suscriptores de las aplicaciones, como el correo electrónico.

   Tenga en cuenta que para los mensajes en la aplicación solo puede definir una clave de reconciliación para todas las aplicaciones móviles.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** y publique el recurso personalizado. Para obtener más información sobre la publicación de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).


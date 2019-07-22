---
title: Ampliar las suscripciones a un recurso de aplicación
seo-title: Ampliar las suscripciones a un recurso de aplicación
description: Ampliar las suscripciones a un recurso de aplicación
seo-description: null
page-status-flag: no activado nunca
uuid: 8879 b 427-b 31 b -4311-bf 54-258 a 91 b 1 fb 78
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: casos de uso—ampliación de recursos
discoiquuid: 59 faa 74 e -86 fc -42 d 3-90 da-f 48580 b 5 ec 13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 20b4d5dfb297cac4cd69fe6f945b4399abd7f06a

---


# Extending the subscriptions to an application resource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-to-add-a-resource.md).

Este recurso se puede ampliar para recopilar datos que se pretenden enviar desde el dispositivo móvil a Adobe Campaign.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. Click **[!UICONTROL Create]** and choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, define the customer data that you want to retrieve from your mobile application by clicking the **[!UICONTROL Add field]** button.

   >[!NOTE]
   >
   >Si está administrando varias aplicaciones móviles, deben aparecer todos los campos utilizados por todas las aplicaciones. La recopilación de PII de iOS o Android define los campos que captura cada aplicación.

   ![](assets/in_app_personal_data.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to your new field. Select your field's **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In the **[!UICONTROL Link to profiles]** category, configure the reconciliation key used to link the profiles from the Adobe Campaign database to your applications' subscribers, such as the email.

   Tenga en cuenta que, para los mensajes en la aplicación, solo puede definir una clave de reconciliación para todas las aplicaciones móviles.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** y publicar el recurso personalizado. For more information on custom resource publication, refer to this [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).


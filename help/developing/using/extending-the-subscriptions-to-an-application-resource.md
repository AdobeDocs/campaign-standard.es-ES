---
solution: Campaign Standard
product: campaign
title: Ampliación de las suscripciones a un recurso de aplicación
description: Obtenga información sobre cómo ampliar la suscripción a un recurso de aplicación
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Modelo de datos
role: Desarrollador
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 23%

---


# Ampliación de las suscripciones a un recurso de aplicación{#extending-the-subscriptions-to-an-application-resource}

En Adobe Campaign, los datos de atributos de perfil móviles enviados desde dispositivos móviles se almacenan en el recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que le permite definir los datos que desea recopilar de los suscriptores de las aplicaciones. Para obtener más información sobre los recursos personalizados, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

Este recurso se puede ampliar para recopilar los datos que se van a enviar desde el dispositivo móvil a Adobe Campaign.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Custom resources]**.
1. Haga clic en **[!UICONTROL Create]** y seleccione la opción **[!UICONTROL Extend an existing resource]**.
1. Seleccione el recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** y haga clic en **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. En la categoría **[!UICONTROL Fields]** de la pestaña **[!UICONTROL Data structure]**, defina los datos de cliente que desea recuperar de la aplicación móvil haciendo clic en el botón **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Si administra varias aplicaciones móviles, se deben enumerar todos los campos utilizados por todas las aplicaciones. La llamada PII recopilada por iOS o Android define qué campos captura cada aplicación.

   ![](assets/in_app_personal_data.png)

1. Agregue un **[!UICONTROL Label]** y un **[!UICONTROL ID]** al nuevo campo. Seleccione el **[!UICONTROL Type]** del campo.

   ![](assets/schema_extension_uc9.png)

1. En la categoría **[!UICONTROL Link to profiles]**, configure la clave de reconciliación utilizada para vincular los perfiles de la base de datos de Adobe Campaign a los suscriptores de las aplicaciones, como el correo electrónico.

   Tenga en cuenta que para los mensajes en la aplicación solo puede definir una clave de reconciliación para todas las aplicaciones móviles.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** y publique el recurso personalizado. Para obtener más información sobre la publicación de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).


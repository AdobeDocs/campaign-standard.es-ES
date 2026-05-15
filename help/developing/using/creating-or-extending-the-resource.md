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
TQID: https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
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

1. En **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, haga clic en el botón **[!UICONTROL Create]**.
1. Elija la acción que desea realizar:

   * **[!UICONTROL Create a new resource]**: escriba los campos **[!UICONTROL Label]** y **[!UICONTROL ID]**. El campo **[!UICONTROL ID]** es obligatorio. Si deja vacío el campo Label, se rellenará automáticamente a partir del ID.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Utilice un máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: seleccione el recurso que desea ampliar.

     ![](assets/schema_extension_10.png)

1. Haga clic en **[!UICONTROL Create]** para crear el recurso, que luego adoptará el estado **[!UICONTROL Draft]** en caso de que se cree un nuevo recurso o el estado **[!UICONTROL Editing]** en caso de que se produzca la extensión.

El nuevo recurso se crea y ahora se puede configurar. Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura de datos del recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

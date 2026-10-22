---
title: Personalización de las campañas con atributos de Adobe Experience Platform
description: Aprenda a personalizar sus campañas con atributos de Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%
---
# Personalización de las campañas con atributos de Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas funciones. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.
>
>Los canales **Push** y **en la aplicación** aún no están disponibles para la personalización mediante datos contextuales de Adobe Experience Platform.

Una vez que el flujo de trabajo esté configurado con una [audiencia de Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), puede personalizar mensajes con atributos de perfil que existan exclusivamente en el Experience Data Model (XDM).

Para ello, debe agregar estos atributos a la actividad **[!UICONTROL Read audience]**:

1. Abra la actividad **[!UICONTROL Read audience]**. En la ficha **[!UICONTROL Additional data]**, haga clic en el botón **[!UICONTROL Create element]**.

   Tenga en cuenta que la ficha **[!UICONTROL Additional data]** solo está disponible después de seleccionar una audiencia de Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Los tipos de datos de matriz y asignación no son compatibles con esta función. Además, solo se mostrarán en el selector los datos del esquema de unión.

1. Seleccione el campo XDM deseado de la lista y, a continuación, haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Haga clic en el botón **[!UICONTROL Add]** para agregarlo a la lista de datos adicionales.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita estos pasos para cada campo XDM que desee agregar al flujo de trabajo.

   >[!NOTE]
   >
   >Puede agregar un máximo de 20 campos XDM en una actividad **[!UICONTROL Read audience]**.

1. Una vez agregados todos los campos, haga clic en el botón **[!UICONTROL Confirm]** para guardar los cambios. Ahora están disponibles para personalizar las entregas.

Para obtener más información sobre cómo crear y personalizar envíos, consulte la documentación de Campaign Standard:

* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)
* [Personalización de entregas](../../designing/using/personalization.md)

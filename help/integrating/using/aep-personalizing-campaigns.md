---
title: Personalización de las campañas con atributos de Adobe Experience Platform
description: Obtenga información sobre cómo personalizar sus campañas con atributos de Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 9%

---

# Personalización de las campañas con atributos de Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Es necesario que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.
>
>**** Los  **Pushand In-** Appchannels aún no están disponibles para su personalización mediante datos contextuales de Adobe Experience Platform.

Una vez configurado el flujo de trabajo con una [audiencia de Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), puede personalizar los mensajes con atributos de perfil que existan exclusivamente en el Modelo de datos de experiencia (XDM).

Para ello, debe añadir estos atributos a la actividad **[!UICONTROL Read audience]** :

1. Abra la actividad **[!UICONTROL Read audience]**. En la pestaña **[!UICONTROL Additional data]**, haga clic en el botón **[!UICONTROL Create element]**.

   Tenga en cuenta que la pestaña **[!UICONTROL Additional data]** solo está disponible después de seleccionar una audiencia de Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Esta función no admite los tipos de datos de matriz y asignación. Además, solo se mostrarán en el selector los datos del esquema de unión.

1. Seleccione el campo XDM deseado de la lista y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Haga clic en el botón **[!UICONTROL Add]** para agregarlo a la lista de datos adicionales.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita estos pasos para cada campo XDM que desee añadir al flujo de trabajo.

   >[!NOTE]
   >
   >Puede añadir un máximo de 20 campos XDM en una actividad **[!UICONTROL Read audience]**.

1. Una vez añadidos todos los campos, haga clic en el botón **[!UICONTROL Confirm]** para guardar los cambios. Ahora están disponibles para personalizar los envíos.

Para obtener más información sobre cómo crear y personalizar entregas, consulte la documentación del Campaign Standard:

* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)
* [Personalización de entregas](../../designing/using/personalization.md)

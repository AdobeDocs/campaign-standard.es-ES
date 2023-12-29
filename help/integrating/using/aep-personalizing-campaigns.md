---
title: Personalización de las campañas con atributos de Adobe Experience Platform
description: Aprenda a personalizar sus campañas con atributos de Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Personalización de las campañas con atributos de Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en fase beta solo para Norteamérica) para acceder a estas funciones. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea acceder.
>
>**Push** y **En la aplicación** los canales aún no están disponibles para la personalización mediante datos contextuales de Adobe Experience Platform.

Una vez configurado el flujo de trabajo con una [Audiencia de Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md)Además, puede personalizar mensajes con atributos de perfil que existan exclusivamente en el Experience Data Model (XDM).

Para ello, debe añadir estos atributos a la **[!UICONTROL Read audience]** actividad:

1. Abra el **[!UICONTROL Read audience]** actividad. En el **[!UICONTROL Additional data]** , haga clic en **[!UICONTROL Create element]** botón.

   Tenga en cuenta que la variable **[!UICONTROL Additional data]** La pestaña solo está disponible después de seleccionar una audiencia de Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Los tipos de datos de matriz y asignación no son compatibles con esta función. Además, solo se mostrarán en el selector los datos del esquema de unión.

1. Seleccione el campo XDM deseado de la lista y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Haga clic en **[!UICONTROL Add]** para añadirlo a la lista de datos adicionales.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita estos pasos para cada campo XDM que desee agregar al flujo de trabajo.

   >[!NOTE]
   >
   >Puede añadir un máximo de 20 campos XDM en una **[!UICONTROL Read audience]** actividad.

1. Una vez añadidos todos los campos, haga clic en el **[!UICONTROL Confirm]** para guardar los cambios. Ahora están disponibles para personalizar las entregas.

Para obtener más información sobre cómo crear y personalizar envíos, consulte la documentación del Campaign Standard:

* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)
* [Personalización de entregas](../../designing/using/personalization.md)

---
solution: Campaign Standard
product: campaign
title: Personalización de las campañas con atributos de Adobe Experience Platform
description: Aprenda a personalizar sus campañas mediante los atributos de la plataforma de experiencias de Adobe.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 9%

---


# Personalización de las campañas con atributos de Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>El servicio Destinos de audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.
>
>**Los canales push** y **en la aplicación** aún no están disponibles para la personalización mediante datos contextuales de Adobe Experience Platform.

Una vez configurado el flujo de trabajo con una audiencia [de](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience Platform, puede personalizar los mensajes con atributos de perfil que existan exclusivamente en el modelo de datos de experiencia (XDM).

Para ello, debe agregar estos atributos a la **[!UICONTROL Read audience]** actividad:

1. Abra la actividad **[!UICONTROL Read audience]**. En la **[!UICONTROL Additional data]** ficha, haga clic en el **[!UICONTROL Create element]** botón.

   Tenga en cuenta que la **[!UICONTROL Additional data]** ficha solo está disponible después de seleccionar una audiencia de Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Esta función no admite los tipos de datos de matriz y asignación. Además, solo se mostrarán en el selector los datos del esquema de unión.

1. Seleccione el campo XDM deseado de la lista y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Haga clic en el **[!UICONTROL Add]** botón para agregarlo a la lista de datos adicionales.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita estos pasos para cada campo XDM que desee agregar al flujo de trabajo.

   >[!NOTE]
   >
   >Puede agregar un máximo de 20 campos XDM en una **[!UICONTROL Read audience]** actividad.

1. Una vez agregados todos los campos, haga clic en el **[!UICONTROL Confirm]** botón para guardar los cambios. Ahora estarán disponibles para personalizar sus envíos.

Para obtener más información sobre cómo crear y personalizar envíos, consulte la documentación del Campaign Standard:

* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)
* [Personalización de entregas](../../designing/using/personalization.md)

---
title: Segmentación de audiencias de Adobe Experience Platform
description: Obtenga información sobre cómo dirigirse a audiencias de Adobe Experience PLatform dentro de flujos de trabajo.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Segmentación de audiencias de Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>El servicio Destinos de audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Una vez que haya creado una audiencia [de la plataforma de experiencias de](../../audiences/using/aep-about-audience-destinations-service.md) Adobe mediante el creador de segmentos de perfil unificado, puede utilizarla del mismo modo que lo haría con una audiencia de campaña dentro de flujos de trabajo para personalizar y enviar mensajes.

Para activar una audiencia de Adobe Experience Platform en sus flujos de trabajo, siga estos pasos:

1. Agregue una **[!UICONTROL Read audience]**actividad al flujo de trabajo y ábrala.

1. Seleccione la **[!UICONTROL Adobe Experience Platform]**opción debajo de**[!UICONTROL Type of audience]**, luego agregue la audiencia deseada.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Una vez seleccionada la audiencia, puede hacer clic en el botón del ojo para revisar o editar la definición del segmento (asegúrese de guardar los cambios de nuevo).

   Al hacer clic en el botón del ojo simplemente se le dirigirá al Generador de segmentos unificado (en otra ficha) asociado con la audiencia seleccionada dentro de Campaign.

1. Seleccione un **[!UICONTROL Platform data mapping]**elemento para especificar la dimensión de objetivo deseada para la audiencia seleccionada de Adobe Experience Platform.

   De forma predeterminada, la clave principal (por ejemplo, la tabla iRecipientID para el perfil, la tabla iAppSubscriptionID para la suscripción de la aplicación) que se utiliza para la reconciliación estará disponible automáticamente en la lista desplegable. Para establecer el objetivo fuera de la clave principal, debe crear un **espacio** de nombres personalizado.

   >[!NOTE]
   >
   >En el caso de los destinos fuera de la clave principal, también debe crear una asignación de objetivos personalizada que corresponda al espacio de nombres personalizado. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contiene todas las asignaciones del Modelo de datos de experiencia (XDM) que se han configurado en la instancia. Para obtener más información sobre el conector de datos de la plataforma Adobe Experience, consulte [este documento](../../administration/using/aep-about-data-connector.md)dedicado.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una vez configuradas correctamente las dimensiones de audiencia y objetivo, haga clic en el **[!UICONTROL Confirm]**botón para guardar los cambios.

Ahora puede configurar el flujo de trabajo con otras actividades. Puede, por ejemplo, vincular una actividad para enviar un correo electrónico a la audiencia que se ha seleccionado **[!UICONTROL Email delivery]**.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard le permite dirigirse a las audiencias de la plataforma de experiencias de Adobe en todos los canales de entrega: Correos electrónicos, mensajes SMS, mensajes de correo directo, notificaciones push y mensajes en la aplicación.

Para obtener más información sobre cómo utilizar flujos de trabajo y envíos, consulte estas secciones:

* [Descubrimiento de flujos de trabajo](../../automating/using/discovering-workflows.md)
* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Descubrimiento de canales de comunicación](../../channels/using/discovering-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)

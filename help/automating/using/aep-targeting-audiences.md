---
title: Segmentación de las audiencias de Adobe Experience Platform
description: Obtenga información sobre el destinatario de audiencias de Adobe Experience PLatform en flujos de trabajo.
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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Segmentación de las audiencias de Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>El servicio Destinos de Audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Una vez que haya creado una audiencia [de](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience Platform con el generador de segmentos de Perfil unificado, puede utilizarla del mismo modo que lo haría con una audiencia de Campaña dentro de flujos de trabajo para personalizar y enviar mensajes.

Para activar una audiencia de Adobe Experience Platform en sus flujos de trabajo, siga estos pasos:

1. Añada una **[!UICONTROL Read audience]** actividad en el flujo de trabajo y ábrala.

1. Seleccione la **[!UICONTROL Adobe Experience Platform]** opción debajo de **[!UICONTROL Type of audience]**, luego agregue la audiencia deseada.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Una vez seleccionada la audiencia, puede hacer clic en el botón del ojo para revisar o editar la definición del segmento (asegúrese de guardar los cambios de nuevo).

   Al hacer clic en el botón del ojo simplemente se le dirigirá al Generador de segmentos unificado (en otra ficha) asociado con la audiencia seleccionada dentro de la Campaña.

1. Seleccione un **[!UICONTROL Platform data mapping]** elemento para especificar la dimensión de segmentación deseada para la audiencia seleccionada de Adobe Experience Platform.

   De forma predeterminada, la clave principal (por ejemplo, la tabla iRecipientID para Perfil, la tabla iAppSubscriptionID para AppSubscription) utilizada para la reconciliación estará disponible automáticamente en la lista desplegable. Para realizar destinatarios fuera de la clave principal, debe crear una **Área de nombres** personalizada.

   >[!NOTE]
   >
   >Para destinatarios fuera de la clave principal, también debe crear una Asignación de destino personalizada que corresponda a la Área de nombres personalizada. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contiene todas las asignaciones del Modelo de datos de experiencia (XDM) que se han configurado en la instancia. Para obtener más información sobre el conector de datos de la plataforma Adobe Experience, consulte [este documento](../../developing/using/aep-about-data-connector.md)dedicado.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una vez que la audiencia y las dimensiones de segmentación estén configuradas correctamente, haga clic en el **[!UICONTROL Confirm]** botón para guardar los cambios.

Ahora puede configurar el flujo de trabajo con otras actividades. Por ejemplo, puede vincular una **[!UICONTROL Email delivery]** actividad para enviar un correo electrónico a la audiencia seleccionada.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard permite el destinatario de audiencias de la plataforma de experiencia de Adobe en todos los canales de envío: Correos electrónicos, mensajes SMS, mensajes de Correo postal, notificaciones push y mensajes en la aplicación.
>
>*Nota: Para todos los mensajes push y en la aplicación, el Campaign Standard solo admite envíos para perfiles conocidos.

Para obtener más información sobre cómo utilizar flujos de trabajo y envíos, consulte estas secciones:

* [Descubrimiento de flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)

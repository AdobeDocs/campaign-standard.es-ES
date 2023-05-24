---
title: Direccionamiento de las audiencias de Adobe Experience Platform
description: Obtenga información sobre cómo dirigirse a audiencias de Adobe Experience Platform dentro de flujos de trabajo.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# Direccionamiento de las audiencias de Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en fase beta solo para Norteamérica) para acceder a estas funciones. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea acceder.

Una vez que haya creado un [Audiencia de Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md) Con el Generador de segmentos, puede utilizarlo del mismo modo que lo haría para una audiencia de Campaign dentro de flujos de trabajo para personalizar y enviar mensajes.

Para activar una audiencia de Adobe Experience Platform en los flujos de trabajo, siga estos pasos:

1. Añadir un **[!UICONTROL Read audience]** en el flujo de trabajo y, a continuación, ábralo.

1. Seleccione el **[!UICONTROL Adobe Experience Platform]** opción en **[!UICONTROL Type of audience]** y luego añada la audiencia que desee.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Una vez seleccionada la audiencia, puede hacer clic en el botón del ojo para revisar o editar la definición del segmento (asegúrese de guardar los cambios de nuevo).

   Al hacer clic en el botón del ojo, simplemente se le dirigirá al Generador de segmentos (en otra pestaña) asociado a la audiencia seleccionada en Campaign.

1. Seleccione una **[!UICONTROL Platform data mapping]** para especificar la dimensión de segmentación deseada para la audiencia de Adobe Experience Platform seleccionada.

   De forma predeterminada, la clave principal (por ejemplo, iRecipientID para la tabla Perfil, iAppSubscriptionID para la tabla AppSubscription) utilizada para la reconciliación estará disponible automáticamente en la lista desplegable. Para dirigirse fuera de la clave principal, debe crear un **Área de nombres**.

   >[!NOTE]
   >
   >Para los destinos fuera de la clave principal, también debe crear una asignación de destino personalizada que corresponda al área de nombres personalizada. Para obtener más información sobre la asignación de destino, consulte [esta sección](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contiene todas las asignaciones del Modelo de datos de experiencia (XDM) que se han configurado en la instancia. Para obtener más información sobre Adobe Experience Platform Data Connector, consulte [este documento dedicado](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una vez que las dimensiones de audiencia y segmentación estén configuradas correctamente, haga clic en **[!UICONTROL Confirm]** para guardar los cambios.

Ahora puede configurar el flujo de trabajo con otras actividades. Por ejemplo, puede vincular un **[!UICONTROL Email delivery]** actividad para enviar un correo electrónico a la audiencia que se ha seleccionado.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard le permite dirigirse a las audiencias de Adobe Experience Platform en todos los canales de entrega: correos electrónicos, mensajes SMS, mensajes de correo directo, notificaciones push y mensajes en la aplicación.
>
>*Nota: Para todos los mensajes push y en la aplicación, Campaign Standard solo admite envíos para perfiles conocidos.

Para obtener más información sobre cómo utilizar flujos de trabajo y envíos, consulte estas secciones:

* [Descubrimiento de flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Acerca de las actividades de canal](../../automating/using/about-channel-activities.md)

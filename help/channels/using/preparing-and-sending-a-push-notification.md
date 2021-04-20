---
solution: Campaign Standard
product: campaign
title: Creación y envío de una notificación push
description: Siga estos pasos para crear una notificación push de un solo envío en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 7%

---


# Preparación y envío de una notificación push{#preparing-and-sending-a-push-notification}

## Preparación de la notificación {#preparing-the-notification}

Los pasos para crear una notificación push con Adobe Campaign son:

1. Desde la ventana **[!UICONTROL Marketing activities]**, [cree una nueva actividad de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Tenga en cuenta que también se puede crear una sola notificación push desde una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o desde la [página principal](../../start/using/interface-description.md#home-page) de Adobe Campaign.

   También puede utilizar una actividad de entrega de notificaciones push en un flujo de trabajo. Esta actividad se presenta en la sección [Push notification delivery](../../automating/using/push-notification-delivery.md).

1. Seleccione **[!UICONTROL Push notification]**.
1. Seleccione una plantilla.

   ![](assets/push_notif_type.png)

   De forma predeterminada, puede seleccionar una de las dos plantillas siguientes:

   * **[!UICONTROL Send push to Campaign profiles]**: utilice esta plantilla para dirigirse a los perfiles de Adobe Campaign CRM que se han suscrito a su aplicación móvil y han elegido recibir notificaciones push. Puede insertar campos [personalization](../../designing/using/personalization.md#inserting-a-personalization-field) en la notificación push, como el nombre del destinatario.
   * **[!UICONTROL Send push to app subscribers]**: utilice esta plantilla para enviar una notificación push a todos los usuarios conocidos y anónimos de aplicaciones móviles que hayan elegido recibir notificaciones de su aplicación. Puede personalizar estos mensajes con los datos recopilados de su aplicación móvil.

   También puede seleccionar plantillas multilingües. Para obtener más información, consulte [Creación de una notificación push multilingüe](../../channels/using/creating-a-multilingual-push-notification.md).

   Para obtener más información sobre las plantillas, consulte la sección [Administración de plantillas](../../start/using/marketing-activity-templates.md).

1. Introduzca las propiedades de la notificación push y seleccione la aplicación móvil en el campo **[!UICONTROL Associate a Mobile App to a delivery]** .

   Tenga en cuenta que la lista desplegable mostrará las aplicaciones SDK V4 y SDK de Experience Platform.

   ![](assets/push_notif_properties.png)

   Puede vincular la notificación push a una campaña. Para ello, selecciónelo entre las campañas que ya se han creado.

1. En la siguiente pantalla, puede especificar una audiencia, por ejemplo, todos los clientes de VIP que se suscribieron a una aplicación móvil específica. Para obtener más información, consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).

   La audiencia se filtrará automáticamente según la aplicación móvil seleccionada en el paso anterior.

   ![](assets/push_notif_audience.png)

1. Ahora puede personalizar la notificación push. En primer lugar, elija el estilo del mensaje: **[!UICONTROL Alert/Message/Badge]** o **[!UICONTROL Silent push]**. Los tipos de notificaciones push se describen en la sección [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md).

   Edite el contenido de la notificación push y defina las opciones avanzadas. Consulte [Personalización de una notificación push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   El contenido de las notificaciones push y las opciones configuradas aquí se pasan a su aplicación móvil en forma de carga útil. La estructura detallada de la carga útil se describe en la nota técnica [Understanding Campaign Standard push notifications payload structure](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/push-notifications/push-payload.translate.html).

1. Haga clic en **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar la notificación, puede probarla con perfiles de prueba y luego ver exactamente lo que verán los destinatarios antes de realizar la entrega. Seleccione **[!UICONTROL Audiences]** en el resumen del envío y haga clic en la pestaña **[!UICONTROL Test profiles]** .

   Para obtener más información sobre el envío de pruebas, consulte [Perfiles de prueba](../../sending/using/sending-proofs.md).

1. Seleccione los perfiles de prueba y haga clic en **[!UICONTROL Preview]** para mostrar la notificación: el contenido se personaliza con los datos de perfil de prueba.
1. Compruebe el diseño de las notificaciones push en diferentes dispositivos: seleccione iPhone, Android phone, iPad o Android tablet para previsualizar el procesamiento.

   ![](assets/push_notif_preview.png)

1. El **[!UICONTROL Estimated Payload Size]** es una estimación basada en los datos del perfil de prueba. El tamaño real de la carga útil puede variar. El límite del mensaje es de 4 KB.

   >[!CAUTION]
   >
   >Si el tamaño de la carga útil supera el límite de 4 KB, el mensaje no se enviará.

Tenga en cuenta que los datos de personalización afectan al tamaño del mensaje.

## Envío de la notificación {#sending-the-notification}

Las notificaciones push se pueden enviar a una audiencia seleccionada en Adobe Campaign definiendo los criterios de audiencia. Por ejemplo, la audiencia seleccionada consiste en 4 suscriptores de aplicaciones móviles segmentadas.

1. Haga clic en **[!UICONTROL Prepare]** para calcular el objetivo y generar las notificaciones.

   ![](assets/push_send_1.png)

1. Una vez que la preparación ha finalizado correctamente, la ventana **[!UICONTROL Deployment]** presenta los siguientes KPI: **[!UICONTROL Target]** y **[!UICONTROL To deliver]**. Tenga en cuenta que el recuento **[!UICONTROL To deliver]** es menor que el de **[!UICONTROL Targeted]**, debido a exclusiones que se pueden ver haciendo clic en el botón ![](assets/lp_link_properties.png) de la parte inferior de la ventana **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. En la pestaña **[!UICONTROL Exclusion logs]**, puede encontrar la lista de todos los mensajes excluidos del destinatario enviados y el motivo detrás de esta exclusión.

   Aquí podemos ver que uno de nuestros suscriptores de la aplicación móvil se excluyó porque la dirección estaba en la  de lista de bloqueados y los demás suscriptores porque el perfil era un duplicado.

   ![](assets/push_send_5.png)

1. Haga clic en la pestaña **[!UICONTROL Exclusion causes]** para mostrar el volumen de mensajes excluidos.

   ![](assets/push_send_7.png)

1. Ahora puede hacer clic en **[!UICONTROL Confirm]** para empezar a enviar notificaciones push.
1. Compruebe el estado de la entrega a través del panel de mensajes y los registros. Para obtener más información, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md) y [Registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   En este ejemplo, el panel de mensajes muestra que Adobe Campaign ha intentado enviar dos notificaciones push: uno se entregó correctamente al dispositivo y otro falló. Para saber por qué el envío tiene errores, haga clic en el botón ![](assets/lp_link_properties.png) en la parte inferior de la ventana **[!UICONTROL Deployment]**.

   ![](assets/push_send_4.png)

1. En la ventana **[!UICONTROL Deployment]** , haga clic en la pestaña **[!UICONTROL Sending logs]** para acceder a la lista de notificaciones push enviadas y sus estados. Para este envío, se envió correctamente una notificación push, mientras que la otra falló debido a un token incorrecto del dispositivo. A continuación, este suscriptor se agregará a la  de lista de bloqueados desde entregas posteriores.

   >[!NOTE]
   >
   >Las razones pueden ser cualquier fallo que se produzca después de Adobe Campaign. En caso de fallos de proveedores como apns y fcm, la razón también lo reflejará. Para obtener más información sobre los errores del proveedor, consulte la documentación de [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) y [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref).

   ![](assets/push_send_6.png)

Ahora puede medir el impacto del envío de notificaciones push con informes dinámicos.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)

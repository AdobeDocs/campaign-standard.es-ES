---
solution: Campaign Standard
product: campaign
title: Crear y enviar una notificación push
description: Siga estos pasos para crear una notificación push de un solo envío en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 7%

---


# Preparación y envío de una notificación push{#preparing-and-sending-a-push-notification}

## Preparación de la notificación {#preparing-the-notification}

Los pasos para crear una notificación push con Adobe Campaign son:

1. En la **[!UICONTROL Marketing activities]** ventana, [cree una nueva actividad](../../start/using/marketing-activities.md#creating-a-marketing-activity)de marketing.

   Tenga en cuenta que también se puede crear una sola notificación push desde una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o desde la [página de inicio](../../start/using/interface-description.md#home-page)de Adobe Campaign.

   También puede utilizar una actividad de envío de notificaciones push en un flujo de trabajo. Esta actividad se presenta en la sección envío [de notificaciones](../../automating/using/push-notification-delivery.md) push.

1. Seleccione **[!UICONTROL Push notification]**.
1. Seleccione una plantilla.

   ![](assets/push_notif_type.png)

   De forma predeterminada, puede seleccionar una de las dos plantillas siguientes:

   * **[!UICONTROL Send push to Campaign profiles]**:: utilice esta plantilla para el destinatario de los perfiles de Adobe Campaign CRM que se han suscrito a su aplicación móvil y han adhesión para recibir notificaciones push. Puede insertar campos de [personalización](../../designing/using/personalization.md#inserting-a-personalization-field) en la notificación push, como el nombre del destinatario.
   * **[!UICONTROL Send push to app subscribers]**:: utilice esta plantilla para enviar una notificación push a todos los usuarios de aplicaciones móviles conocidos y anónimos que hayan adhesión para recibir notificaciones de la aplicación. Puede personalizar estos mensajes con los datos recopilados de la aplicación móvil.

   También puede seleccionar plantillas multilingües. Para obtener más información, consulte [Creación de una notificación](../../channels/using/creating-a-multilingual-push-notification.md)push multilingüe.

   For more on templates, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tenga en cuenta que la lista desplegable mostrará las aplicaciones SDK V4 y SDK Experience Platform.

   ![](assets/push_notif_properties.png)

   Puede vincular la notificación push a una campaña. Para ello, selecciónelo entre las campañas que ya se han creado.

1. En la siguiente pantalla, puede especificar una audiencia, por ejemplo, todos los clientes de VIP que se suscribieron a una aplicación móvil específica. Para obtener más información sobre esto, consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).

   La audiencia se filtrará automáticamente según la aplicación móvil seleccionada en el paso anterior.

   ![](assets/push_notif_audience.png)

1. Ahora puede personalizar la notificación push. Primero, elija el estilo del mensaje: **[!UICONTROL Alert/Message/Badge]** o **[!UICONTROL Silent push]**. Los tipos de notificaciones push se describen en la sección [Acerca de las notificaciones](../../channels/using/about-push-notifications.md) push.

   Edite el contenido de la notificación push y defina las opciones avanzadas. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   El contenido y las opciones de la notificación push configuradas aquí se pasan a la aplicación móvil en forma de carga útil. La estructura detallada de la carga útil se describe en la nota técnica [Explicación de la estructura](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/push-notifications/push-payload.translate.html) de carga útil de las notificaciones push de ACS.

1. Haga clic en **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar la notificación, puede probarla con perfiles de prueba y luego ver exactamente lo que verán sus destinatarios antes de enviar el envío. Seleccione **[!UICONTROL Audiences]** en el resumen del envío y haga clic en la **[!UICONTROL Test profiles]** ficha.

   Para obtener más información sobre el envío de pruebas, consulte [perfiles](../../sending/using/sending-proofs.md)de prueba.

1. Seleccione los perfiles de prueba y haga clic en **[!UICONTROL Preview]** para mostrar la notificación: el contenido se personaliza con los datos del perfil de prueba.
1. Compruebe el diseño de la notificación push en distintos dispositivos: seleccione iPhone, teléfono Android, iPad o tablet Android para procesar la previsualización.

   ![](assets/push_notif_preview.png)

1. Se **[!UICONTROL Estimated Payload Size]** trata de una estimación basada en los datos del perfil de prueba. El tamaño real de la carga útil puede variar. El límite del mensaje es de 4 KB.

   >[!CAUTION]
   >
   >Si el tamaño de la carga útil supera el límite de 4 KB, el mensaje no se enviará.

Tenga en cuenta que los datos de personalización afectan al tamaño del mensaje.

## Envío de la notificación {#sending-the-notification}

Las notificaciones push se pueden enviar a una audiencia seleccionada en Adobe Campaign definiendo los criterios de audiencia. Para el ejemplo siguiente, nuestra audiencia seleccionada consiste en 4 suscriptores de aplicaciones móviles con objetivo.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Tenga en cuenta que el recuento **[!UICONTROL To deliver]** es menor que el de **[!UICONTROL Targeted]**, debido a exclusiones que se pueden ver haciendo clic en el botón ![](assets/lp_link_properties.png) de la parte inferior de la ventana **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. En la **[!UICONTROL Exclusion logs]** ficha, puede encontrar la lista de todos los mensajes excluidos del destinatario enviado y el motivo de esta exclusión.

   Aquí podemos ver que uno de nuestros suscriptores de aplicaciones móviles fue excluido porque la dirección estaba en la  de lista de bloqueados y los demás suscriptores porque el perfil era un duplicado.

   ![](assets/push_send_5.png)

1. Haga clic en la **[!UICONTROL Exclusion causes]** ficha para mostrar el volumen de mensajes excluidos.

   ![](assets/push_send_7.png)

1. Ahora puede hacer clic en **[!UICONTROL Confirm]** el inicio para enviar notificaciones push.
1. Compruebe el estado de la entrega a través del panel de mensajes y los registros. Para obtener más información sobre esto, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md) y [Registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   En este ejemplo, el panel de mensajes muestra que Adobe Campaign ha intentado enviar dos notificaciones push: uno se entregó correctamente al dispositivo y otro falló. Para saber por qué el envío tiene errores, haga clic en el ![](assets/lp_link_properties.png) botón en la parte inferior de la **[!UICONTROL Deployment]** ventana.

   ![](assets/push_send_4.png)

1. En la **[!UICONTROL Deployment]** ventana, haga clic en la **[!UICONTROL Sending logs]** ficha para acceder a la lista de las notificaciones push enviadas y sus estados. Para este envío, se envió correctamente una notificación push, mientras que la otra falló debido a un autentificador de dispositivo incorrecto. Este suscriptor se agregará a la  de lista de bloqueados desde otros envíos.

   >[!NOTE]
   >
   >Las razones pueden ser cualquier error posterior a Adobe Campaign. En caso de fallos de proveedores como apns y fcm, la razón también lo reflejará. Para obtener más información sobre los errores del proveedor, consulte la documentación de [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) y [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) .

   ![](assets/push_send_6.png)

Ahora puede medir el impacto del envío de las notificaciones push con los informes dinámicos.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)

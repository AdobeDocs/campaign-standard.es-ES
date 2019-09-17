---
title: Preparación y envío de una notificación push
seo-title: Preparación y envío de una notificación push
description: Preparación y envío de una notificación push
seo-description: Siga estos pasos para crear una notificación push de un solo envío en Adobe Campaign.
page-status-flag: nunca activado
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: entrega,mobileAppContent,retroceso
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Preparación y envío de una notificación push{#preparing-and-sending-a-push-notification}

## Preparación de la notificación {#preparing-the-notification}

Los pasos para crear una notificación push con Adobe Campaign son:

1. En la **[!UICONTROL Marketing activities]** ventana, [cree una nueva actividad](../../start/using/marketing-activities.md#creating-a-marketing-activity)de marketing.

   Tenga en cuenta que también se puede crear una sola notificación push desde una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o desde la página [principal](../../start/using/interface-description.md#home-page)de Adobe Campaign.

   También puede utilizar una actividad de envío de notificaciones push en un flujo de trabajo. Esta actividad se presenta en la sección de envío [de notificaciones](../../automating/using/push-notification-delivery.md) push.

1. Seleccione **[!UICONTROL Push notification]**.
1. Seleccione una plantilla.

   ![](assets/push_notif_type.png)

   De forma predeterminada, puede seleccionar una de las dos plantillas siguientes:

   * **[!UICONTROL Send push to Campaign profiles]**:: utilice esta plantilla para dirigirse a los perfiles de CRM de Adobe Campaign que se han suscrito a su aplicación móvil y han elegido recibir notificaciones push. Puede insertar campos de [personalización](../../designing/using/personalization.md#inserting-a-personalization-field) en la notificación push, como el nombre del destinatario.
   * **[!UICONTROL Send push to app subscribers]**:: utilice esta plantilla para enviar una notificación push a todos los usuarios de aplicaciones móviles conocidos y anónimos que hayan elegido recibir notificaciones desde la aplicación. Puede personalizar estos mensajes con los datos recopilados de la aplicación móvil.
   También puede seleccionar plantillas multilingües. Para obtener más información, consulte [Creación de una notificación](../../channels/using/creating-a-multilingual-push-notification.md)push multilingüe.

   Para obtener más información sobre las plantillas, consulte la sección [Administración de plantillas](../../start/using/about-templates.md) .

1. Introduzca las propiedades de la notificación push y seleccione la aplicación móvil en el **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Tenga en cuenta que el menú desplegable mostrará las aplicaciones SDK V4 y SDK de la plataforma de experiencia.

   ![](assets/push_notif_properties.png)

   Puede vincular la notificación push a una campaña. Para ello, selecciónelo de las campañas que ya se hayan creado.

1. En la siguiente pantalla, puede especificar una audiencia, por ejemplo, todos los clientes VIP que se suscribieron a una aplicación móvil específica. Para obtener más información sobre esto, consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).

   La audiencia se filtrará automáticamente según la aplicación móvil seleccionada en el paso anterior.

   ![](assets/push_notif_audience.png)

1. Ahora puede personalizar la notificación push. Primero, elija el estilo del mensaje: **[!UICONTROL Alert/Message/Badge]** o **[!UICONTROL Silent push]**. Los tipos de notificaciones push se describen en la sección [Acerca de las notificaciones](../../channels/using/about-push-notifications.md) push.

   Edite el contenido de la notificación push y defina las opciones avanzadas. Consulte [Personalización de una notificación](../../channels/using/customizing-a-push-notification.md)push.

   ![](assets/push_notif_content.png)

   El contenido y las opciones de la notificación push configuradas aquí se pasan a la aplicación móvil en forma de carga útil. La estructura detallada de la carga útil se describe en la nota técnica [Explicación de la estructura](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) de carga útil de las notificaciones push de ACS.

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar la notificación, puede probarla con perfiles de prueba y luego ver exactamente lo que verán los destinatarios antes de enviar la entrega. Seleccione **[!UICONTROL Audiences]** el resumen de envío y haga clic en la **[!UICONTROL Test profiles]** ficha.

   Para obtener más información sobre el envío de pruebas, consulte Perfiles [de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Seleccione los perfiles de prueba y haga clic en **[!UICONTROL Preview]** para mostrar la notificación: el contenido se personaliza con los datos del perfil de prueba.
1. Compruebe el diseño de la notificación push en distintos dispositivos: seleccione iPhone, teléfono Android, iPad o tablet Android para obtener una vista previa del procesamiento.

   ![](assets/push_notif_preview.png)

1. Se **[!UICONTROL Estimated Payload Size]** trata de una estimación basada en los datos del perfil de prueba. El tamaño real de la carga útil puede variar. El límite del mensaje es de 4 KB.

   >[!CAUTION]
   >
   >Si el tamaño de carga útil supera el límite de 4 KB, el mensaje no se enviará. Los datos de personalización afectan al tamaño del mensaje.

## Envío de la notificación {#sending-the-notification}

Las notificaciones push se pueden enviar a una audiencia seleccionada en Adobe Campaign definiendo los criterios de audiencia. Por ejemplo, la audiencia seleccionada está formada por 4 suscriptores de aplicaciones móviles con objetivo.

1. Haga clic en **[!UICONTROL Prepare]** para calcular el objetivo y generar las notificaciones.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Tenga en cuenta que el recuento **[!UICONTROL To deliver]** es menor que el de **[!UICONTROL Targeted]**, debido a exclusiones que se pueden ver haciendo clic en el botón ![](assets/lp_link_properties.png) de la parte inferior de la ventana **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. En la **[!UICONTROL Exclusion logs]** ficha, puede encontrar la lista de todos los mensajes excluidos del destino enviado y el motivo de esta exclusión.

   Aquí podemos ver que uno de nuestros suscriptores de aplicaciones móviles fue excluido porque la dirección estaba bloqueada y los demás suscriptores porque el perfil estaba duplicado.

   ![](assets/push_send_5.png)

1. Haga clic en la **[!UICONTROL Exclusion causes]** ficha para mostrar el volumen de mensajes excluidos.

   ![](assets/push_send_7.png)

1. Ahora puede hacer clic **[!UICONTROL Confirm]** para empezar a enviar notificaciones push.
1. Compruebe el estado de la entrega a través del tablero de mensajes y los registros. Para obtener más información sobre esto, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md) y registros [de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   En este ejemplo, el panel de mensajes muestra que Adobe Campaign ha intentado enviar dos notificaciones push: uno se entregó correctamente al dispositivo y otro falló. Para saber por qué la entrega tiene errores, haga clic en el ![](assets/lp_link_properties.png) botón en la parte inferior de la **[!UICONTROL Deployment]** ventana.

   ![](assets/push_send_4.png)

1. En la **[!UICONTROL Deployment]** ventana, haga clic en la **[!UICONTROL Sending logs]** ficha para acceder a la lista de notificaciones push enviadas y sus estados. Para esta entrega, se envió correctamente una notificación push, mientras que la otra falló debido a un autentificador de dispositivo incorrecto. Este suscriptor quedará bloqueado en otras entregas.

   >[!NOTE]
   >
   >Las razones pueden ser cualquier error posterior a Adobe Campaign. En caso de fallos de proveedores como apns y fcm, la razón también lo reflejará. Para obtener más información sobre los errores del proveedor, consulte la documentación de [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) y [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) .

   ![](assets/push_send_6.png)

Ahora puede medir el impacto del envío de notificaciones push con informes dinámicos.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)


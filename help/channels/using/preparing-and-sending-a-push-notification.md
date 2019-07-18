---
title: Preparación y envío de una notificación Push
seo-title: Preparación y envío de una notificación Push
description: Preparación y envío de una notificación Push
seo-description: Siga estos pasos para crear una notificación Push de envío único en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 01997725-ca 0 a -420 c -9 e 81-5 ea 801652 f 87
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: notificaciones push
discoiquuid: ec 930 cd 4-6365-4 e 54-babe -9 dc 2 eed 041 fc
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Preparing and sending a push notification{#preparing-and-sending-a-push-notification}

## Preparing the notification {#preparing-the-notification}

Los pasos para crear una notificación Push con Adobe Campaign son los siguientes:

1. From the **[!UICONTROL Marketing activities]** window, [create a new marketing activity](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Note that a single push notification can also be created from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   También puede utilizar una actividad de envío de notificaciones Push en un flujo de trabajo. This activity is presented in the [Push notification delivery](../../automating/using/push-notification-delivery.md) section.

1. Select **[!UICONTROL Push notification]**.
1. Seleccione una plantilla.

   ![](assets/push_notif_type.png)

   De forma predeterminada, puede seleccionar una de las dos plantillas siguientes:

   * **[!UICONTROL Send push to Campaign profiles]**: utilice esta plantilla para dirigirse a los perfiles de CRM de Adobe Campaign que se han suscrito a la aplicación móvil y que han elegido recibir notificaciones push. You can insert [personalization](../../designing/using/inserting-a-personalization-field.md) fields into your push notification, such as the recipient's first name.
   * **[!UICONTROL Send push to app subscribers]**: utilice esta plantilla para enviar una notificación push a todos los usuarios de aplicaciones móviles anónimas y anónimas que hayan elegido recibir notificaciones desde su aplicación. Puede personalizar estos mensajes con datos recopilados de su aplicación móvil.
   También puede seleccionar plantillas multilingües. For more information, refer to [Creating a multilingual push notification](../../channels/using/creating-a-multilingual-push-notification.md).

   For more on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tenga en cuenta que el menú desplegable mostrará las aplicaciones SDK V 4 y Experience Platform de SDK.

   ![](assets/push_notif_properties.png)

   Puede vincular la notificación push a una campaña. Para ello, selecciónelo de las campañas que ya se hayan creado.

1. En la siguiente pantalla puede especificar una audiencia, por ejemplo, todos los clientes VIP que se suscribieron a una aplicación móvil específica. For more on this, see [Creating audiences](../../audiences/using/creating-audiences.md).

   La audiencia se filtrará automáticamente en función de la aplicación móvil seleccionada en el paso anterior.

   ![](assets/push_notif_audience.png)

1. Ahora puede personalizar la notificación Push. First, choose the message style: **[!UICONTROL Alert/Message/Badge]** or **[!UICONTROL Silent push]**. The push notification types are described in the [About push notifications](../../channels/using/about-push-notifications.md) section.

   Edite el contenido de la notificación Push y defina las opciones avanzadas. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   El contenido de notificaciones push y las opciones configuradas aquí se pasan a su aplicación móvil en forma de carga útil. The detailed structure of the payload is described in the [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technote.

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar la notificación, puede probarla con perfiles de prueba y, a continuación, ver exactamente lo que verán los destinatarios antes de enviar el envío. Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   For more on sending tests, refer to [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. Consulte el diseño de notificaciones Push en diferentes dispositivos: seleccione iphone, teléfono Android, ipad o tablet Android para previsualizar el procesamiento.

   ![](assets/push_notif_preview.png)

1. The **[!UICONTROL Estimated Payload Size]** is an estimate based on test profile data. El tamaño real de carga útil puede variar. El límite del mensaje es 4 KB.

   >[!CAUTION]
   >
   >Si el tamaño de carga útil supera el límite de 4 KB, el mensaje no se enviará. Los datos de personalización afectan al tamaño del mensaje.

## Sending the notification {#sending-the-notification}

Las notificaciones Push se pueden enviar a una audiencia seleccionada en Adobe Campaign definiendo los criterios de audiencia. Para el ejemplo siguiente, nuestra audiencia seleccionada consiste en 4 suscriptores de aplicaciones móviles con objetivo.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Tenga en cuenta que el recuento **[!UICONTROL To deliver]** es menor que el de **[!UICONTROL Targeted]**, debido a exclusiones que se pueden ver haciendo clic en el botón ![](assets/lp_link_properties.png) de la parte inferior de la ventana **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. In the **[!UICONTROL Exclusion logs]** tab, you can find the list of all the messages excluded from the target sent and the reason behind this exclusion.

   Aquí podemos ver que uno de nuestros suscriptores de aplicaciones móviles fue excluido porque la dirección estaba bloqueada y los demás suscriptores porque el perfil estaba duplicado.

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. Compruebe el estado de la entrega a través del panel de mensajes y registros. For more on this, see [Sending messages](../../sending/using/confirming-the-send.md) and [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   En este ejemplo, el panel de mensajes muestra que Adobe Campaign ha intentado enviar dos notificaciones Push: uno se entregó correctamente al dispositivo y otro falló. To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. From the **[!UICONTROL Deployment]** window, click the **[!UICONTROL Sending logs]** tab to access the list of sent push notifications and their statuses. Para esta entrega, se envió una notificación Push correctamente, mientras que la otra falló debido a un token de dispositivo incorrecto. A continuación, este suscriptor quedará bloqueado a partir de entregas posteriores.

   >[!NOTE]
   >
   >Las razones pueden ser cualquier error descendente en Adobe Campaign. En caso de errores de proveedores como apns y fcm, el motivo también reflejará esto. For more information on provider failures, you can refer to the [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentation.

   ![](assets/push_send_6.png)

Ahora puede medir el impacto de la entrega de notificaciones Push con informes dinámicos.

**Temas relacionados:**

* [Informe de notificaciones Push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación Push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)


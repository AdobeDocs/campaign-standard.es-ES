---
title: Preparación y envío de un mensaje en la aplicación
seo-title: Preparación y envío de un mensaje en la aplicación
description: Preparación y envío de un mensaje en la aplicación
seo-description: Cree un mensaje en la aplicación para dirigir a los suscriptores de la aplicación con contenido específico.
page-status-flag: no activado nunca
uuid: a 79 b 0466-8641-46 cc-a 70 f-e 4 e 839587 bb 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajería en la aplicación
discoiquuid: 18 bf 5297-a 688-4302-abe 4-e 2 fbcafdb 515
context-tags: delivery, activadores, back; Deliverycreation, wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e3b71fdaf18a20dc87a05c2a964a3429c75dd3ce

---


# Preparing and sending an In-App message{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>La personalización en la aplicación se basa en un campo de vinculación que suele ser un ID de CRM o un ID de inicio de sesión de aplicación móvil. Usted es el único responsable de asegurar este campo de vinculación cuando se utiliza en conexión con Adobe Campaign. Si no consigue que los campos de vinculación sean seguros, su mensaje personalizado puede ser vulnerable. Adobe no será responsable de los daños que surgen del acceso no autorizado o del uso de cualquier dato de perfil si no se siguen las prácticas de composición, administración y protección del campo de vinculación seguro.

En Adobe Campaign hay tres tipos de mensaje en la aplicación:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Este tipo de mensaje le permite segmentar perfiles de Adobe Campaign (perfiles CRM) que se han suscrito a la aplicación móvil. Este tipo de mensaje se puede personalizar con todos los atributos de perfil disponibles en Adobe Campaign, pero requiere un protocolo de enlace seguro entre el SDK móvil y el servicio de mensajería en la aplicación de Campaign para garantizar que los usuarios autorizados utilicen los mensajes con información personal y delicada.

   Para descargar este tipo de mensaje en los dispositivos de los usuarios, Mobile SDK tiene que enviar campos de vinculación utilizados para conectar un perfil móvil a un perfil CRM en Adobe Campaign. For more information on SDK APIs required to support In-App, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Este tipo de mensaje le permite enviar mensajes a todos los usuarios (actuales o futuros) de la aplicación móvil aunque no tengan un perfil existente en Adobe Campaign. Por lo tanto, la personalización no es posible cuando se personalizan los mensajes como el perfil de usuario no existe ni siquiera en Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Este tipo de mensaje le permite dirigirse a todos los usuarios anónimos o anónimos de una aplicación móvil que tenga un perfil móvil en Adobe Campaign. Este tipo de mensajes se puede personalizar utilizando atributos no personales y no confidenciales y no requiere de protocolo de enlace seguro entre el SDK de Mobile y el servicio de mensajería en la aplicación de Adobe Campaign.

   For more information on how to handle personal and sensitive data, refer to [Handling mobile profile fields with personal and sensitive data](../../channels/using/preparing-and-sending-an-in-app-message.md#handling-mobile-profile-fields-with-personal-and-sensitive-data).

![](assets/diagram_inapp.png)

## Handling mobile profile fields with personal and sensitive data {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Este recurso debe ampliarse para recopilar datos que se pretenden enviar desde el dispositivo móvil a Adobe Campaign. To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Para habilitar la personalización de los mensajes en la aplicación de forma más segura, es necesario configurar los campos de perfil móvil de este recurso. In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>Si tiene una implementación existente con la extensión de recurso personalizada en esta tabla, le recomendamos que etiquete los campos correctamente antes de aprovecharlos para personalizar los mensajes en la aplicación.

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users' PII data remains secure.

## Preparing your In-App message {#preparing-your-in-app-message}

Los pasos para crear un mensaje en la aplicación independiente con Adobe Campaign son los siguientes:

1. From Adobe Campaign home page, click the **[!UICONTROL In-App messaging]** card.

   You can also create an In-App from the **Marketing activities** tab, by clicking the **[!UICONTROL Create]** button.

   Tenga en cuenta que también se puede crear un mensaje en la aplicación desde una campaña o desde la página principal de Adobe Campaign o desde un flujo de trabajo.

1. Select **In-App message**.

   ![](assets/inapp_creating.png)

1. Seleccione una plantilla adecuada según las necesidades de segmentación de visitantes.

   ![](assets/inapp_creating_2.png)

   De forma predeterminada, puede seleccionar una de las tres siguientes plantillas integradas:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Enter the In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   ![](assets/inapp_creating_3.png)

1. Seleccione la audiencia a la que desea dirigir el mensaje en la aplicación. La audiencia se filtra previamente según la aplicación móvil asociada a esta entrega.

   Note that this step is not needed with the **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** since it targets all users of a mobile application.

   ![](assets/inapp_creating_8.png)

1. In the **[!UICONTROL Triggers]** tab, drag and drop the event that will trigger your message. Si elige un activador, elige una acción realizada por los usuarios que hará que se muestre el mensaje en la aplicación.

   Hay disponibles cuatro categorías de eventos:

   * **[!UICONTROL Mobile Application events]**: Eventos personalizados implementados en la aplicación móvil.

      For more on events creations, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**: Eventos de ciclo de vida predeterminados admitidos por el SDK de Adobe Mobile.

      For more on life cycle events, refer to this [page](https://marketing.adobe.com/resources/help/en_US/mobile/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: Las tres categorías siguientes son compatibles en función de lo instrumentado en su aplicación móvil: Adobe Analytics, datos de contexto o estado de visualización.

      Tenga en cuenta que estos eventos solo están disponibles si tiene una licencia de Adobe Analytics.

   * **[!UICONTROL Places]**: Las tres categorías siguientes aprovechan los datos de ubicación en tiempo real para ofrecer experiencias móviles relevantes contextualmente: Coloca los datos de contexto, coloca los metadatos personalizados o el tipo de evento Lugares.

      For more information on Adobe Places, refer to the [Places documentation](https://placesdocs.com/).
   ![](assets/inapp_creating_4.png)

1. If you use an **[!UICONTROL Analytics Events]**, Adobe Analytics and View state events will be automatically populated based on the report suites configured in the Analytics extension in Adobe Experience Platform Launch whereas Context data events have to be manually added.

   Tenga en cuenta que estos eventos solo están disponibles si tiene una licencia de Adobe Analytics.

   ![](assets/inapp_creating_7.png)

1. If you use a **[!UICONTROL Places]** trigger, Places context data, Places custom metadata or Places event type will be automatically populated based on all the Libraries and their Points of Interest created in Adobe Places.

   Tenga en cuenta que este activador se aplicará al dispositivo solo para los puntos de interés de las bibliotecas seleccionadas en la extensión Lugares en Launch Platform Launch. For more information on the Places extension and how to install it, refer to this [documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1/places-extension).

1. In the **[!UICONTROL Frequency & duration]** tab, choose the frequency for your trigger, the start and end date, day of the week and time of the day when your In-App message will be active.

   ![](assets/inapp_creating_5.png)

1. Edite el contenido del mensaje y defina las opciones avanzadas. See [Customizing an In-App message](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html).

   ![](assets/inapp_creating_6.png)

1. Click **[!UICONTROL Create]**.

El mensaje en la aplicación ya está listo para enviarse a la audiencia objetivo.

**Temas relacionados:**

* [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md)
* [Informe en la aplicación](../../reporting/using/in-app-report.md)
* [Envío de un mensaje en la aplicación dentro de un flujo de trabajo](../../automating/using/in-app-delivery.md)

## Sending your In-App message {#sending-your-in-app-message}

Cuando haya terminado de preparar la entrega y se hayan llevado a cabo los pasos de aprobación, puede enviar el mensaje.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the messages.

   ![](assets/inapp_sending_4.png)

1. Una vez que la preparación ha finalizado correctamente, la ventana **Deployment** muestra los siguientes KPI: **Target** y **To deliver**.

   You can check the Deployment window by clicking the ![](assets/lp_link_properties.png) button for potential exclusions or errors in your delivery.

   ![](assets/inapp_sending_5.png)

1. Click **[!UICONTROL Confirm]** to start sending your In-App message.

   ![](assets/inapp_sending_6.png)

1. Compruebe el estado de la entrega a través del panel de mensajes y registros. For more on this, refer to this [section](../../sending/using/monitoring-a-delivery.md).

   **[!UICONTROL Delivered]** y **[!UICONTROL Sent]** los KPI se basan en lo que se envía correctamente desde el servicio de entrega de campaña al mensaje. Tenga en cuenta que estos KPI no indican el número de dispositivos móviles que recibieron o descargaron el mensaje correctamente del servicio de entrega de mensajes.

   ![](assets/inapp_sending_7.png)

1. Mida el impacto de los mensajes en la aplicación con los informes de entrega. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**Temas relacionados:**

* [Informe en la aplicación](../../reporting/using/in-app-report.md)
* [Envío de un mensaje en la aplicación dentro de un flujo de trabajo](../../automating/using/in-app-delivery.md)


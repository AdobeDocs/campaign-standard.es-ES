---
title: Configuración de la integración de datos de puntos de interés de los puntos de interés
seo-title: Configuración de la integración de datos de puntos de interés de los puntos de interés
description: Configuración de la integración de datos de puntos de interés de los puntos de interés
seo-description: Descubra cómo configurar la función de datos Puntos de interés en Adobe Campaign para enviar mensajes personalizados según la ubicación de los suscriptores.
page-status-flag: no activado nunca
uuid: 0689 a 06 c-cc 1 a -442 f -95 b 8-a 07 fcec 85 d 79
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-mobile-for-mobile
discoiquuid: a 967 c 6 cc-c 53 b -41 b 4-866 b -90860 d 78 f 463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 84fc114152385063ef07927e37d71f0c660225cf

---


# Configuring Campaign-Points of Interest data integration{#configuring-campaign-points-of-interest-data-integration}

## Configuring Campaign-Points of Interest data integration using SDK V4 {#configuring-campaign-poi-sdkv4}

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

Para utilizar la función de datos de Punto de interés con aplicaciones móviles configuradas con SDK V 4, debe:

1. Acceso a Adobe Analytics for Mobile. Consulte su contrato de licencia o póngase en contacto con su ejecutivo de cuentas de Adobe para obtener más información.
1. Configure su aplicación móvil en Adobe Campaign. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Configure su aplicación móvil en la interfaz de Adobe Mobile Services. Esto le permite garantizar que los datos recopilados por Adobe Mobile Services se envíen a Adobe Campaign. See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado desde la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Mobile Cloud Mobile en su aplicación móvil. See [Integrating the SDK into a mobile application](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Defina Puntos de interés en la interfaz de Adobe Mobile Services. See [Defining Points of Interest in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. Defina los datos que desee recopilar de los suscriptores de la aplicación móvil. See [Collecting subscribers' Points of interest data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Setting up a mobile app in Adobe Campaign using SDK V4 {#setting-up-a-mobile-app-in-campaign}

Para poder recopilar datos de puntos de interés con Adobe Campaign, debe configurar la aplicación móvil de la que Adobe Campaign recibirá datos.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Click **[!UICONTROL Create]** to set up an application.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   Do not fill in the **[!UICONTROL Device-specific settings]** section. Esto sólo se aplica a la configuración de aplicaciones que reciben notificaciones Push.

In the **[!UICONTROL Mobile application properties]** section, two URLs are listed: **[!UICONTROL Collect PII endpoint]** and **[!UICONTROL Location Services endpoint]**. Se utilizarán en la interfaz de Adobe Mobile Services. See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** La URL se utiliza para recopilar los ID de Experience Cloud y los tokens de registro de los usuarios desde la aplicación móvil cuando se inicia. Cuando un usuario inicia sesión en la aplicación utilizando credenciales como correo electrónico, nombre, apellido, etc., estos datos también se recopilan y usan para reconciliar el autentificador de registros del usuario con un perfil de Adobe Campaign.
* **[!UICONTROL Location Services endpoint]** La URL se utiliza para recopilar datos de ubicación como la latitud, la longitud y el radio de un usuario desde un punto de interés.

You can now use these values in Adobe Mobile Services to finish the configuration, as explained in the [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) section.

![](assets/poi_mobile_app_properties.png)

### Configuring a V4 mobile app in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar los datos recopilados por Adobe Mobile Services a Adobe Campaign, debe configurar los postbacks en la interfaz de Mobile Services.

You will need specific information that you can find in the mobile application parameters set in Adobe Campaign (see [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Debe tener acceso a Adobe Analytics para realizar la siguiente configuración. Si no es usuario de Adobe Analytics, póngase en contacto con su administrador de Adobe Campaign.

1. Log into [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Cree la aplicación o seleccione una existente.
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. In the **Visitor ID Service ** section, check **Enable** and select your organization from the drop-down list. Click **Save**.

   >[!CAUTION]
   >
   >Esta organización debe ser la misma que la utilizada en la instancia de Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Cree un postback.

   * Select **[!UICONTROL PII]** as the **[!UICONTROL Postback Type]**.
   * In the **[!UICONTROL URL]** field, copy the **[!UICONTROL Collect PII Endpoint]** URL from the mobile application that you configured in the Adobe Campaign interface, preceded by the server name. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

      Para iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Para Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**, seleccione cualquier evento, normalmente **[!UICONTROL Launched]** y **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Cree un segundo postback.

   * Select **[!UICONTROL Postback]** as the **[!UICONTROL Postback Type]**.
   * In the **[!UICONTROL URL]** field, copy the **[!UICONTROL Location Services Endpoint]** URL from the mobile application that you configured in the Adobe Campaign interface, preceded by the server name. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**, seleccione **[!UICONTROL campaign.test]** y **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>For detailed information on configuring postbacks, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

El kit de desarrollo de software del servicio principal de Mobile (SDK) facilita la integración de una aplicación móvil en Adobe Campaign.

This step is described in this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Defining Points of Interest in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir los puntos de interés que se utilizan para recopilar los datos de ubicación:

1. Vaya a la interfaz de Adobe Mobile Services.
1. Agregue la aplicación.

   For more information on managing applications in Mobile Services, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Defina los puntos de interés.

   For more information on managing Points of Interest, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Collecting subscribers' Points of interest data {#collecting-subscribers--points-of-interest-data}

Un recurso personalizado específico permite definir los datos que desea recopilar de los suscriptores de las aplicaciones.

This step is described in the [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) page.

## Configuring Campaign-Points of Interest data integration with Adobe Experience Platform SDKs {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Su aplicación móvil ya debe configurarse en Adobe Campaign Standard con el SDK de Adobe Experience Platform. For the detailed steps, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

Para poder utilizar los servicios de ubicación de Adobe Experience Platform con aplicaciones móviles configuradas con el SDK de Adobe Experience Platform, debe:

1. Add the **[!UICONTROL Places]** and **[!UICONTROL Places Monitor]** extensions to your mobile app configuration in Adobe Experience Platform Launch. Configure su aplicación móvil en Adobe Campaign. See [Install the Places extension in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) and [Install the Places Monitor extension in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Once your extensions are set up, create data elements within **[!UICONTROL Adobe Experience Platform Launch]** to retrieve data from these extensions.

1. Then, in **[!UICONTROL Adobe Experience Platform Launch]**, you need to create rules to support mobile use cases between Point of Interests and Adobe Campaign.\
   This rule will be triggered when a user enters a geo-fenced **[!UICONTROL Point of Interest]**. Refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#Locationpostback) to create your rule.

1. Definición de puntos de interés en Lugares. See [Create a Point of Interest](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Accessing mobile apps used to collect location data {#accessing-mobile-apps-used-to-collect-location-data}

Para acceder a las aplicaciones creadas correctamente en Adobe Campaign:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** or **[!UICONTROL Mobile app (AEP SDK)]** depending on the SDK.
1. Seleccione una aplicación móvil de la lista para mostrar sus propiedades.

   ![](assets/poi_mobile_app_subscribers.png)

También se muestra una lista de suscriptores de la aplicación. Los suscriptores son todos los usuarios que han instalado la aplicación en su dispositivo móvil. Los perfiles de la base de datos de Adobe Campaign se identifican con un distintivo de registro.

## Accessing collected location data {#accessing-collected-location-data}

Once the setup is done, the collected Points of Interest data is listed in the **[!UICONTROL Places]** tab of each profile. Para acceder a la lista:

1. Seleccione un perfil.
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Select the **[!UICONTROL Places]** tab.

   ![](assets/poi_profile_places.png)

Se enumeran los datos de Puntos de interés recopilados para el perfil actual. Los datos de ubicación se almacenan en la base de datos de Adobe Campaign durante seis meses.

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/about-profiles.md).

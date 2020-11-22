---
solution: Campaign Standard
product: campaign
title: Configuración de la integración de Campaign con datos de Puntos de interés
description: Obtenga información sobre cómo configurar la función de datos Puntos de interés en Adobe Campaign para enviar mensajes personalizados en función de la ubicación de los suscriptores.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# Configuración de la integración de Campaign con datos de Puntos de interés{#configuring-campaign-points-of-interest-data-integration}

## Configuración de la integración de datos de puntos de interés de Campaña con SDK de Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>La aplicación móvil ya debe configurarse en Adobe Campaign Standard mediante el SDK de Adobe Experience Platform. For the detailed steps, refer to this [page](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

Las aplicaciones móviles utilizadas para recopilar datos de ubicación deben ser configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para poder utilizar Adobe Experience Platform Location Services con aplicaciones móviles configuradas con Adobe Experience Platform SDK, debe:

1. Añada las **[!UICONTROL Places]** extensiones y **[!UICONTROL Places Monitor]** a la configuración de la aplicación móvil en Adobe Experience Platform Launch. Configure la aplicación móvil en Adobe Campaign. Consulte [Instalar la extensión Places en Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) e [Instalar la extensión Places Monitor en Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. Una vez configuradas las extensiones, cree los elementos de datos en **[!UICONTROL Adobe Experience Platform Launch]** para recuperar datos de estas extensiones. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) para crear los elementos de datos.

1. A continuación, en **[!UICONTROL Adobe Experience Platform Launch]** la , debe crear reglas para admitir casos de uso móvil entre el punto de interés y Adobe Campaign.\
   Esta regla se activará cuando un usuario entre en una **[!UICONTROL Point of Interest]** valla geográfica. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) para crear la regla.

1. Defina su **[!UICONTROL Points of Interest]** en Lugares. Consulte [Creación de un punto de interés](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a las aplicaciones móviles utilizadas para recopilar datos](#accessing-mobile-apps-used-to-collect-location-data) de ubicación y [Acceso a los datos](#accessing-collected-location-data)de ubicación recopilados.

## Configuración de la integración de datos de puntos de interés de Campaña mediante el SDK V4 {#configuring-campaign-poi-sdkv4}

Las aplicaciones móviles utilizadas para recopilar datos de ubicación deben ser configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para utilizar la función de datos del punto de interés con aplicaciones móviles configuradas con SDK V4, debe:

1. Tener acceso a Adobe Analytics for Mobile. Consulte su contrato de licencia o póngase en contacto con su ejecutivo de cuentas de Adobe para obtener más información.
1. Configure la aplicación móvil en Adobe Campaign. Consulte [Configuración de una aplicación móvil en Campaña](#setting-up-a-mobile-app-in-campaign).
1. Configure la aplicación móvil en la interfaz de Adobe Mobile Services. Esto le permite asegurarse de que los datos recopilados por Adobe Mobile Services se envían a Adobe Campaign. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado de la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Experience Cloud Mobile en la aplicación móvil. Consulte [Integración del SDK en una aplicación](#integrating-the-sdk-into-a-mobile-application)móvil.

1. Definir puntos de interés en la interfaz de Adobe Mobile Services. Consulte [Definición de puntos de interés en Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Defina los datos que desea recopilar de los suscriptores de la aplicación móvil. Consulte [Recopilación de datos](#collecting-subscribers--points-of-interest-data)de puntos de interés de los suscriptores.
1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a las aplicaciones móviles utilizadas para recopilar datos](#accessing-mobile-apps-used-to-collect-location-data) de ubicación y [Acceso a los datos](#accessing-collected-location-data)de ubicación recopilados.

### Configuración de una aplicación móvil en Adobe Campaign mediante SDK V4 {#setting-up-a-mobile-app-in-campaign}

Para poder recopilar datos de puntos de interés con Adobe Campaign, debe configurar la aplicación móvil desde la que Adobe Campaign recibirá datos.

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Haga clic en **[!UICONTROL Create]** para configurar una aplicación.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   No rellene la **[!UICONTROL Device-specific settings]** sección. Esto solo se aplica a la configuración de aplicaciones que reciben notificaciones push.

En la **[!UICONTROL Mobile application properties]** sección, se enumeran dos direcciones URL: **[!UICONTROL Collect PII endpoint]** y **[!UICONTROL Location Services endpoint]**. Se utilizarán en la interfaz de Adobe Mobile Services. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* La **[!UICONTROL Collect PII endpoint]** URL se utiliza para recopilar los ID de Experience Cloud y los tokens de registro de los usuarios desde la aplicación móvil cuando se inicia. Cuando un usuario inicia sesión en la aplicación con credenciales como correo electrónico, nombre, apellidos, etc., estos datos también se recopilan y utilizan para reconciliar el token de registro del usuario con un perfil de Adobe Campaign.
* La dirección URL se utiliza para recopilar datos de ubicación, como la latitud, la longitud y el radio del usuario desde un punto de interés. **[!UICONTROL Location Services endpoint]**

Ahora puede utilizar estos valores en Adobe Mobile Services para finalizar la configuración, tal como se explica en la sección [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Configuración de una aplicación móvil V4 en Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar los datos recopilados por Adobe Mobile Services a Adobe Campaign, debe configurar postbacks en la interfaz de Mobile Services.

Necesitará información específica que puede encontrar en los parámetros de la aplicación móvil establecidos en Adobe Campaign (consulte [Configuración de una aplicación móvil en Campaña](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Debe tener acceso a Adobe Analytics para realizar la siguiente configuración. Si no es un usuario de Adobe Analytics, póngase en contacto con el administrador de Adobe Campaign.

1. Inicie sesión en [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Cree la aplicación o seleccione una existente.
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. En la sección Servicio **de ID de** Visitante, marque **Habilitar** y seleccione su organización en la lista desplegable. Haga clic en **Save**.

   >[!CAUTION]
   >
   >Esta organización debe ser la misma que la que se usa en la instancia de Adobe Campaign.

1. Haga clic en **[!UICONTROL Manage Postbacks]**.
1. Cree un postback.

   * Seleccione **[!UICONTROL PII]** como **[!UICONTROL Postback Type]**.
   * En el **[!UICONTROL URL]** campo, copie la **[!UICONTROL Collect PII Endpoint]** URL de la aplicación móvil configurada en la interfaz de Adobe Campaign, precedida por el nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaña](#setting-up-a-mobile-app-in-campaign).
   * Rellene el **[!UICONTROL Post Body]** campo como se indica a continuación:

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

   * Configure **Content Type** como **[!UICONTROL application/json]**.
   * En el **¿Qué etiquetas de datos activan el postback?**, seleccione cualquier evento, normalmente **[!UICONTROL Launched]** y **[!UICONTROL exists]**.
   * Haga clic en **[!UICONTROL Save & Activate]**.

1. Cree un segundo postback.

   * Seleccione **[!UICONTROL Postback]** como **[!UICONTROL Postback Type]**.
   * En el **[!UICONTROL URL]** campo, copie la **[!UICONTROL Location Services Endpoint]** URL de la aplicación móvil configurada en la interfaz de Adobe Campaign, precedida por el nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaña](#setting-up-a-mobile-app-in-campaign).
   * Rellene el **[!UICONTROL Post Body]** campo como se indica a continuación:

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

   * Configure **Content Type** como **[!UICONTROL application/json]**.
   * En el **¿Qué etiquetas de datos activan el postback?**, seleccione **[!UICONTROL campaign.test]** y **[!UICONTROL exists]**.
   * Haga clic en **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Para obtener información detallada sobre la configuración de postbacks, consulte la documentación [de](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)Adobe Mobile Services.

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

El kit de desarrollo de software (SDK) del servicio principal de Mobile facilita la integración de una aplicación móvil en Adobe Campaign.

Este paso se describe en esta [página](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html).

### Definición de puntos de interés en Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir los puntos de interés que se utilizan para recopilar datos de ubicación:

1. Vaya a la interfaz de Adobe Mobile Services.
1. Añada la aplicación.

   Para obtener más información sobre la administración de aplicaciones en Mobile Services, consulte la documentación [de](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)Adobe Mobile Services.

1. Defina los puntos de interés.

   Para obtener más información sobre la administración de puntos de interés, consulte la documentación [de](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)Adobe Mobile Services.

### Recopilación de datos de puntos de interés de los suscriptores {#collecting-subscribers--points-of-interest-data}

Un recurso personalizado específico le permite definir los datos que desea recopilar de los suscriptores de sus aplicaciones.

Este paso se describe en la página [Configuración de una aplicación móvil mediante SDK V4](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) .


## Acceso a las aplicaciones móviles utilizadas para recopilar datos de ubicación {#accessing-mobile-apps-used-to-collect-location-data}

Para acceder a las aplicaciones creadas correctamente en Adobe Campaign:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** según el SDK.
1. Seleccione una aplicación móvil de la lista para mostrar sus propiedades.

   ![](assets/poi_mobile_app_subscribers.png)

En la **[!UICONTROL Mobile application subscribers]** ficha también se muestra una lista de los suscriptores de la aplicación. Los suscriptores son todos los usuarios que han instalado la aplicación en su dispositivo móvil. Los perfiles de la base de datos de Adobe Campaign se identifican con un token de registro.

## Acceso a los datos de ubicación recopilados {#accessing-collected-location-data}

Una vez finalizada la configuración, los datos recopilados de Puntos de interés se muestran en la **[!UICONTROL Places]** ficha de cada perfil. Para acceder a la lista:

1. Seleccione un perfil.
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Seleccione la pestaña **[!UICONTROL Places]** .

   ![](assets/poi_profile_places.png)

Se muestran los datos recopilados de Puntos de interés para el perfil actual. Los datos de ubicación se almacenan en la base de datos de Adobe Campaign durante seis meses.

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Perfiles](../../audiences/using/about-profiles.md).

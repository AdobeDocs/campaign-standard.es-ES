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
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# Configuración de la integración de datos de puntos de interés de los puntos de interés{#configuring-campaign-points-of-interest-data-integration}

## Configuración de la integración de datos de puntos de interés con los SDK de Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Su aplicación móvil ya debe configurarse en Adobe Campaign Standard con el SDK de Adobe Experience Platform. Para obtener los pasos detallados, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Las aplicaciones móviles utilizadas para recopilar los datos de ubicación deben ser configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para poder utilizar los servicios de ubicación de Adobe Experience Platform con aplicaciones móviles configuradas con el SDK de Adobe Experience Platform, debe:

1. Agregue las **[!UICONTROL Places]****[!UICONTROL Places Monitor]** extensiones y la extensión a la configuración de la aplicación móvil en Adobe Experience Platform Launch. Configure su aplicación móvil en Adobe Campaign. Consulte [Instalación de la extensión Lugares en Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) e [Instalación de la extensión Places Monitor en Launch Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Una vez configuradas las extensiones, cree elementos de datos dentro **[!UICONTROL Adobe Experience Platform Launch]** de para recuperar datos de estas extensiones. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) para crear los elementos de datos.

1. A continuación, **[!UICONTROL Adobe Experience Platform Launch]** debe crear reglas para admitir los casos de uso móvil entre puntos de interés y Adobe Campaign.\
   Esta regla se desencadena cuando un usuario introduce una dimensión geográfica **[!UICONTROL Point of Interest]**. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) para crear la regla.

1. Defina su **[!UICONTROL Points of Interest]** en Lugares. Consulte [Creación de un punto de interés](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a aplicaciones móviles utilizadas para recopilar datos](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) de ubicación y [Acceso a los datos de ubicación recopilados](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Configuración de la integración de datos de puntos de interés de interés mediante SDK V 4 {#configuring-campaign-poi-sdkv4}

Las aplicaciones móviles utilizadas para recopilar los datos de ubicación deben ser configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para utilizar la función de datos de Punto de interés con aplicaciones móviles configuradas con SDK V 4, debe:

1. Acceso a Adobe Analytics for Mobile. Consulte su contrato de licencia o póngase en contacto con su ejecutivo de cuentas de Adobe para obtener más información.
1. Configure su aplicación móvil en Adobe Campaign. Consulte [Configuración de una aplicación móvil en Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Configure su aplicación móvil en la interfaz de Adobe Mobile Services. Esto le permite garantizar que los datos recopilados por Adobe Mobile Services se envíen a Adobe Campaign. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado desde la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Mobile Cloud Mobile en su aplicación móvil. Consulte [Integración del SDK en una aplicación móvil](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Defina Puntos de interés en la interfaz de Adobe Mobile Services. Consulte [Definición de puntos de interés en Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. Defina los datos que desee recopilar de los suscriptores de la aplicación móvil. Consulte [Recopilación de datos de interés de los suscriptores](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a aplicaciones móviles utilizadas para recopilar datos](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) de ubicación y [Acceso a los datos de ubicación recopilados](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Configuración de una aplicación móvil en Adobe Campaign mediante SDK V 4 {#setting-up-a-mobile-app-in-campaign}

Para poder recopilar datos de puntos de interés con Adobe Campaign, debe configurar la aplicación móvil de la que Adobe Campaign recibirá datos.

1. Haga clic en **[!UICONTROL Adobe Campaign]** el logotipo, en la esquina superior izquierda, y seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Haga clic en **[!UICONTROL Create]** para configurar una aplicación.
1. Introduzca un nombre en **[!UICONTROL Application name]** el campo y haga clic **[!UICONTROL Create]** en.

   No rellene la **[!UICONTROL Device-specific settings]** sección. Esto sólo se aplica a la configuración de aplicaciones que reciben notificaciones Push.

En **[!UICONTROL Mobile application properties]** la sección, se enumeran dos direcciones URL: **[!UICONTROL Collect PII endpoint]** y **[!UICONTROL Location Services endpoint]**. Se utilizarán en la interfaz de Adobe Mobile Services. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** La URL se utiliza para recopilar los ID de Experience Cloud y los tokens de registro de los usuarios desde la aplicación móvil cuando se inicia. Cuando un usuario inicia sesión en la aplicación utilizando credenciales como correo electrónico, nombre, apellido, etc., estos datos también se recopilan y usan para reconciliar el autentificador de registros del usuario con un perfil de Adobe Campaign.
* **[!UICONTROL Location Services endpoint]** La URL se utiliza para recopilar datos de ubicación como la latitud, la longitud y el radio de un usuario desde un punto de interés.

Ahora puede utilizar estos valores en Adobe Mobile Services para finalizar la configuración, según se explica en [Configuración de una aplicación móvil en Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Configuración de una aplicación móvil V 4 en Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar los datos recopilados por Adobe Mobile Services a Adobe Campaign, debe configurar los postbacks en la interfaz de Mobile Services.

Necesitará información específica que puede encontrar en los parámetros de aplicación móvil establecidos en Adobe Campaign (consulte [Configuración de una aplicación móvil en Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Debe tener acceso a Adobe Analytics para realizar la siguiente configuración. Si no es usuario de Adobe Analytics, póngase en contacto con su administrador de Adobe Campaign.

1. Inicie sesión en [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Cree la aplicación o seleccione una existente.
1. Vaya a **[!UICONTROL Manage App Settings]** la página.
1. En **la sección Servicio** de ID de visitante, marque **Habilitar** y seleccione su organización en la lista desplegable. Haga clic **en Guardar**.

   >[!CAUTION]
   >
   >Esta organización debe ser la misma que la utilizada en la instancia de Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Cree un postback.

   * Seleccione **[!UICONTROL PII]** como **[!UICONTROL Postback Type]**.
   * En **[!UICONTROL URL]** el campo, copie **[!UICONTROL Collect PII Endpoint]** la URL desde la aplicación móvil que configuró en la interfaz de Adobe Campaign, precedido por el nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Complete **[!UICONTROL Post Body]** el campo de la siguiente manera:

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

   * Establezca **el tipo de contenido** como **[!UICONTROL application/json]**.
   * ¿En qué **etiquetas de datos activan el postback?**, seleccione cualquier evento, normalmente **[!UICONTROL Launched]** y **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Cree un segundo postback.

   * Seleccione **[!UICONTROL Postback]** como **[!UICONTROL Postback Type]**.
   * En **[!UICONTROL URL]** el campo, copie **[!UICONTROL Location Services Endpoint]** la URL desde la aplicación móvil que configuró en la interfaz de Adobe Campaign, precedido por el nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Complete **[!UICONTROL Post Body]** el campo de la siguiente manera:

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

   * Establezca **el tipo de contenido** como **[!UICONTROL application/json]**.
   * ¿En qué **etiquetas de datos activan el postback?**, seleccione **[!UICONTROL campaign.test]** y **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Para obtener información detallada sobre cómo configurar los postbacks, consulte [la documentación de Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integración del SDK en una aplicación móvil {#integrating-the-sdk-into-a-mobile-application}

El kit de desarrollo de software del servicio principal de Mobile (SDK) facilita la integración de una aplicación móvil en Adobe Campaign.

Este paso se describe en esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Definición de puntos de interés en Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir los puntos de interés que se utilizan para recopilar los datos de ubicación:

1. Vaya a la interfaz de Adobe Mobile Services.
1. Agregue la aplicación.

   Para obtener más información sobre la administración de aplicaciones en Mobile Services, consulte [la documentación de Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Defina los puntos de interés.

   Para obtener más información sobre la administración de puntos de interés, consulte [la documentación de Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Recopilación de datos de puntos de interés de los suscriptores {#collecting-subscribers--points-of-interest-data}

Un recurso personalizado específico permite definir los datos que desea recopilar de los suscriptores de las aplicaciones.

Este paso se describe en [Configuración de una aplicación móvil mediante](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) la página SDK V 4.


## Acceso a aplicaciones móviles utilizadas para recopilar datos de ubicación {#accessing-mobile-apps-used-to-collect-location-data}

Para acceder a las aplicaciones creadas correctamente en Adobe Campaign:

1. Haga clic en **[!UICONTROL Adobe Campaign]** el logotipo, en la esquina superior izquierda.
1. Seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** según el SDK.
1. Seleccione una aplicación móvil de la lista para mostrar sus propiedades.

   ![](assets/poi_mobile_app_subscribers.png)

También se muestra una lista de los suscriptores de la aplicación en **[!UICONTROL Mobile application subscribers]** la ficha. Los suscriptores son todos los usuarios que han instalado la aplicación en su dispositivo móvil. Los perfiles de la base de datos de Adobe Campaign se identifican con un distintivo de registro.

## Acceso a los datos de ubicación recopilados {#accessing-collected-location-data}

Una vez que se ha realizado la configuración, los datos de Puntos de interés recopilados se enumeran en **[!UICONTROL Places]** la ficha de cada perfil. Para acceder a la lista:

1. Seleccione un perfil.
1. Haga clic en **[!UICONTROL Edit profile properties]** el botón de la derecha.
1. Seleccione **[!UICONTROL Places]** la ficha.

   ![](assets/poi_profile_places.png)

Se enumeran los datos de Puntos de interés recopilados para el perfil actual. Los datos de ubicación se almacenan en la base de datos de Adobe Campaign durante seis meses.

Para obtener más información sobre cómo acceder y editar perfiles, consulte [Perfiles](../../audiences/using/about-profiles.md).

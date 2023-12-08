---
title: Configuración de la integración de Campaign con datos de Puntos de interés
description: Aprenda a configurar la función de datos de puntos de interés en Adobe Campaign para enviar mensajes personalizados según la ubicación de los suscriptores.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 2%

---

# Configuración de la integración de Campaign con datos de Puntos de interés{#configuring-campaign-points-of-interest-data-integration}

## Configuración de la integración de Campaign con datos de Puntos de interés con SDK de Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>La aplicación móvil ya debe estar configurada en Adobe Campaign Standard mediante el SDK para Adobe Experience Platform. Para ver los pasos detallados, consulte esto [página](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

Las aplicaciones móviles utilizadas para recopilar datos de ubicación deben estar configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para poder utilizar los servicios de ubicación de Adobe Experience Platform con aplicaciones móviles configuradas con el SDK de Adobe Experience Platform, debe:

1. Añada el **[!UICONTROL Places]** extensión a la configuración de la aplicación móvil en la IU de recopilación de datos. Configure la aplicación móvil en Adobe Campaign. Consulte [Instalación de la extensión Places](https://developer.adobe.com/client-sdks/solution/places).

1. Una vez configuradas las extensiones, cree elementos de datos en la IU de recopilación de datos para recuperar datos de estas extensiones. Consulte esta sección [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) para crear los elementos de datos.

1. A continuación, en la IU de recopilación de datos, debe crear reglas para admitir casos de uso móvil entre el punto de interés y Adobe Campaign.\
   Esta regla se activará cuando un usuario entre en un límite geográfico **[!UICONTROL Point of Interest]**. Consulte esta sección [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) para crear la regla.

1. Defina su **[!UICONTROL Points of Interest]** en Sitios. Consulte [Creación de un punto de interés](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a aplicaciones móviles utilizadas para recopilar datos de ubicación](#accessing-mobile-apps-used-to-collect-location-data) y [Acceso a los datos de ubicación recopilados](#accessing-collected-location-data).

## Configuración de la integración de Campaign con datos de Puntos de interés mediante SDK V4 {#configuring-campaign-poi-sdkv4}

Las aplicaciones móviles utilizadas para recopilar datos de ubicación deben estar configuradas por un **administrador** en la interfaz de Adobe Campaign.

Para utilizar la función de datos del punto de interés con aplicaciones móviles configuradas con el SDK V4, debe:

1. Tener acceso a Adobe Analytics para dispositivos móviles. Consulte el acuerdo de licencia o póngase en contacto con el administrador de cuentas de Adobe para obtener más información.
1. Configure la aplicación móvil en Adobe Campaign. Consulte [Configuración de una aplicación móvil en Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configure la aplicación móvil en la interfaz de Adobe Mobile Services. Esto le permite asegurarse de que los datos recopilados por Adobe Mobile Services se envían a Adobe Campaign. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado de la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integración del SDK de Experience Cloud Mobile en la aplicación móvil. Consulte [Integración del SDK en una aplicación móvil](#integrating-the-sdk-into-a-mobile-application).

1. Defina los puntos de interés en la interfaz de Adobe de Mobile Services. Consulte [Definición de puntos de interés en Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Defina los datos que desea recopilar de los suscriptores de la aplicación móvil. Consulte [Recopilación de datos de puntos de interés de suscriptores](#collecting-subscribers--points-of-interest-data).
1. Asegúrese de acceder a la aplicación móvil y a los datos de ubicación recopilados en Adobe Campaign. Consulte [Acceso a aplicaciones móviles utilizadas para recopilar datos de ubicación](#accessing-mobile-apps-used-to-collect-location-data) y [Acceso a los datos de ubicación recopilados](#accessing-collected-location-data).

### Configuración de una aplicación móvil en Adobe Campaign mediante el SDK V4 {#setting-up-a-mobile-app-in-campaign}

Para poder recopilar datos de puntos de interés con Adobe Campaign, debe configurar la aplicación móvil desde la que Adobe Campaign recibirá los datos.

1. Haga clic en **Adobe** , en la esquina superior izquierda, y seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Clic **[!UICONTROL Create]** para configurar una aplicación.
1. Introduzca un nombre en la **[!UICONTROL Application name]** y haga clic en **[!UICONTROL Create]**.

   No rellene el **[!UICONTROL Device-specific settings]** sección. Esto solo se aplica a la configuración de aplicaciones que reciben notificaciones push.

En el **[!UICONTROL Mobile application properties]** , se muestran dos direcciones URL: **[!UICONTROL Collect PII endpoint]** y **[!UICONTROL Location Services endpoint]**. Se utilizarán en la interfaz de Adobe de Mobile Services. Consulte [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* El **[!UICONTROL Collect PII endpoint]** La URL se utiliza para recopilar los ID de Experience Cloud y los tokens de registro de los usuarios de la aplicación móvil cuando se inicia. Cuando un usuario inicia sesión en la aplicación con credenciales como correo electrónico, nombre, apellidos, etc., estos datos también se recopilan y se utilizan para reconciliar el token de registro del usuario con un perfil de Adobe Campaign.
* El **[!UICONTROL Location Services endpoint]** La URL se utiliza para recopilar datos de ubicación, como la latitud, longitud y radio de un usuario, desde un punto de interés.

Ahora puede utilizar estos valores en Adobe Mobile Services para finalizar la configuración, como se explica en la sección [Configuración de una aplicación móvil en Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) sección.

![](assets/poi_mobile_app_properties.png)

### Configuración de una aplicación móvil V4 en Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar los datos recopilados por Adobe Mobile Services a Adobe Campaign, debe configurar los postbacks en la interfaz de Mobile Services.

Necesitará información específica que puede encontrar en los parámetros de la aplicación móvil establecidos en Adobe Campaign (consulte [Configuración de una aplicación móvil en Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Debe tener acceso a Adobe Analytics para realizar la siguiente configuración. Si no es usuario de Adobe Analytics, póngase en contacto con el administrador de Adobe Campaign.

1. Iniciar sesión en [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Cree la aplicación o seleccione una existente.
1. Vaya a la página **[!UICONTROL Manage App Settings]**.
1. En el **Servicio de ID de visitante** , marque **Activar** y seleccione su organización en la lista desplegable. Haga clic en **Guardar**.

   >[!CAUTION]
   >
   >Esta organización debe ser la misma que utiliza en la instancia de Adobe Campaign.

1. Haga clic en **[!UICONTROL Manage Postbacks]**.
1. Cree un postback.

   * Seleccionar **[!UICONTROL PII]** como el **[!UICONTROL Postback Type]**.
   * En el **[!UICONTROL URL]** , copie el **[!UICONTROL Collect PII Endpoint]** URL de la aplicación móvil configurada en la interfaz de Adobe Campaign, precedida del nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaign](#setting-up-a-mobile-app-in-campaign).
   * Rellene el **[!UICONTROL Post Body]** como se indica a continuación:

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

   * Establecer **Tipo de contenido** as **[!UICONTROL application/json]**.
   * En el **¿Qué etiquetas de datos almacenan en Déclencheur el Postback?**, seleccione cualquier evento, normalmente **[!UICONTROL Launched]** y **[!UICONTROL exists]**.
   * Haga clic en **[!UICONTROL Save & Activate]**.

1. Cree un segundo postback.

   * Seleccionar **[!UICONTROL Postback]** como el **[!UICONTROL Postback Type]**.
   * En el **[!UICONTROL URL]** , copie el **[!UICONTROL Location Services Endpoint]** URL de la aplicación móvil configurada en la interfaz de Adobe Campaign, precedida del nombre del servidor. Consulte [Configuración de una aplicación móvil en Campaign](#setting-up-a-mobile-app-in-campaign).
   * Rellene el **[!UICONTROL Post Body]** como se indica a continuación:

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

   * Establecer **Tipo de contenido** as **[!UICONTROL application/json]**.
   * En el **¿Qué etiquetas de datos almacenan en Déclencheur el Postback?**, seleccione **[!UICONTROL campaign.test]** y **[!UICONTROL exists]**.
   * Haga clic en **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Para obtener información detallada sobre la configuración de los postbacks, consulte [Documentación de Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### Integración del SDK en una aplicación móvil {#integrating-the-sdk-into-a-mobile-application}

El kit de desarrollo de software (SDK) del servicio principal de Mobile facilita la integración de una aplicación móvil en Adobe Campaign.

Este paso se describe en la siguiente sección [página](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html).

### Definición de puntos de interés en Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir los puntos de interés que se utilizan para recopilar datos de ubicación:

1. Vaya a la interfaz de Adobe Mobile Services.
1. Añada la aplicación.

   Para obtener más información sobre la administración de aplicaciones en Mobile Services, consulte la [Documentación de Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Defina los puntos de interés.

   Para obtener más información sobre la administración de puntos de interés, consulte la [Documentación de Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### Recopilación de datos de puntos de interés de suscriptores {#collecting-subscribers--points-of-interest-data}

Un recurso personalizado específico permite definir los datos que desea recopilar de los suscriptores de las aplicaciones.

Este paso se describe en la [Configuración de una aplicación móvil mediante el SDK V4](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) página.

## Acceso a aplicaciones móviles utilizadas para recopilar datos de ubicación {#accessing-mobile-apps-used-to-collect-location-data}

Para acceder a las aplicaciones creadas correctamente en Adobe Campaign:

1. Haga clic en **Adobe** en la esquina superior izquierda.
1. Seleccionar **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** en función del SDK.
1. Seleccione una aplicación móvil de la lista para mostrar sus propiedades.

   ![](assets/poi_mobile_app_subscribers.png)

También se muestra una lista de los suscriptores de la aplicación en la **[!UICONTROL Mobile application subscribers]** pestaña. Los suscriptores son todos los usuarios que han instalado la aplicación en su dispositivo móvil. Los perfiles de la base de datos de Adobe Campaign se identifican con un token de registro.

## Acceso a los datos de ubicación recopilados {#accessing-collected-location-data}

Una vez completada la configuración, los datos de puntos de interés recopilados se enumeran en la **[!UICONTROL Places]** de cada perfil. Para acceder a la lista:

1. Seleccione un perfil.
1. Haga clic en **[!UICONTROL Edit profile properties]** botón a la derecha.
1. Seleccione la pestaña **[!UICONTROL Places]** .

   ![](assets/poi_profile_places.png)

Se muestran los datos recopilados de puntos de interés del perfil actual. Los datos de ubicación se almacenan en la base de datos de Adobe Campaign durante seis meses.

Para obtener más información sobre el acceso y la edición de perfiles, consulte [Perfiles](../../audiences/using/about-profiles.md).

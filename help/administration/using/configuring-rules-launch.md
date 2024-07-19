---
title: Configuración de reglas de etiquetas para admitir casos de uso de Adobe Campaign Standard
description: Obtenga información sobre cómo configurar reglas de etiquetas para admitir casos de uso de Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Configuración de reglas de etiquetas para admitir casos de uso de Adobe Campaign Standard {#configuring-rules-launch}

En la interfaz de usuario de recopilación de datos, cree elementos de datos y reglas para enviar PII y otros datos desde aplicaciones móviles a [!DNL Adobe Campaign Standard].

Para garantizar que todos los cambios de configuración en la IU de recopilación de datos surtan efecto, debe publicarlos. Para obtener más información, consulte [Publicación](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Para crear reglas en la IU de recopilación de datos, siga estos pasos:

1. [Creación de elementos de datos](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creando reglas](../../administration/using/configuring-rules-launch.md#create-data-elements) para los casos de uso que desea admitir:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de seguimiento en la aplicación](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback de seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de ubicación](../../administration/using/configuring-rules-launch.md#location-postback)

## Creación de elementos de datos {#create-data-elements}

Estos son los elementos de datos que recomendamos crear en la IU de recopilación de datos.
Puede crear elementos de datos adicionales según sus necesidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para crear estos elementos de datos:

1. En la IU de recopilación de datos, en el panel de aplicaciones móviles, haga clic en la pestaña **[!UICONTROL Data Elements]**.

1. Para crear el elemento de datos **[!UICONTROL Experience Cloud ID]**, haga clic en **[!UICONTROL Create New Data Element]**.

1. En el campo **[!UICONTROL Name]**, por ejemplo, escriba **mcid**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. Luego **[!UICONTROL Experience Cloud ID]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Para crear el elemento de datos Pkey, haga clic en **[!UICONTROL Add data element]**.

1. En el campo **[!UICONTROL Name]**, por ejemplo, escriba **pkey**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. Luego **[!UICONTROL pkey]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

1. Para crear el elemento de datos del servidor de Campaign, haga clic en **[!UICONTROL Add data element]**.

1. En el campo **[!UICONTROL Name]**, escriba un nombre, por ejemplo, **camp-server**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL Campaign Server]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

## Creación de reglas {#creating-rules}

Debe crear reglas para lo siguiente:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de seguimiento en la aplicación](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de ubicación](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Para enviar información PII de una aplicación móvil a Adobe Campaign, debe implementar una API de SDK. Para obtener más información, ve a [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

Para enviar datos PII a [!DNL Adobe Campaign Standard], cree una regla en la IU de recopilación de datos:

1. En la IU de recopilación de datos, en el panel de aplicaciones móviles, haga clic en la pestaña **[!UICONTROL Rules]** y luego en **[!UICONTROL Create New Rule]**.

1. Escriba un nombre, por ejemplo, **Mobile Core - Recopilar PII**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Collect PII]** en la lista desplegable **[!UICONTROL Event type]**.

1. Haga clic en **[!UICONTROL Keep changes]**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send PII]** en la lista desplegable **[!UICONTROL Action type]**.

1. En **[!UICONTROL URL]**, escriba la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add Post Body]**.

1. En **[!UICONTROL Post Body]**, escriba lo siguiente:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   MarketingCloudId permite reconciliar a los suscriptores de la aplicación con los destinatarios de la base de datos y, como resultado, es obligatorio. Puede especificar otros pares clave-valor según sus necesidades comerciales. En el ejemplo anterior, se están pasando el correo electrónico, el nombre y los apellidos desde la aplicación.

   Las claves (por ejemplo cusEmail, cusFirstName y cusLastName) deben coincidir con los ID de campo definidos en el recurso personalizado en la instancia de Adobe Campaign Standard. Las variables de valor (por ejemplo email, firstName y LastName) deben coincidir con las claves de los datos JSON enviados desde la aplicación móvil al llamar a la API collectPII de AMS desde el código de la aplicación.

   También puede pasar datos del ciclo vital en el postback Recopilar PII o un postback diferente según los déclencheur del evento. A continuación, se muestra un ejemplo del JSON de datos del ciclo vital:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Los elementos de datos definidos en la IU de recopilación de datos deben incluirse en porcentajes dobles, por ejemplo `%%mcid%%`, y las variables de contexto de la aplicación deben incluirse en porcentajes únicos, por ejemplo %contextdata.email%.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 0.

   ![](assets/do-not-localize/rules_2.png)

Los datos de usuario ahora están configurados para enviarse a Campaign.

### Postback de seguimiento en la aplicación {#inapp-tracking-postback}

>[!NOTE]
>
>Si utiliza Android ACPCore v1.4.0 o posterior/ iOS ACPCore v2.3.0 o posterior, no es necesario configurar los postbacks de seguimiento.

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard] con el fin de generar informes sobre cómo los usuarios interactúan con los mensajes en la aplicación móvil, cree la regla siguiente en la interfaz de usuario de la recopilación de datos:

1. En la IU de recopilación de datos, en el panel de aplicaciones móviles, seleccione la pestaña **[!UICONTROL Rules]** y haga clic en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Adobe Campaign - Rastreo de clics en la aplicación**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL In-App click tracking]** en la lista desplegable **[!UICONTROL Event type]**.

1. Haga clic en **[!UICONTROL Keep changes]**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la lista desplegable **[!UICONTROL Event type]**.

1. En **[!UICONTROL URL]**, escriba la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add post body]**.

1. En **[!UICONTROL Post Body]**, escriba **{}**.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback de seguimiento de notificaciones push {#push-tracking-postback}

>[!NOTE]
>
>Si utiliza Android ACPCore v1.4.0 o posterior/ iOS ACPCore v2.3.0 o posterior, no es necesario configurar los postbacks de seguimiento.

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard], lo que ayuda a realizar un seguimiento de las entregas de notificaciones push y de la interacción de los usuarios con la aplicación móvil, debe crear una regla en la IU de recopilación de datos.

Para obtener más información sobre el seguimiento push, consulte [Seguimiento push](../../administration/using/push-tracking.md).

Para realizar un seguimiento de las acciones de la aplicación, utilice la API trackAction. Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. En la IU de recopilación de datos, en el panel de aplicaciones móviles, haga clic en la pestaña **[!UICONTROL Rules]** y luego en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Adobe Campaign - rastreo de clics push**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Track Action]** en la lista desplegable **[!UICONTROL Event type]**.

1. En la lista desplegable **[!UICONTROL Action]**, seleccione **[!UICONTROL Action]**, seleccione **[!UICONTROL equals]** y escriba **seguimiento**.

1. Haga clic en **[!UICONTROL Keep changes]**. A continuación, en la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la lista desplegable **[!UICONTROL Action type]**.

1. En **[!UICONTROL URL]**, escriba la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add post body]**.

1. Agregue el cuerpo del anuncio, por ejemplo, { }.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 0.

### Postback de ubicación {#location-postback}

1. En la IU de recopilación de datos, en el panel de aplicaciones móviles, haga clic en la pestaña **[!UICONTROL Rules]** y luego en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Ubicación postback**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. Cree un evento, por ejemplo, Introducir punto de interés o Salida de punto de interés. En la lista desplegable **[!UICONTROL Extension]**, seleccione **Places - Beta**. A continuación, **Escriba el punto de interés** o **salga del punto de interés** en la lista desplegable **[!UICONTROL Event type]**.

1. Escriba un nombre, por ejemplo, **Places - Beta - Escriba el punto de interés** o **Punto de interés de salida**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. En la lista desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. Luego **[!UICONTROL Send postback]** de la lista desplegable **[!UICONTROL Action type]**.

1. Escriba un nombre, por ejemplo, **Núcleo móvil - Enviar ubicación Postback**.

1. En **[!UICONTROL URL]**, escriba la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add post body]** y agregue el cuerpo del anuncio, por ejemplo:

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >En el ejemplo anterior, los elementos de datos del lado derecho deben configurarse en la IU de recopilación de datos aprovechando los pasos de [Creación de elementos de datos](../../administration/using/configuring-rules-launch.md#create-data-elements). Los elementos de datos del lado izquierdo son compatibles con [!DNL Adobe Campaign Standard] y no necesitan ninguna configuración. Si necesita datos adicionales, debe realizar extensiones de recursos personalizadas en [!DNL Adobe Campaign Standard].

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 5.

   ![](assets/do-not-localize/rules_4.png)

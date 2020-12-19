---
solution: Campaign Standard
product: campaign
title: Configuración de reglas de Adobe Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard
description: Configuración de reglas de Adobe Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 5%

---


# Configuración de reglas de Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard {#configuring-rules-launch}

En [!DNL Adobe Experience Platform Launch], debe crear elementos de datos y reglas para enviar PII y otros datos desde aplicaciones móviles a [!DNL Adobe Campaign Standard].

Para asegurarse de que todos los cambios de configuración de [!DNL Adobe Experience Platform Launch] surten efecto, debe publicar estos cambios. Para obtener más información, consulte [Publicación](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Para crear reglas en [!DNL Experience Platform Launch], siga estos pasos:

1. [Creación de elementos de datos](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creación de ](../../administration/using/configuring-rules-launch.md#create-data-elements) reglas para casos de uso que desee admitir:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de seguimiento en la aplicación](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback del seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de ubicación](../../administration/using/configuring-rules-launch.md#location-postback)

## Creación de elementos de datos {#create-data-elements}

Estos son los elementos de datos que recomendamos crear en [!DNL Experience Platform Launch].
Puede crear elementos de datos adicionales según sus necesidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para crear estos elementos de datos:

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, haga clic en la ficha **[!UICONTROL Data Elements]**.

1. Para crear el elemento de datos **[!UICONTROL Experience Cloud ID]**, haga clic en **[!UICONTROL Create New Data Element]**.

1. En el campo **[!UICONTROL Name]**, por ejemplo, escriba **mcid**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Experience Cloud ID]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Para crear el elemento de datos Pkey, haga clic en **[!UICONTROL Add data element]**.

1. En el campo **[!UICONTROL Name]**, por ejemplo, escriba **pkey**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL pkey]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

1. Para crear el elemento de datos del servidor de Campaña, haga clic en **[!UICONTROL Add data element]**.

1. En el campo **[!UICONTROL Name]**, escriba un nombre, por ejemplo, **camp-server**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL Campaign Server]** en la lista desplegable de tipo **[!UICONTROL Data element]**.

## Creación de reglas {#creating-rules}

Debe crear reglas para lo siguiente:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de seguimiento en la aplicación](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback del seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de ubicación](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Para enviar información de PII desde una aplicación móvil a Adobe Campaign, debe implementar una API de SDK. Para obtener más información, vaya a [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Para enviar datos PII a [!DNL Adobe Campaign Standard], cree una regla en [!DNL Experience Platform Launch]:

1. En [!DNL Experience Platform Launch], desde el panel de la aplicación móvil, haga clic en la ficha **[!UICONTROL Rules]** y luego en **[!UICONTROL Create New Rule]**.

1. Escriba un nombre, por ejemplo, **Mobile Core - Recopilar PII**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Collect PII]** en la lista desplegable **[!UICONTROL Event type]**.

1. Haga clic en **[!UICONTROL Keep changes]**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send PII]** en la lista desplegable **[!UICONTROL Action type]**.

1. En **[!UICONTROL URL]**, introduzca la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add Post Body]**.

1. En **[!UICONTROL Post Body]**, escriba lo siguiente:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   MarketingCloudId le permite reconciliar a los suscriptores de la aplicación con los destinatarios de la base de datos y, como resultado, es necesario. Puede especificar otros pares clave-valor según sus necesidades comerciales. En el ejemplo anterior, se están pasando los mensajes de correo electrónico, nombre y apellidos desde la aplicación.

   Las claves (por ejemplo, cusEmail, cusFirstName y cusLastName) deben coincidir con los ID de campo definidos en el recurso personalizado de la instancia de Adobe Campaign Standard. Las variables de valor (por ejemplo, email, firstName y LastName) deben coincidir con las claves de los datos JSON que se envían desde la aplicación móvil mientras se llama a la API collectPII de AMS desde el código de la aplicación.

   También puede pasar datos del ciclo vital en el postback Recopilar PII o en otro postback, según los activadores de Evento. a continuación se muestra un ejemplo del JSON de datos del ciclo vital:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Los elementos de datos definidos en [!DNL Experience Platform Launch] se deben incluir en porcentajes de doble, por ejemplo %%mcid%%%, y las variables de contexto de la aplicación se deben incluir en porcentajes únicos, por ejemplo %contextdata.email%.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 0.

   ![](assets/do-not-localize/rules_2.png)

Los datos de usuario ahora están configurados para enviarse a Campaña.

### Postback de seguimiento en la aplicación {#inapp-tracking-postback}

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard] para obtener sistemas de informes sobre cómo interactúan los usuarios con los mensajes en la aplicación móvil, cree la siguiente regla en [!DNL Experience Platform Launch]:

1. En [!DNL Experience Platform Launch], desde el panel de la aplicación móvil, seleccione la ficha **[!UICONTROL Rules]** y haga clic en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Seguimiento de clics en la aplicación - Adobe Campaign**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL In-App click tracking]** en la lista desplegable **[!UICONTROL Event type]**.

1. Haga clic en **[!UICONTROL Keep changes]**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la lista desplegable **[!UICONTROL Event type]**.

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

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard], lo cual ayuda a rastrear los envíos de notificaciones Push y la interacción de los usuarios con la aplicación móvil, debe crear una regla en [!DNL Experience Platform Launch].

Para obtener más información sobre el seguimiento push, consulte [Seguimiento push](../../administration/using/push-tracking.md).

Para realizar el seguimiento de las acciones de la aplicación, utilice la API trackAction. Para obtener más información, consulte [Seguimiento de acciones de la aplicación](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. En [!DNL Experience Platform Launch], desde el panel de la aplicación móvil, haga clic en la ficha **[!UICONTROL Rules]** y luego en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Adobe Campaign - seguimiento de clics push**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Track Action]** en la lista desplegable **[!UICONTROL Event type]**.

1. En la lista desplegable **[!UICONTROL Action]**, seleccione **[!UICONTROL Action]**, seleccione **[!UICONTROL equals]** y escriba **tracking**.

1. Haga clic en **[!UICONTROL Keep changes]**. A continuación, en la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la lista desplegable **[!UICONTROL Action type]**.

1. En **[!UICONTROL URL]**, introduzca la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Seleccione la casilla de verificación **[!UICONTROL Add post body]**.

1. Añada el cuerpo del anuncio, por ejemplo, { }.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 0.

### Postback de ubicación {#location-postback}

1. En [!DNL Experience Platform Launch], desde el panel de la aplicación móvil, haga clic en la ficha **[!UICONTROL Rules]** y luego en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Postback de ubicación**.

1. En la sección **[!UICONTROL Events]**, haga clic en **[!UICONTROL Add]**.

1. Cree un evento, por ejemplo, Introduzca el punto de interés o el punto de interés de salida. En la lista desplegable **[!UICONTROL Extension]**, seleccione **Lugares - Beta**. A continuación, **Introduzca POI** o **Salida de POI** en la lista desplegable **[!UICONTROL Event type]**.

1. Escriba un nombre, por ejemplo, **Lugares - Beta - Introducir POI** o **Salida de POI**.

1. En la sección **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]**.

1. Del desplegable **[!UICONTROL Extension]**, seleccione **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la lista desplegable **[!UICONTROL Action type]**.

1. Escriba un nombre, por ejemplo, **Mobile Core - Enviar postback de ubicación**.

1. En **[!UICONTROL URL]**, introduzca la siguiente dirección URL:

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
   >En el ejemplo anterior, los elementos de datos del lado derecho deben configurarse en [!DNL Experience Platform Launch] aprovechando los pasos de [Creación de elementos de datos](../../administration/using/configuring-rules-launch.md#create-data-elements). Los elementos de datos del lado izquierdo se admiten en [!DNL Adobe Campaign Standard] y no necesitan ninguna configuración. Si necesita datos adicionales, debe llevar a cabo extensiones de recursos personalizadas en [!DNL Adobe Campaign Standard].

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. En **[!UICONTROL Timeout]**, seleccione 5.

   ![](assets/do-not-localize/rules_4.png)

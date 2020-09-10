---
title: Configuración de reglas de Adobe Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard
description: Configuración de reglas de Adobe Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2112f93fba368435850957e6e90b7c7c88ddf248
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---


# Configuración de reglas de lanzamiento para admitir casos de uso de Adobe Campaign Standard {#configuring-rules-launch}

En [!DNL Adobe Experience Platform Launch], debe crear elementos de datos y reglas para enviar PII y otros datos desde aplicaciones móviles a [!DNL Adobe Campaign Standard].

Para asegurarse de que todos los cambios de configuración [!DNL Adobe Experience Platform Launch] surten efecto, debe publicar estos cambios. Para obtener más información, consulte [Publicación](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Para crear reglas en [!DNL Experience Platform Launch], siga estos pasos:

1. [Creación de elementos de datos](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creación de reglas](../../administration/using/configuring-rules-launch.md#create-data-elements) para casos de uso que desee admitir:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de seguimiento en la aplicación](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback del seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de ubicación](../../administration/using/configuring-rules-launch.md#location-postback)

## Creación de elementos de datos {#create-data-elements}

Estos son los elementos de datos en los que se recomienda crear [!DNL Experience Platform Launch].
Puede crear elementos de datos adicionales según sus necesidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para crear estos elementos de datos:

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, haga clic en la **[!UICONTROL Data Elements]** ficha.

1. Para crear el elemento de **[!UICONTROL Experience Cloud ID]** datos, haga clic en **[!UICONTROL Create New Data Element]**.

1. En el **[!UICONTROL Name]** campo, por ejemplo, escriba **mcid**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Experience Cloud ID]** en la lista desplegable **[!UICONTROL Data element]** de tipos.

   ![](assets/do-not-localize/rules_1.png)

1. Para crear el elemento de datos Pkey, haga clic en **[!UICONTROL Add data element]**.

1. En el **[!UICONTROL Name]** campo, por ejemplo, escriba **pkey**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL pkey]** en la lista desplegable **[!UICONTROL Data element]** de tipos.

1. Para crear el elemento de datos del servidor de Campaña, haga clic en **[!UICONTROL Add data element]**.

1. En el **[!UICONTROL Name]** campo, escriba un nombre, por ejemplo, **camp-server**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. A continuación, **[!UICONTROL Campaign Server]** en la lista desplegable **[!UICONTROL Data element]** de tipos.

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

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, haga clic en la **[!UICONTROL Rules]** ficha y, a continuación, en **[!UICONTROL Create New Rule]**.

1. Escriba un nombre, por ejemplo, **Mobile Core - Recopilación de PII**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Collect PII]** in the **[!UICONTROL Event type]** drop-down.

1. Haga clic **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send PII]** in the **[!UICONTROL Action type]** drop-down.

1. En **[!UICONTROL URL]**, introduzca la siguiente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Seleccione la **[!UICONTROL Add Post Body]** casilla de verificación.

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

   Los elementos de datos definidos en [!DNL Experience Platform Launch] deben incluirse en porcentajes de doble, por ejemplo %%mcid%%, y las variables de contexto de la aplicación deben incluirse en porcentajes únicos, por ejemplo %contextdata.email%.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_2.png)

Los datos de usuario ahora están configurados para enviarse a Campaña.

### Postback de seguimiento en la aplicación {#inapp-tracking-postback}

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard] para obtener sistemas de informes sobre cómo interactúan los usuarios con los mensajes en la aplicación móvil, cree la siguiente regla en [!DNL Experience Platform Launch]:

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, seleccione la **[!UICONTROL Rules]** ficha y haga clic en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Adobe Campaign - Seguimiento** de clics en la aplicación.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Then, **[!UICONTROL In-App click tracking]** in the **[!UICONTROL Event type]** drop-down.

1. Haga clic **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send postback]** in the **[!UICONTROL Event type]** drop-down.

1. En **[!UICONTROL URL]**, escriba la siguiente dirección URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Seleccione la **[!UICONTROL Add post body]** casilla de verificación.

1. En **[!UICONTROL Post Body]**, escriba **{}**.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback del seguimiento de notificaciones push {#push-tracking-postback}

Para enviar datos de seguimiento a [!DNL Adobe Campaign Standard], lo que le ayuda a rastrear sus envíos de notificaciones push y la interacción de los usuarios con la aplicación móvil, debe crear una regla en [!DNL Experience Platform Launch].

Para obtener más información sobre el seguimiento push, consulte Seguimiento [push](../../administration/using/push-tracking.md).

Para realizar el seguimiento de las acciones de la aplicación, utilice la API trackAction. Para obtener más información, consulte [Seguimiento de acciones](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)de la aplicación.

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, haga clic en la **[!UICONTROL Rules]** ficha y, a continuación, en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Adobe Campaign - seguimiento** de clics push.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Track Action]** in the **[!UICONTROL Event type]** drop-down.

1. En la **[!UICONTROL Action]** lista desplegable, seleccione **[!UICONTROL Action]**, seleccione **[!UICONTROL equals]** y escriba **seguimiento**.

1. Haga clic en **[!UICONTROL Keep changes]**. Then, in the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send postback]** in the **[!UICONTROL Action type]** drop-down.

1. En **[!UICONTROL URL]**, introduzca la siguiente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Seleccione la **[!UICONTROL Add post body]** casilla de verificación.

1. Añada el cuerpo del anuncio, por ejemplo, { }.

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

### Postback de ubicación {#location-postback}

1. En [!DNL Experience Platform Launch], en el panel de la aplicación móvil, haga clic en la **[!UICONTROL Rules]** ficha y, a continuación, en **[!UICONTROL Add Rule]**.

1. Escriba un nombre, por ejemplo, **Ubicación postback**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. Cree un evento, por ejemplo, Introduzca el punto de interés o el punto de interés de salida. En la **[!UICONTROL Extension]** lista desplegable, seleccione **Lugares - Beta**. A continuación, **introduzca el punto de interés** o el punto de **salida** en la **[!UICONTROL Event type]** lista desplegable.

1. Escriba un nombre, por ejemplo, **Lugares - Beta - Introducir punto de interés** o punto de **salida**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. A continuación, **[!UICONTROL Send postback]** en la **[!UICONTROL Action type]** lista desplegable.

1. Escriba un nombre, por ejemplo **Mobile Core - Enviar postback** de ubicación.

1. En **[!UICONTROL URL]**, introduzca la siguiente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Seleccione la **[!UICONTROL Add post body]** casilla de verificación y agregue el cuerpo del anuncio, por ejemplo:

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
   >En el ejemplo anterior, los elementos de datos del lado derecho deben configurarse [!DNL Experience Platform Launch] aprovechando los pasos de [Creación de elementos](../../administration/using/configuring-rules-launch.md#create-data-elements)de datos. Los elementos de datos del lado izquierdo son compatibles [!DNL Adobe Campaign Standard] y no necesitan ninguna configuración. Si necesita datos adicionales, debe realizar extensiones de recursos personalizadas en [!DNL Adobe Campaign Standard].

1. En **[!UICONTROL Content Type]**, escriba **application/json**.

1. In **[!UICONTROL Timeout]**, select 5.

   ![](assets/do-not-localize/rules_4.png)

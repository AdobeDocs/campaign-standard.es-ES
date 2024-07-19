---
title: Casos de uso móvil admitidos en Adobe Campaign Standard mediante el uso de los SDK para Adobe Experience Platform
description: Descubra cómo admitir casos de uso móvil
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Casos de uso móvil admitidos en Adobe Campaign Standard {#mobile-use-cases}

En esta página, encontrará la lista de todos los casos de uso móvil admitidos en [!DNL Adobe Campaign Standard] con el [!DNL Adobe Experience Platform SDKs]. Tenga en cuenta que la compatibilidad con estos casos de uso implica instalar y configurar [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform] y [!DNL Adobe Campaign Standard]. Para obtener más información, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard admite los siguientes casos de uso:

* [Registro de un perfil móvil en Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Envío de un token push al Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Enriquecimiento de un perfil móvil con datos personalizados de su aplicación](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Enriquecimiento de un perfil móvil con datos del ciclo vital de la aplicación](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Seguimiento de la interacción del usuario con notificaciones push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implemente un evento personalizado en la aplicación móvil para almacenar en déclencheur los mensajes en la aplicación](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Establezca campos de vinculación para una autenticación adicional para la plantilla de perfil basada en los mensajes en la aplicación](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Para configurar estos casos de uso, necesita las siguientes extensiones:

* **[!DNL Adobe Campaign Standard]** <br>Para instalar y configurar la extensión de Campaign Standard, consulte [Configuración de la extensión de Campaign Standard en la IU de recopilación de datos](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**, que se instala automáticamente. <br>Para obtener más información acerca de la extensión móvil principal, consulte [Mobile Core](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**, que se instala automáticamente. <br>Para obtener más información sobre la extensión de perfil, consulte [Perfil](https://developer.adobe.com/client-sdks/documentation/profile/).

## Registro de un perfil móvil en Campaign Standard {#register-mobile-profile}

### Con iOS {#register-mobile-profile-ios}

En iOS, se requieren los siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, cuando la aplicación se inicia y cuando la aplicación está en primer plano.
* **[!UICONTROL Lifecycle Pause]**, cuando la aplicación se encuentra en segundo plano.

Para obtener más información, consulte [Extensión del ciclo de vida en iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Esta es una implementación de ejemplo de este caso de uso con iOS:

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Con Android {#register-mobile-profile-android}

En Android, se requieren los siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obtener más información, consulte [Extensión del ciclo de vida en Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Envío de un token push a Adobe Campaign Standard {#send-push-token}

### Con iOS {#send-push-token-ios}

En iOS, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Para obtener más información, consulte [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Esta es una implementación de ejemplo para este caso de uso con iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Con Android {#send-push-token-android}

En Android, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Para obtener más información, consulte [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Enriquecimiento de un perfil móvil con datos personalizados de su aplicación {#enrich-mobile-profile-custom}

Para que este caso de uso funcione, debe crear reglas para los postbacks PII. Para obtener más información, consulte [Postbacks PII](../../administration/using/configuring-rules-launch.md#pii-postback).

### Con iOS {#enrich-mobile-profile-custom-ios}

En iOS, se requiere lo siguiente [!DNL Experience Platform API]:

* collectPII <br> Para obtener más información, consulte collectPII.

Esta es una implementación de ejemplo de este caso de uso con iOS:

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Con Android {#enrich-mobile-profile-custom-android}

En Android, se requiere lo siguiente [!DNL Experience Platform API]:

* collectPII <br> Para obtener más información, consulte collectPII.

Esta es una implementación de ejemplo para este caso de uso con Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## Enriquecimiento de un perfil móvil con datos del ciclo vital de la aplicación {#enrich-mobile-profile-lifecycle}

Para que este caso de uso funcione, debe crear reglas para los postbacks PII. Para obtener más información, consulte [Postbacks PII](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign no distingue entre datos personalizados o datos del ciclo vital de la aplicación móvil. Ambos tipos de datos se pueden enviar al servidor mediante una regla de postback collectPii en respuesta a un evento en la aplicación móvil.

### Con iOS {#enrich-mobile-profile-lifecycle-ios}

En iOS, se requieren los siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, cuando la aplicación se inicia y cuando la aplicación está en primer plano.
* **[!UICONTROL Lifecycle Pause]**, cuando la aplicación se encuentra en segundo plano.

Para obtener más información, consulte [Extensión del ciclo de vida en iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Esta es una implementación de ejemplo de este caso de uso con iOS:

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Con Android {#enrich-mobile-profile-lifecycle-android}

En Android, se requieren los siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obtener más información, consulte [Extensión del ciclo de vida en Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Seguimiento de la interacción del usuario con notificaciones push {#track-user-push}

Debe crear reglas para el postback de seguimiento de notificaciones push. Para obtener más información, consulte [Seguimiento de notificaciones push postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Con iOS {#track-user-push-ios}

En iOS, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta es una implementación de ejemplo de este caso de uso con iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Con Android {#track-user-push-android}

En Android, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implemente un evento personalizado en la aplicación para almacenar en déclencheur los mensajes en la aplicación {#custom-event-inapp}

### Con iOS {#custom-event-inapp-ios}

En iOS, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta es una implementación de ejemplo de este caso de uso con iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Con Android {#custom-event-inapp-android}

En Android, se requiere lo siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Establecer campos de vinculación para una autenticación adicional {#linkage-fields-inapp}

### Con iOS {#linkage-fields-inapp-ios}

Para establecer los campos de vinculación para la autenticación adicional de la plantilla de perfil basada en los mensajes en la aplicación de iOS, se requiere lo siguiente [!DNL Experience Platform SDK]:

* Establecer campos de vinculación <br>Para obtener más información, consulte [Establecer campos de vinculación](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Restablecer campos de vinculación <br>Para obtener más información, consulte [Restablecer campos de vinculación](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

Estas son algunas implementaciones de ejemplo de este caso de uso con iOS.

Para establecer los campos de vinculación:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Para restablecer los campos de vinculación:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Con Android {#linkage-fields-inapp-android}

Para establecer campos de vinculación para una autenticación adicional para la plantilla de perfil basada en mensajes en la aplicación en Android, se requiere el siguiente SDK de Experience Platform:

* Establecer campos de vinculación <br>Para obtener más información, consulte [Establecer campos de vinculación](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Restablecer campos de vinculación <br>Para obtener más información, consulte [Restablecer campos de vinculación](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Estas son algunas implementaciones de ejemplo de este caso de uso con Android.

Para establecer los campos de vinculación:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Para restablecer los campos de vinculación:

```
Campaign.resetLinkageFields()
```

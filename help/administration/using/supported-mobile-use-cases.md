---
title: Casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK para Adobe Experience Platform
description: Este documento proporciona información sobre cómo admitir casos de uso móvil.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---

# Casos de uso móvil admitidos en Adobe Campaign Standard {#mobile-use-cases}

En esta página, encontrará la lista de todos los casos de uso móvil admitidos en [!DNL Adobe Campaign Standard] mediante el [!DNL Adobe Experience Platform SDKs]. Tenga en cuenta que el soporte de estos casos de uso implica la instalación y configuración de [!DNL Adobe Experience Platform SDKs], [!DNL Adobe Experience Platform Launch] y [!DNL Adobe Campaign Standard]. Para obtener más información, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard admite los siguientes casos de uso:

* [Registro de un perfil móvil en Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Envío de un token push al Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Enriquecimiento de un perfil móvil con datos personalizados de su aplicación](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Enriquecimiento de un perfil móvil con datos del ciclo vital de su aplicación](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Seguimiento de la interacción del usuario con las notificaciones push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implemente un evento personalizado en su aplicación móvil para almacenar en déclencheur los mensajes en la aplicación](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Establecer campos de vinculación para una autenticación adicional para la plantilla de perfil basada en mensajes en la aplicación](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Para configurar estos casos de uso, necesita las siguientes extensiones de [!DNL Experience Platform Launch]:

* **[!DNL Adobe Campaign Standard]** <br>Para instalar y configurar la extensión del Campaign Standard, consulte  [Configuración de la extensión del Campaign Standard en Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch).
* **[!DNL Mobile Core]**, que se instala automáticamente. <br>Para obtener más información sobre la extensión principal de Mobile, consulte  [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core).
* **[!DNL Profile]**, que se instala automáticamente. <br>Para obtener más información sobre la extensión de perfil, consulte  [Perfil](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile).

## Registro de un perfil móvil en Campaign Standard {#register-mobile-profile}

### Con iOS {#register-mobile-profile-ios}

En iOS, se requieren las siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, cuando la aplicación se inicia y está en primer plano.
* **[!UICONTROL Lifecycle Pause]**, cuando la aplicación esté en segundo plano.

Para obtener más información, consulte [Lifecycle extension in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esta es una implementación de muestra de este caso de uso con iOS:

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

En Android, se requieren las siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obtener más información, consulte [Lifecycle extension in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

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

En iOS, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Para obtener más información, consulte  [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Esta es una implementación de ejemplo para este caso de uso con iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Con Android {#send-push-token-android}

En Android, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Para obtener más información, consulte  [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

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

En iOS, se requiere el siguiente [!DNL Experience Platform API]:

* collectPII <br> Para obtener más información, consulte collectPII.

Esta es una implementación de muestra de este caso de uso con iOS:

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Con Android {#enrich-mobile-profile-custom-android}

En Android, se requiere el siguiente [!DNL Experience Platform API]:

* collectPII <br> Para obtener más información, consulte collectPII.

Esta es una implementación de ejemplo para este caso de uso con Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## Enriquecimiento de un perfil móvil con datos del ciclo vital de su aplicación {#enrich-mobile-profile-lifecycle}

Para que este caso de uso funcione, debe crear reglas para los postbacks PII. Para obtener más información, consulte [Postbacks PII](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign no distingue entre datos personalizados o datos del ciclo vital de la aplicación móvil. Ambos tipos de datos se pueden enviar al servidor mediante una regla de postback collectPii como respuesta a un evento en la aplicación móvil.

### Con iOS {#enrich-mobile-profile-lifecycle-ios}

En iOS, se requieren las siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, cuando la aplicación se inicia y está en primer plano.
* **[!UICONTROL Lifecycle Pause]**, cuando la aplicación esté en segundo plano.

Para obtener más información, consulte [Lifecycle extension in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esta es una implementación de muestra de este caso de uso con iOS:

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

En Android, se requieren las siguientes [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obtener más información, consulte [Lifecycle extension in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

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

## Seguimiento de la interacción del usuario con las notificaciones push {#track-user-push}

Debe crear reglas para el seguimiento de postback de notificaciones push. Para obtener más información, consulte [Postback del seguimiento de notificaciones push](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Con iOS {#track-user-push-ios}

En iOS, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta es una implementación de muestra de este caso de uso con iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Con Android {#track-user-push-android}

En Android, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Para obtener más información, consulte  [Seguimiento de acciones de aplicaciones](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implemente un evento personalizado en la aplicación para almacenar en déclencheur los mensajes en la aplicación {#custom-event-inapp}

### Con iOS {#custom-event-inapp-ios}

En iOS, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Para obtener más información, consulte [Seguimiento de acciones de aplicaciones](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta es una implementación de muestra de este caso de uso con iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Con Android {#custom-event-inapp-android}

En Android, se requiere el siguiente [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Para obtener más información, consulte  [Seguimiento de acciones de aplicaciones](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta es una implementación de ejemplo para este caso de uso con Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Definir campos de vinculación para autenticación adicional {#linkage-fields-inapp}

### Con iOS {#linkage-fields-inapp-ios}

Para establecer campos de vinculación para una autenticación adicional para la plantilla de perfil basada en mensajes en la aplicación en iOS, se requiere el siguiente [!DNL Experience Platform SDK]:

* Definir campos de vinculación <br>Para obtener más información, consulte [Establecer campos de vinculación](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Restablecer campos de vinculación <br>Para obtener más información, consulte [Restablecer campos de vinculación](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Estas son implementaciones de ejemplo de este caso de uso con iOS.

Para definir los campos de vinculación:

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

* Definir campos de vinculación <br>Para obtener más información, consulte [Establecer campos de vinculación](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Restablecer campos de vinculación <br>Para obtener más información, consulte [Restablecer campos de vinculación](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Estas son implementaciones de ejemplo de este caso de uso con Android.

Para definir los campos de vinculación:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Para restablecer los campos de vinculación:

```
Campaign.resetLinkageFields()
```

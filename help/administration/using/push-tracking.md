---
title: Implementación del seguimiento push
description: Este documento le permite asegurarse de que el seguimiento de notificaciones push se ha implementado correctamente en iOS y Android.
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
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 2%

---


# Implementación del seguimiento push {#push-tracking}

## Acerca del seguimiento push {#about-push-tracking}

Para garantizar que la notificación push se ha desarrollado completamente, debe asegurarse de que la porción de seguimiento se ha implementado correctamente.
Esto supone que ya ha implementado las primeras partes de la implementación de notificaciones push:

* Registro del usuario de la aplicación
* Gestión de un mensaje de notificación push

El seguimiento push se divide en tres tipos:

* **Impresiones** push: cuando se ha enviado una notificación push al dispositivo y se encuentra en el centro de notificaciones, pero no se ha tocado en absoluto.  Esto se considera una impresión.  En la mayoría de los casos, los números de impresiones deben ser similares si no iguales al número entregado. Garantiza que el dispositivo obtuvo el mensaje y retransmitió esa información al servidor.

* **Clic** push: cuando se ha enviado una notificación push al dispositivo y el usuario ha hecho clic en él.  El usuario deseaba realizar la vista (que a su vez pasaría al seguimiento Push Open) o descartar la notificación.

* **Abrir** push: cuando se envía una notificación push al dispositivo y el usuario hace clic en la notificación que hace que la aplicación se abra.  Esto es similar a los clics push, excepto que no se activará un push Open si se descartó la notificación.

Para implementar el seguimiento para Campaign Standard, la aplicación móvil debe incluir SDK móvil. Estos SDK están disponibles en Adobe Mobile Services. Para obtener más información, consulte [esta página](../../administration/using/configuring-a-mobile-application.md).

Para enviar la información de seguimiento hay tres variables que deben enviarse. Dos que forman parte de los datos recibidos de Campaign Standard y una variable de acción que dicta si es una **Impresión**, un **Clic** o un **Abrir**.

| Variable  | Valor |
|:-:|:-:|
| wideLogId | _mId de datos |
| deliveryId | _dId de datos |
| action | 1 para Open, 2 para Click y 7 para Impresión |

## Implementación para Android {#implementation-android}

### Cómo implementar el seguimiento de impresión push {#push-impression-tracking-android}

Para el seguimiento de impresiones, deberá enviar el valor &quot;7&quot; para la acción al llamar a **[!UICONTROL trackAction()]** la función.

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Cómo implementar el rastreo de clics {#push-click-tracking-android}

Para el rastreo de clics, deberá enviar el valor &quot;2&quot; para la acción al llamar a **[!UICONTROL trackAction()]** la función.

Para rastrear clics, es necesario administrar dos escenarios:

* El usuario ve la notificación pero la borra.
* El usuario ve la notificación y hace clic en ella para convertirla en un seguimiento abierto.

Para gestionar esto, debe utilizar dos Intentos: uno para hacer clic en la notificación y otro para descartarla.

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

Para poder **[!UICONTROL BroadcastReceiver]** trabajar necesita registrarlo en el **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Cómo implementar el seguimiento abierto {#push-open-tracking-android}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia/abre mediante notificación push, no se produce ningún evento de seguimiento.

Para rastrear la apertura, debe crear Calidad. Los objetos de intención permiten que el sistema operativo Android llame al método cuando se realicen determinadas acciones. En este caso, haga clic en la notificación para abrir la aplicación.

Este código se basa en la implementación del seguimiento de impresión de clics. Con **[!UICONTROL Intent]** el conjunto, ahora necesita enviar la información de seguimiento de vuelta a Adobe Campaign Standard. En este caso, debe configurar el **[!UICONTROL Open Intent]** para que se abra en una determinada vista de la aplicación, lo que llamará al método onResume con los datos de notificación en la **[!UICONTROL Intent Object]**.

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
  
  
private void handleTracking() {
    //Check to see if this view was opened based on a notification
    Intent intent = getIntent();
    Bundle data = intent.getExtras();
  
    if (data != null) {
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementación para iOS {#implementation-iOS}

### Cómo implementar el seguimiento de impresión push {#push-impression-tracking-iOS}

Para el seguimiento de impresiones, deberá enviar el valor &quot;7&quot; para la acción al llamar a **[!UICONTROL trackAction()]** la función.

Para comprender cómo funcionan las notificaciones de iOS, es necesario detallar los tres estados de una aplicación:

* **Primer plano**: cuando la aplicación está activa actualmente y en pantalla (en primer plano).
* **Antecedentes**: cuando la aplicación is no está en pantalla pero el proceso no está cerrado. Al hacer clic en el botón de inicio con el botón de doble, generalmente se muestran todas las aplicaciones que están en segundo plano.
* **Desactivado/cerrado**: una aplicación cuyo proceso ha sido eliminado.

Si se cierra una aplicación, Apple no llamará a la aplicación hasta que ésta se haya reiniciado. Esto significa que no podrá saber cuándo se recibió la notificación en iOS.

Para que el seguimiento siga **[!UICONTROL Impression]** funcionando mientras la aplicación se encuentra en segundo plano, debemos enviarlo **[!UICONTROL Content-Available]** para que la aplicación sepa que se debe realizar un seguimiento.

>[!CAUTION]
>
>El seguimiento de impresiones de iOS no es preciso y no debe considerarse fiable.

La siguiente aplicación de fondo de destinatarios de código:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

El siguiente código destinatario la aplicación en primer plano:

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Cómo implementar el rastreo de clics {#push-click-tracking-iOS}

Para el rastreo de clics, deberá enviar el valor &quot;2&quot; para la acción al llamar a **[!UICONTROL trackAction()]** la función.

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Ahora, al enviar notificaciones push, debe agregar una categoría. En este caso, lo llamamos &quot;PREDETERMINADO&quot;.

![](assets/tracking_push.png)

A continuación, para gestionar **[!UICONTROL Dismiss]** y enviar una información de seguimiento, debe agregar lo siguiente:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Cómo implementar el seguimiento abierto {#push-open-tracking-iOS}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia/abre mediante notificación push, no se produce ningún evento de seguimiento.

```
import Foundation
import UserNotifications
import UserNotificationsUI
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```

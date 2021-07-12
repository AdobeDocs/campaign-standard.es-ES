---
solution: Campaign Standard
product: campaign
title: Implementación del seguimiento push
description: Este documento le permite asegurarse de que el seguimiento de notificaciones push se ha implementado correctamente en iOS y Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Configuración de instancia
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 1%

---

# Implementación del seguimiento push {#push-tracking}

## Acerca del seguimiento push {#about-push-tracking}

Para garantizar que la notificación push se haya desarrollado completamente, debe asegurarse de que la parte de seguimiento se haya implementado correctamente, ya que no todas las notificaciones push tienen habilitado el seguimiento. Para habilitar esto, los desarrolladores deben identificar qué entregas tienen habilitado el seguimiento, Adobe Campaign Standard enviará un indicador llamado `_acsDeliveryTracking` con dos valores **en** o **off**. El desarrollador de la aplicación debe enviar una solicitud de seguimiento solo en los envíos que tengan la variable configurada como **en**.

>[!IMPORTANT]
>
>Esta variable no está disponible para los envíos establecidos antes de la versión 21.1 o los envíos que utilizan plantillas personalizadas.

El seguimiento push se divide en tres tipos:

* **Impresiones push** : cuando se entrega una notificación push al dispositivo y se encuentra en el centro de notificaciones, pero no se ha tocado en absoluto.  Esto se considera una impresión.  En la mayoría de los casos, los números de impresiones deberían ser similares si no iguales al número entregado. Garantiza que el dispositivo obtuvo el mensaje y retransmitió esa información al servidor.

* **Clic push** : cuando se envía una notificación push al dispositivo y el usuario ha hecho clic en él.  El usuario quería ver la notificación (que a su vez pasará al seguimiento de Push Open) o descartará la notificación.

* **Apertura push** : cuando se envía una notificación push al dispositivo y el usuario ha hecho clic en la notificación que provoca que la aplicación se abra.  Esto es similar al clic push , excepto que no se activará un push Open si se descarta la notificación.

Para implementar el seguimiento para Campaign Standard, la aplicación móvil debe incluir el SDK móvil. Estos SDK están disponibles en Adobe Mobile Services. Para obtener más información, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Para enviar la información de seguimiento hay tres variables que se deben enviar. Dos que son parte de los datos recibidos del Campaign Standard y una variable de acción que dicta si es una **Impresión**, **Clic** o **Abrir**.

| Variable  | Valor |
|:-:|:-:|
| broadlogId | _mId a partir de datos |
| deliveryId | _dId a partir de datos |
| acción | 1 para Open, 2 para Click y 7 para Impression |

## Implementación para Android {#implementation-android}

### Implementación del seguimiento de impresión push {#push-impression-tracking-android}

Para el seguimiento de impresiones, deberá enviar el valor &quot;7&quot; para que se realice la acción al llamar a la función **[!UICONTROL trackAction()]** .

Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Implementación del rastreo de clics {#push-click-tracking-android}

Para el rastreo de clics, debe enviar el valor &quot;2&quot; para la acción al llamar a la función **[!UICONTROL trackAction()]** .

Para rastrear clics, se deben gestionar dos escenarios:

* El usuario ve la notificación, pero la borra.
* El usuario ve la notificación y hace clic en ella para convertirla en un seguimiento abierto.

Para gestionar esto, debe utilizar dos intenciones: una para hacer clic en la notificación y otra para rechazar la notificación.

Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

Para que **[!UICONTROL BroadcastReceiver]** funcione, debe registrarlo en el **[!UICONTROL AndroidManifest.xml]**

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
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Implementación del seguimiento abierto {#push-open-tracking-android}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en notificación para abrir la aplicación. Si la aplicación no se inicia o abre mediante una notificación push, no se produce ningún evento de seguimiento.

Para rastrear la apertura, debe crear Intent. Los objetos de intención permiten que el sistema operativo Android realice una llamada al método cuando se hayan realizado determinadas acciones. En este caso, haga clic en la notificación para abrir la aplicación.

Este código se basa en la implementación del seguimiento de impresión de clics. Con **[!UICONTROL Intent]** configurado, ahora debe enviar la información de seguimiento de vuelta a Adobe Campaign Standard. En este caso, es necesario configurar **[!UICONTROL Open Intent]** para que se abra en una vista determinada de la aplicación; esto llamará al método onResume con los datos de notificación de **[!UICONTROL Intent Object]**.

Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
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

### Implementación del seguimiento de impresión push {#push-impression-tracking-iOS}

Para el seguimiento de impresiones, deberá enviar el valor &quot;7&quot; para que se realice la acción al llamar a la función **[!UICONTROL trackAction()]** .

Para comprender cómo funcionan las notificaciones de iOS, es necesario detallar los tres estados de una aplicación:

* **Primer plano**: cuando la aplicación está activa y actualmente está en pantalla (en primer plano).
* **Antecedentes**: cuando la aplicación is no está en pantalla, pero el proceso no está cerrado. Cuando hace doble clic en el botón principal, normalmente muestra todas las aplicaciones que están en segundo plano.
* **Desactivado/cerrado**: una aplicación cuyo proceso ha finalizado.

Si se cierra una aplicación, Apple no la llamará hasta que se vuelva a iniciar. Esto significa que no podrá saber cuándo se recibió la notificación en iOS.

Para que el seguimiento de **[!UICONTROL Impression]** siga funcionando mientras la aplicación está en segundo plano, debemos enviar **[!UICONTROL Content-Available]** para que la aplicación sepa que se debe realizar un seguimiento.

>[!CAUTION]
>
>El seguimiento de impresiones de iOS no es preciso y no debe considerarse fiable.

Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

El siguiente código se dirige a la aplicación en segundo plano:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

El siguiente código se dirige a la aplicación en primer plano:

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Implementación del rastreo de clics {#push-click-tracking-iOS}

Para el rastreo de clics, debe enviar el valor &quot;2&quot; para la acción al llamar a la función **[!UICONTROL trackAction()]** .
Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

Ahora, al enviar notificaciones push, debe añadir una categoría. En este caso, lo llamamos &quot;PREDETERMINADO&quot;.

![](assets/tracking_push.png)

A continuación, para gestionar **[!UICONTROL Dismiss]** y enviar una información de seguimiento, debe añadir lo siguiente:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Implementación del seguimiento abierto {#push-open-tracking-iOS}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en notificación para abrir la aplicación. Si la aplicación no se inicia o abre mediante una notificación push, no se produce ningún evento de seguimiento.

Para los envíos creados antes de la versión 21.1 o los envíos con plantilla personalizada, consulte esta [sección](../../administration/using/push-tracking.md#about-push-tracking).

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
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```

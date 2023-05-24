---
title: Implementación del seguimiento push
description: Aprenda a garantizar que el seguimiento de notificaciones push se haya implementado correctamente en iOS y Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: acbe5f1990738f586e4310d13f0e19baab11d771
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Implementación del seguimiento push {#push-tracking}

## Acerca del seguimiento push {#about-push-tracking}

Para garantizar que la notificación push se haya desarrollado completamente, debe asegurarse de que la parte de seguimiento se haya implementado correctamente, ya que no todas las notificaciones push tienen seguimiento habilitado. Para habilitar esto, los desarrolladores deben identificar qué entregas tienen seguimiento habilitado, Adobe Campaign Standard enviará un indicador llamado `_acsDeliveryTracking` con dos valores **el** o **desactivado**. El desarrollador de aplicaciones debe enviar una solicitud de seguimiento solo en los envíos que tengan la variable configurada como **el**.

>[!IMPORTANT]
>
>Esta variable no debe estar disponible para entregas anteriores a la versión 21.1 o para entregas que utilicen plantillas personalizadas.

El seguimiento push se divide en tres tipos:

* **Impresiones push** : cuando se ha enviado una notificación push al dispositivo y está en el centro de notificaciones, pero no se ha tocado.  Esto se considera una impresión.  En la mayoría de los casos, los números de impresiones deben ser similares, si no iguales, al número entregado. Garantiza que el dispositivo haya recibido el mensaje y haya retransmitido esa información al servidor.

* **Clic push** : cuando se ha enviado una notificación push al dispositivo y el usuario ha hecho clic en él.  El usuario deseaba ver la notificación (que a su vez pasará al seguimiento de Apertura push) o descartarla.

* **Push Open** : cuando se ha enviado una notificación push al dispositivo y el usuario ha hecho clic en la notificación, lo que provoca que la aplicación se abra.  Esto es similar al clic push, excepto que una apertura push no se activa si se descarta la notificación.

Para implementar el seguimiento para Campaign Standard, la aplicación móvil debe incluir los SDK de Adobe Experience Platform. Estos SDK están disponibles en [Documentación de SDK para Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

Para enviar información de seguimiento, hay tres variables que deben enviarse. Dos que forman parte de los datos recibidos del Campaign Standard y una variable de acción que dicta si es un **Impresión**, **Clic** o **Abrir**.

| Variable  | Valor |
|:-:|:-:|
| broadlogId | _mId de datos |
| deliveryId | _dId desde datos |
| acción | &quot;1&quot; para Apertura, &quot;2&quot; para Clic y &quot;7&quot; para Impresión |

## Implementación para Android {#implementation-android}

### Implementación del seguimiento de impresiones push {#push-impression-tracking-android}

Para el seguimiento de impresiones, tendrá que enviar el valor &quot;7&quot; para la acción al llamar a `collectMessageInfo()` o `trackAction()` funciones.

Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### Implementación del rastreo de clics {#push-click-tracking-android}

Para el rastreo de clics, tendrá que enviar el valor &quot;2&quot; para la acción al llamar a `collectMessageInfo()` o `trackAction()` funciones.
Para rastrear clics, se deben manejar dos situaciones:

* El usuario ve la notificación, pero la borra.
* El usuario ve la notificación y hace clic en ella para convertirla en un seguimiento abierto.

Para gestionar esto, debe utilizar dos intenciones: una para hacer clic en la notificación y otra para descartar la notificación.

Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

Para que la **[!UICONTROL BroadcastReceiver]** para trabajar, debe registrarlo en el **[!UICONTROL AndroidManifest.xml]**

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
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Implementación del seguimiento abierto {#push-open-tracking-android}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia o abre mediante una notificación push, no se produce ningún evento de seguimiento.

Para rastrear la apertura, debe crear Intención. Los objetos de intención permiten al sistema operativo Android llamar al método cuando se realizan determinadas acciones. En este caso, haga clic en la notificación para abrir la aplicación.

Este código se basa en la implementación del seguimiento de impresiones de clics. Con **[!UICONTROL Intent]** configurado, ahora debe devolver la información de seguimiento a Adobe Campaign Standard. En este caso, debe configurar la variable **[!UICONTROL Open Intent]** para abrir una vista determinada en la aplicación, se llamará al método onResume con los datos de notificación en el **[!UICONTROL Intent Object]**.

Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementación para iOS {#implementation-iOS}

### Implementación del seguimiento de impresiones push {#push-impression-tracking-iOS}

Para el seguimiento de impresiones, tendrá que enviar el valor &quot;7&quot; para la acción al llamar a `collectMessageInfo()` o `trackAction()` funciones.

Para comprender cómo funcionan las notificaciones de iOS, es necesario detallar los tres estados de una aplicación:

* **Primer plano**: cuando la aplicación está activa actualmente y en pantalla (en primer plano).
* **Fondo**: cuando la aplicación is no está en pantalla, pero el proceso no está cerrado. Al hacer doble clic en el botón de inicio, generalmente se muestran todas las aplicaciones que están en segundo plano.
* **Desactivado/cerrado**: una aplicación cuyo proceso se ha eliminado.

Para poder seguir teniendo **[!UICONTROL Impression]** el seguimiento funciona mientras la aplicación está en segundo plano y es necesario enviarlo **[!UICONTROL Content-Available]** para que la aplicación sepa que se debe realizar un seguimiento.

>[!CAUTION]
>
> Si se cierra una aplicación, Apple no la llamará hasta que se haya reiniciado. Esto significa que no podrá saber cuándo se ha recibido la notificación en iOS. </br> Debido a este motivo, el seguimiento de impresiones de iOS puede no ser preciso y no debe considerarse fiable.

Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### Implementación del rastreo de clics {#push-click-tracking-iOS}

Para el rastreo de clics, tendrá que enviar el valor &quot;2&quot; para la acción al llamar a `collectMessageInfo()` o `trackAction()` funciones.
Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

Ahora, cuando envía notificaciones push, debe añadir una categoría. En este caso, lo llamamos &quot;PREDETERMINADO&quot;.

![](assets/tracking_push.png)

A continuación, para gestionar el **[!UICONTROL Dismiss]** y enviar una información de seguimiento: debe añadir lo siguiente:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Implementación del seguimiento abierto {#push-open-tracking-iOS}

Deberá enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia o abre mediante una notificación push, no se produce ningún evento de seguimiento.

Para las entregas creadas antes de la versión 21.1 o las entregas con plantilla personalizada, consulte esta sección [sección](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

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
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```

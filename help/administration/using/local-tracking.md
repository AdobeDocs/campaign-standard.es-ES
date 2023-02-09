---
title: Implementación del seguimiento local
description: Obtenga información sobre cómo garantizar que el seguimiento de notificaciones push se haya implementado correctamente en iOS y Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 1%

---

# Implementación del seguimiento local {#local-tracking}

## Acerca del seguimiento local {#about-local-tracking}

En esta página, aprenda a garantizar que el seguimiento de notificaciones locales se haya implementado correctamente. Tenga en cuenta que esto implica que la notificación local ya se ha configurado.

El seguimiento de notificaciones locales se puede dividir en tres tipos:

* **Impresiones locales** - Cuando se ha enviado una notificación local al dispositivo y se encuentra en el centro de notificaciones, pero no se ha tocado en absoluto. En la mayoría de los casos, el número de impresiones debe ser similar si no es el mismo que el número entregado. Garantiza que el dispositivo obtuvo el mensaje y reenvía esa información al servidor.

* **Clic local** : cuando se envía una notificación local al dispositivo y el usuario ha hecho clic en la notificación. El usuario quería ver la notificación (que a su vez pasará al seguimiento abierto local) o rechazar la notificación.

* **Apertura local** : cuando se envía una notificación local al dispositivo y el usuario ha hecho clic en la notificación que provoca que la aplicación se abra. Esto es similar al clic local, excepto que una apertura local no se activará si se descarta la notificación.

Para implementar el seguimiento para Adobe Campaign Standard, la aplicación móvil debe incluir el SDK móvil en la aplicación. Estos SDK están disponibles en [!DNL Adobe Mobile Services].

Para enviar la información de seguimiento, hay tres variables que se deben enviar: dos son parte de los datos recibidos de Adobe Campaign y el otro es una variable de acción que dicta si es una impresión, un clic o una apertura.

| Variable  | Valor |
| :-: | :-: |
| deliveryId | `deliveryId` a partir de datos entrantes (similar al seguimiento push donde `_dld` se utiliza) |
| broadlogId | `broadlogId` a partir de datos entrantes (similar al seguimiento push donde `_mld` se utiliza) |
| acción | &quot;1&quot; para Open, &quot;2&quot; para Click y &quot;7&quot; para Impression |

## Implementación del seguimiento de impresión local {#implement-local-impression-tracking}

El SDK de Adobe Experience Platform Mobile enviará automáticamente el evento de impresión tanto para Android como para iOS sin ninguna configuración adicional.

## Implementación del rastreo de clics {#implementing-click-tracking}

Para el rastreo de clics, debe enviar el valor &quot;2&quot; para la acción cuando llame a `collectMessageInfo()` o `trackAction()` funciones.

### Para Android {#implement-click-tracking-android}

Para rastrear clics, se deben implementar dos escenarios:

* El usuario ve la notificación, pero la borra.

   Para rastrear clics en caso de despido, agregue el receptor de difusión `NotificationDismissalHandler` en el archivo AndroidManifest del módulo de la aplicación.

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* El usuario ve la notificación y hace clic en ella, lo que lo convierte en un seguimiento abierto.

   Este escenario debería producir un clic y una apertura. El seguimiento de este clic formará parte de la implementación necesaria para rastrear la apertura. Consulte [Implementación del seguimiento abierto](#implement-open-tracking).

### Para iOS {#implement-click-tracking-ios}

Para enviar la información de rastreo de clics, debe añadir lo siguiente:

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Implementación del seguimiento abierto {#implement-open-tracking}

Debe enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia o abre mediante una notificación local, no se produce ningún evento de seguimiento.

### Para Android {#implement-open-tracking-android}

Para rastrear la apertura, debemos crear un objeto Intent. Los objetos de intención permiten que el sistema operativo Android realice una llamada al método cuando se hayan realizado determinadas acciones. En este caso, haga clic en la notificación para abrir la aplicación.

Este código se basa en la implementación del seguimiento de impresión de clics. Con la intención definida, ahora debe enviar la información de seguimiento de vuelta a Adobe Campaign. En este caso, Android View([!DNL Activity]) que activó la notificación se abrirá o pondrá en primer plano como resultado del clic por usuario. El objeto Intent de [!DNL Activity] contiene los datos de notificación que se pueden utilizar para realizar el seguimiento de la apertura.

MainActivity.java (extiende [!DNL Activity])

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

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Para iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```

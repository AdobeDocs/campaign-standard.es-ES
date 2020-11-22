---
solution: Campaign Standard
product: campaign
title: Implementación del seguimiento push
description: Este documento le permite asegurarse de que el seguimiento de notificaciones push se ha implementado correctamente en iOS y Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---


# Implementación de seguimiento local {#local-tracking}

## Acerca del seguimiento local {#about-local-tracking}

En esta página, aprenda a asegurarse de que el seguimiento de notificaciones locales se ha implementado correctamente. Tenga en cuenta que esto implica que la notificación local ya se ha configurado.

El seguimiento de notificaciones locales se puede dividir en tres tipos:

* **Impresiones** locales: cuando se ha enviado una notificación local al dispositivo y se encuentra en el centro de notificaciones, pero no se ha tocado en absoluto. En la mayoría de los casos, el número de impresiones debe ser similar si no es el mismo que el número entregado. Garantiza que el dispositivo obtuvo el mensaje y retransmite esa información al servidor.

* **Clic** local: cuando se ha enviado una notificación local al dispositivo y el usuario ha hecho clic en él. El usuario deseaba realizar la vista (que a su vez pasará al seguimiento abierto local) o descartar la notificación.

* **Apertura** local: cuando se envía una notificación local al dispositivo y el usuario hace clic en la notificación que hace que la aplicación se abra. Esto es similar al clic local, excepto que no se activará una apertura local si se descartó la notificación.

Para implementar el seguimiento para Adobe Campaign Standard, la aplicación móvil debe incluir SDK móvil en la aplicación. Estos SDK están disponibles en [!DNL Adobe Mobile Services].

Para enviar la información de seguimiento, hay tres variables que deben enviarse: dos son parte de los datos recibidos de Adobe Campaign y la otra es una variable de acción que dicta si es una impresión, un clic o una apertura.

| Variable  | Valor |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; de datos entrantes (similar al seguimiento push donde se usa&quot;_dld&quot;) |
| wideLogId | &quot;wideLogId&quot; de los datos entrantes (similar al seguimiento push donde se usa &quot;_mld&quot;) |
| action | &quot;1&quot; para Open, &quot;2&quot; para Click y &quot;7&quot; para Impression |

## Implementación del seguimiento de impresión local {#implement-local-impression-tracking}

Para el seguimiento de impresiones, debe enviar el valor &quot;7&quot; para action cuando llame a las funciones collectMessageInfo() o trackAction().

### Para Android {#implement-local-impression-tracking-android}

El SDK de Adobe Experience Platform Mobile inicio el seguimiento de impresiones para la notificación local al activarla.

### Para iOS {#implement-local-impression-tracking-ios}

Para explicar cómo implementar el seguimiento de impresión, necesitamos comprender los tres estados de una aplicación:

* **Primer plano**: cuando la aplicación está activa y en pantalla en primer plano.

* **Antecedentes**: cuando la aplicación no está en pantalla pero el proceso tampoco está cerrado. Al hacer clic en el botón de inicio con el doble, generalmente se muestran todas las aplicaciones en segundo plano.

* **Desactivado/Cerrado**: cuando el proceso de la aplicación ha sido eliminado. Si se cierra una aplicación, Apple no la llamará hasta que la aplicación se haya reiniciado. Esto significa que nunca podrá saber realmente cuándo se recibió la notificación en iOS.

Para que el seguimiento de impresiones siga funcionando mientras la aplicación se encuentra en segundo plano, debemos enviar &quot;Contenido disponible&quot; para que la aplicación sepa que es necesario realizar el seguimiento.

El SDK de Adobe Experience Platform Mobile inicio el seguimiento de impresiones para la notificación local al activarla.

>[!CAUTION]
>
>El seguimiento de impresiones de iOS no es preciso y no debe considerarse de forma fiable.

## Implementación del rastreo de clics {#implementing-click-tracking}

Para el rastreo de clics, debe enviar el valor &quot;2&quot; para action cuando llame a las funciones collectMessageInfo() o trackAction().

### Para Android {#implement-click-tracking-android}

Para rastrear clics, es necesario administrar dos escenarios:

* El usuario ve la notificación pero la borra.

* El usuario ve la notificación y hace clic en ella, lo que lo convierte en un seguimiento abierto.

El SDK de Adobe Experience Platform Mobile rastrea el primer escenario de clic.

### Para iOS {#implement-click-tracking-ios}

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

A continuación, para gestionar el despido y enviar una información de seguimiento, debe agregar lo siguiente:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## Implementación del seguimiento abierto {#implement-open-tracking}

Debe enviar &quot;1&quot; y &quot;2&quot;, ya que el usuario debe hacer clic en la notificación para abrir la aplicación. Si la aplicación no se inicia/abre mediante una notificación local, no se produce ningún evento de seguimiento.

### Para Android {#implement-open-tracking-android}

Para rastrear la apertura, necesitamos crear intención. Los objetos de intención permiten que el sistema operativo Android llame al método cuando se hayan realizado determinadas acciones; en este caso, haga clic en la notificación para abrir la aplicación.

Este código se basa en la implementación del seguimiento de impresión de clics. Con la intención establecida, ahora debe enviar la información de seguimiento a Adobe Campaign. En este caso, la Vista([!DNL Activity]) de Android que activó la notificación se abrirá o pondrá en primer plano como resultado del clic por usuario. El objeto de intención de [!DNL Activity] contiene los datos de notificación que pueden utilizarse para rastrear la apertura.

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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```

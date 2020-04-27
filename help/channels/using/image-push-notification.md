---
title: Mostrar una imagen desde una notificación push de Adobe Campaign Standard
description: Aprenda aquí a mostrar una imagen de una notificación push de Adobe Campaign en un dispositivo iOS.
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Mostrar una imagen desde una notificación push de Adobe Campaign Standard {#image-push}

>[!NOTE]
>
>Este documento solo se aplica a dispositivos iOS.

## Paso 1: Configurar notificación push {#set-up-push}

Los SDK de la plataforma de experiencia admiten la notificación push.

Un administrador de la interfaz de Adobe Campaign debe configurar las aplicaciones móviles que reciben notificaciones push.

Al configurar Adobe Campaign y Adobe Mobile Services, podrá utilizar los datos de su aplicación móvil para sus campañas. Para obtener más información, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Para enviar notificaciones push con una aplicación de SDK de Experience Cloud, una aplicación móvil debe configurarse en Adobe Experience Platform Launch y en Adobe Campaign. Para obtener más información, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Paso 2: Personalice la notificación push en Adobe Campaign {#customize-push}

Para ajustar la notificación push, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña una notificación push.

1. Cree una notificación push. Para obtener más información, consulte esta página.

1. En la página de contenido de notificaciones push, acceda a la sección Opciones avanzadas.

1. Introduzca la dirección URL del archivo en el campo URL de contenido de medios enriquecidos.
Para iOS 10 o superior, puede insertar archivos de imagen, gif, audio y vídeo.

   ![](assets/push_notif_advanced_6.png)

1. Previsualización y guarde la notificación push.

## Paso 3: Adaptar el código de la aplicación móvil {#mobile-app-code}

Después de personalizar la notificación push en Adobe Campaign, debe configurar la aplicación móvil para que muestre la imagen en los dispositivos.

>[!NOTE]
>
>Si su aplicación está en Objective-C, consulte la siguiente [documentación](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Si la aplicación está en Swift, siga los pasos a continuación:

1. Abra el proyecto de xCode.

1. En el proyecto Xcode, seleccione **Archivo** > **Nuevo** > **Destinatario**.

1. Seleccione Extensión del servicio de notificaciones.

   ![](assets/push_notif_advanced_12.png)

1. Compruebe que se crea la clase de archivo **NotificationService.swift** .

1. Edite esta clase y reemplace el contenido predeterminado por lo siguiente.
Esto permite que la aplicación gestione el parámetro entrante con la dirección URL de la imagen, lo analice, lo copie localmente y, a continuación, lo muestre desde la notificación push.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

El dispositivo móvil debe recibir la siguiente carga útil mientras se envía la notificación.

La dirección URL de la imagen se asigna a la clave media-attachment-url. Es el par clave/valor que debe gestionar desde la perspectiva del código de la aplicación para descargar y mostrar la imagen.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Paso 4: Prueba de envío de la notificación push {#test-send-push}

Ahora puede probar la creación de la aplicación y el envío creado en el paso 2 anterior. Para obtener más información sobre cómo preparar y enviar la notificación push, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)


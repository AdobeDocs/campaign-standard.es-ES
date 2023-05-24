---
title: Mostrar una imagen desde una notificación push de Adobe Campaign Standard
description: Obtenga información aquí sobre cómo mostrar una imagen desde una notificación push de Adobe Campaign en un dispositivo iOS
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 18%

---

# Adición de imágenes y vídeos en iOS {#image-push}

>[!NOTE]
>
>Este documento solo se aplica a dispositivos iOS.

En este documento, aprenderá a mostrar una imagen desde una notificación push de Adobe Campaign Standard iOS.

## Paso 1: Configurar la notificación push {#set-up-push}

Los SDK de Experience Platform admiten las notificaciones push.

Las aplicaciones móviles que reciben notificaciones push deben ser configuradas por un administrador en la interfaz de Adobe Campaign.

Al configurar Adobe Campaign y Adobe Mobile Services, podrá utilizar los datos de su aplicación móvil para sus campañas. Para obtener más información, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Para enviar notificaciones push con una aplicación de SDK de Experience Cloud, se debe configurar una aplicación móvil en la interfaz de usuario de recopilación de datos y en Adobe Campaign. Para obtener más información, consulte esta [página](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Paso 2: Personalizar la notificación push en Adobe Campaign {#customize-push}

Para modificar una notificación push, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña una notificación push.

1. Creación de una notificación push. Para obtener más información, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

1. En la página de contenido de las notificaciones push, acceda al **[!UICONTROL Advanced options]** sección.

1. Introduzca la dirección URL del archivo en la **[!UICONTROL Rich media content URL]** field.
Para iOS 10 o superior, puede insertar archivos de imagen, gif, audio y vídeo.

   ![](assets/push_notif_advanced_6.png)

1. Previsualice y guarde la notificación push.

## Paso 3: Adaptar el código de la aplicación móvil {#mobile-app-code}

Después de personalizar la notificación push en Adobe Campaign, debe configurar la aplicación móvil para que muestre la imagen en los dispositivos.

>[!NOTE]
>
>Si su aplicación está en Objective-C, consulte lo siguiente [documentación](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Si la aplicación está en [!DNL Swift], siga los pasos a continuación:

1. Abra su [!DNL Xcode] proyecto.

1. En su [!DNL Xcode] proyecto, seleccione **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Seleccione **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Compruebe que la variable **NotificationService.swift** se crea la clase de archivo.

1. Edite esta clase y reemplace el contenido predeterminado por el siguiente.
Esto permite a la aplicación gestionar el parámetro entrante con la URL de la imagen, analizarlo, copiarlo localmente y luego mostrarlo desde la notificación push.

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

La dirección URL de imagen está asignada con la clave media-attachment-url. Este es el par clave/valor que debe gestionar desde la perspectiva del código de la aplicación para descargar y mostrar la imagen.

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

## Paso 4: Probar el envío de la notificación push {#test-send-push}

Ahora puede probar la creación de la aplicación y la entrega que ha creado en el paso 2 anterior. Para obtener más información sobre la preparación y el envío de notificaciones push, consulte esta sección [página](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

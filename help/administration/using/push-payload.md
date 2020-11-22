---
solution: Campaign Standard
product: campaign
title: Explicación de la estructura de carga útil de las notificaciones push de Campaign Standard
description: Este documento tiene por objeto describir la estructura de la carga útil recibida en las aplicaciones móviles.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---


# Explicación de la estructura de carga de las notificaciones push {#push-payload}

Adobe Campaign le permite enviar notificaciones push personalizadas y segmentadas en dispositivos móviles iOS y Android a aplicaciones móviles (aplicación móvil).

Todas las notificaciones push que se reciben en una aplicación móvil contienen información que la aplicación utiliza para mostrar la notificación push si se envía una notificación push de Alert y que es más probable que también realice un cálculo adicional, especialmente si se envía una notificación push silenciosa.

El código de la aplicación móvil recibe esta información en un controlador de evento que indica que se ha recibido una notificación push. Al enviar notificaciones push desde Adobe Campaign Standard, la información recibida en la aplicación móvil también puede contener información específica del Campaign Standard que puede utilizarse para aprovechar algunas funciones proporcionadas por el Campaign Standard. Además, la carga útil puede contener datos personalizados que la aplicación móvil puede utilizar.

Este documento describe la estructura de la carga útil recibida en una aplicación móvil cuando se envía correctamente una notificación push a una aplicación desde Adobe Campaign Standard.

>[!NOTE]
>
>La estructura de carga útil varía según el tipo de aplicación móvil (es decir, aplicación de iOS, aplicación de Android habilitada para FCM).

## Estructura de carga útil push {#push-payload-structure}

Esta sección detalla una estructura de una carga útil de muestra para varias plataformas móviles y describe los atributos principales que contiene. Es la estructura de la carga útil recibida en el código de la aplicación móvil en el controlador de evento que indica que se ha recibido una notificación push.

Los atributos de carga útil y sus valores variarán según las configuraciones proporcionadas en las opciones avanzadas de notificación Push. Esta sección también proporciona una asignación entre estas configuraciones en la interfaz de usuario del Campaign Standard y los atributos en la carga útil para aclarar cómo cambiará la carga útil al configurar una opción en el Campaign Standard.

### Para la aplicación móvil de iOS {#payload-structure-ios}

**Carga útil de muestra enviada desde Adobe Campaign a la aplicación iOS:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**Carga útil de muestra de JSON para usar con [iOS APNS Tester](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

La sección más importante de la carga útil es el diccionario de aplicaciones, que contiene claves definidas por Apple y se utiliza para determinar cómo el sistema que recibe la notificación debe alertar al usuario, si es que lo hace. Esta sección contiene claves predefinidas que la aplicación móvil utiliza para formular el comportamiento de la notificación push.

En los documentos para desarrolladores de Apple encontrará información detallada sobre los atributos dentro de las aplicaciones: [Creación de la carga útil](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)de notificación remota.

### Para la aplicación Android {#payload-structure-android}

**Ejemplo de carga útil enviada desde Adobe Campaign a una aplicación de Android**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**Carga útil de muestra JSON para usar el probador [Google FCM](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

La carga útil contiene un mensaje de datos que incluye todo el contenido del envío de notificaciones push, incluidos los pares de clave/valor personalizados, y la aplicación cliente debe gestionar el mensaje para generar y mostrar la notificación push, si es necesario o para agregar cualquier otra lógica empresarial.

Para comprender los aspectos de una carga útil androide, consulte Conceptos y opciones [de mensajería (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>La compatibilidad con los mensajes de notificación en la carga útil de Android se eliminó a partir de enero de 2018 para permitir el inicio de la aplicación y pasar el control a la aplicación móvil sin necesidad de que el usuario interactúe con la aplicación.

### Asignación entre configuraciones de Campaign Standard y atributos de carga útil {#mapping-payload}

| Configuración de campaña | Atributo afectado en iOS | Atributo afectado en Android | Descripción |
|:-:|:-:|:-:|:-:|
| Título del mensaje <br>Cuerpo del mensaje | alerta → descripción de título <br> → cuerpo | title <br>body | Estos datos contienen datos específicos del mensaje de alerta.<br>El título y las claves de cuerpo proporcionan el contenido de la alerta. |
| Reproducir un sonido | sonido | sonido | Un sonido personalizado para reproducir con la alerta. |
| Valor del distintivo | distintivo | distintivo | Un valor entero que se usará para marcar el icono de la aplicación. |
| Añadir un vínculo profundo | uri | NA | Un vínculo profundo le permite llevar a los usuarios directamente al contenido ubicado dentro de la aplicación (en lugar de abrir una página del explorador web). |
| Categoría | categoría | categoría | Para mostrar acciones personalizadas con una notificación remota. <br>La tecla de categoría ayuda al sistema a mostrar las acciones de esa categoría como botones en la interfaz de alerta. |
| Campos personalizados | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Cualquier dato personalizado que desee enviar a la aplicación. |
| URL de contenido de medios enriquecidos (archivos de imagen, gif, audio y vídeo)<br>(solo aplicable a iOS 10 o posterior) | media-attachment-url | NA | URL de los archivos multimedia para agregar contenido enriquecido a la notificación. <br>Al proporcionar un valor para esta URL, el indicador de contenido mutable se envía automáticamente a la carga útil. <br> (Solo aplicable para iOS 10 o superior) |
| Contenido mutable <br> (solo aplicable para iOS 10 o superior) | mutable-content | NA | La extensión del servicio de notificaciones de la aplicación &quot;interceptará&quot; todas las notificaciones remotas con la clave de contenido mutable y le permitirá gestionar/manipular el contenido de la carga útil de la solicitud, que se puede utilizar para personalizar la notificación. Los casos de uso de esta función incluyen la descarga y visualización de varios medios, descifrando los datos cifrados presentes en la carga útil push. Encontrará más información en [Modificar la carga útil de una notificación](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)remota. <br>(Solo aplicable para iOS 10 o superior) |
| Contenido disponible | contenido disponible | NA | Al seleccionar esta opción, se activa la activación de una aplicación de iOS mientras se encuentra en estado de fondo/suspendido. El proceso de activación implica que la aplicación se ejecuta en segundo plano y que el controlador de evento adecuado responsable de la recepción de la carga útil de datos de notificaciones push obtiene un control y puede utilizar los datos para realizar cualquier cálculo, incluida, entre otras cosas, la creación de notificaciones push personalizadas y la visualización del mismo. Encontrará más información en el envío [de notificación](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)Despertar aplicación con notificación. |
| URL de contenido multimedia enriquecido (archivos de imagen)<br>(solo aplicable para Android) | NA | media-attachment-url | URL de los archivos de imagen para agregar contenido enriquecido a la notificación. |
| NA | _mId<br>_dId | _mId <br>_dId | Valores de la identificación de registroDiplomático y la identificaciónEntrega.<br>Estos atributos son obligatorios si la aplicación desea llamar a un postback de seguimiento para rastrear cuándo se hizo clic o abrió la notificación push. El servidor de aplicaciones calcula y envía internamente esta información sin la intervención del usuario.<br>Encontrará información sobre postbacks en esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback). |

### Cómo recuperar información de carga útil en el código de la aplicación móvil {#payload-information}

El código de la aplicación móvil recibe la información de carga útil que envía el servidor de aplicaciones en un controlador de evento que indica que se ha recibido una notificación push. Este evento variaría en función de la plataforma móvil en la que se esté trabajando y también en función de si la aplicación se está ejecutando en primer o segundo plano. La siguiente documentación le ayudará a identificar el controlador de eventos que desea gestionar en función de su caso de uso.

* Aplicaciones iOS: **Gestión de notificaciones** remotas en Notificaciones [](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)remotas.
* Aplicaciones de Android: [Recepción de mensajes en una aplicación cliente de Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Ejemplo para la aplicación móvil de iOS**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Ejemplo de aplicación FCM para dispositivos móviles Android**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```

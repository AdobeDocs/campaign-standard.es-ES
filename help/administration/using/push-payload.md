---
title: Explicación de la estructura de carga útil de las notificaciones push del Campaign Standard
description: El objetivo de este documento es describir la estructura de la carga útil recibida en las aplicaciones móviles.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 4%

---

# Explicación de la estructura de carga de las notificaciones push {#push-payload}

Adobe Campaign le permite enviar notificaciones push personalizadas y segmentadas a aplicaciones móviles (aplicación móvil) de iOS y Android.

Cada notificación push recibida en una aplicación móvil contiene información que la aplicación utiliza para mostrar la notificación push si se envía una notificación push de Alert y, probablemente, también realice algún cálculo adicional, especialmente si se envía una notificación push silenciosa.

El código de la aplicación móvil recibe esta información en un controlador de eventos que indica que se ha recibido una notificación push. Al enviar notificaciones push desde Adobe Campaign Standard, la información recibida en la aplicación móvil también puede contener información específica del Campaign Standard que se puede utilizar para aprovechar algunas funciones proporcionadas por el Campaign Standard. Además, la carga útil puede contener datos personalizados que la aplicación móvil puede consumir.

Este documento describe la estructura de la carga útil recibida en una aplicación móvil cuando una notificación push se envía correctamente a una aplicación desde Adobe Campaign Standard.

>[!NOTE]
>
>La estructura de carga varía según el tipo de aplicación móvil (es decir, la aplicación iOS, la aplicación Android habilitada para FCM).

## Estructura de la carga útil push {#push-payload-structure}

Esta sección detalla la estructura de una carga útil de ejemplo para varias plataformas móviles y describe los principales atributos que contiene. Esta es la estructura de la carga útil recibida en el código de la aplicación móvil en el controlador de eventos que indica que se ha recibido una notificación push.

Los atributos de carga útil y sus valores variarán según las configuraciones proporcionadas en las opciones avanzadas de notificaciones push. Esta sección también proporciona una asignación entre estas configuraciones en la interfaz de usuario del Campaign Standard y los atributos en la carga útil para aclarar cómo cambiará la carga útil al configurar una opción en el Campaign Standard.

### Para la aplicación móvil de iOS {#payload-structure-ios}

**Carga útil de muestra enviada desde la aplicación Adobe Campaign a iOS:**

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

**Carga útil de ejemplo JSON para usar con [iOS APNS Tester](https://pushtry.com/)**

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

Puede encontrar información detallada sobre los atributos dentro de las aplicaciones en los documentos para desarrolladores de Apple: [Creación de la carga útil de notificación remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Para la aplicación de Android {#payload-structure-android}

**Ejemplo de carga útil enviada de Adobe Campaign a la aplicación Android**

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

**Carga útil de muestra de JSON para usar [Google FCM Tester](https://pushtry.com/)**

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

La carga útil contiene un mensaje de datos que incluye todo el contenido de la entrega de notificaciones push, incluidos los pares de clave/valor personalizados, y la aplicación cliente debe gestionar el mensaje para generar y mostrar la notificación push (si es necesario) o, de lo contrario, añadir cualquier otra lógica empresarial.

Para comprender los aspectos de una carga útil de android, consulte [Conceptos y opciones de mensajería (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>La compatibilidad con los mensajes de notificación en la carga útil de Android se ha eliminado a partir de enero de 2018 para permitir el inicio de la aplicación y pasar el control a la aplicación móvil sin necesidad de que el usuario interactúe con la aplicación.

### Asignación entre configuraciones de Campaign Standard y atributos de carga útil {#mapping-payload}

| Configuración de campaña | Atributo afectado en iOS | Atributo afectado en Android | Descripción |
|:-:|:-:|:-:|:-:|
| Título del mensaje <br>Cuerpo del mensaje | alerta → título <br> alerta → cuerpo | title <br>body | Estos datos contienen datos específicos del mensaje de alerta.<br>El título y las claves del cuerpo proporcionan el contenido de la alerta. |
| Reproducir un sonido | sonido | sonido | Un sonido personalizado para reproducir con la alerta. |
| Valor del distintivo | distintivo | distintivo | Un valor entero que se utilizará para asignar un distintivo al icono de la aplicación. |
| Añadir un vínculo profundo | uri | NA | Un vínculo profundo le permite llevar a los usuarios directamente al contenido ubicado dentro de la aplicación (en lugar de abrir una página del explorador web). |
| Categoría | categoría | categoría | Para mostrar acciones personalizadas con una notificación remota. <br>La clave de categoría ayuda al sistema a mostrar las acciones para esa categoría como botones en la interfaz de alerta. |
| Campos personalizados | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Cualquier dato personalizado que desee enviar a su aplicación. |
| URL de contenido multimedia enriquecido (archivos de imagen, gif, audio y vídeo)<br>(Solo aplicable para iOS 10 o superior) | media-attachment-url | NA | URL de los archivos multimedia para añadir contenido enriquecido a la notificación. <br>Al proporcionar un valor para esta URL, el indicador de contenido mutable se envía automáticamente a la carga útil. <br> (Solo aplicable para iOS 10 o superior) |
| Contenido mutable <br> (Solo aplicable para iOS 10 o superior) | contenido mutable | NA | La extensión del servicio de notificaciones de su aplicación &quot;interceptará&quot; todas las notificaciones remotas con la clave de contenido mutable y le permitirá gestionar/manipular el contenido de la carga útil de la solicitud, que se puede utilizar para personalizar la notificación. Algunos casos de uso de esta función son la descarga y visualización de varios medios, lo que descifra los datos cifrados presentes en la carga útil push. Encontrará más información en [Modificación de la carga útil de una notificación remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Solo aplicable para iOS 10 o superior) |
| Contenido disponible | contenido disponible | NA | Al seleccionar esta opción, se habilita la activación de una aplicación de iOS mientras está en estado de fondo/suspendido. Despertar implica que la aplicación se ejecuta en segundo plano y que el controlador de eventos adecuado responsable de la recepción de la carga de datos de la notificación push obtiene un control y puede utilizar los datos para realizar cualquier cálculo, incluida, entre otras cosas, la creación de notificaciones push personalizadas y la visualización de lo mismo. Encontrará más información en [Activación de la aplicación con entrega de notificaciones](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL de contenido multimedia enriquecido (archivos de imagen)<br>(Solo aplicable para Android) | NA | media-attachment-url | URL de los archivos de imagen para añadir contenido enriquecido a la notificación. |
| NA | _mId<br>_dId | _mId <br>_dId | Valores de broadlogId y deliveryId.<br>Estos atributos son necesarios si la aplicación desea llamar a un postback de seguimiento para rastrear cuándo se hizo clic o abrió la notificación push. El servidor de aplicaciones calcula esta información y la envía internamente sin intervención del usuario.<br>En esta sección se puede encontrar información sobre los postbacks [página](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Cómo recuperar la información de carga útil en el código de la aplicación móvil {#payload-information}

La información de carga útil que envía el servidor de aplicaciones la recibe el código de la aplicación móvil en un controlador de eventos que indica que se recibió una notificación push. Este evento variaría en función de la plataforma móvil en la que se esté trabajando y también en función de si la aplicación se está ejecutando en primer o segundo plano. La siguiente documentación le ayuda a identificar el controlador de eventos que desea gestionar en función de su caso de uso.

* Aplicaciones de iOS: **Gestión de notificaciones remotas** en [Notificaciones remotas](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
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

**Ejemplo de aplicación FCM para Android Mobile**

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

---
title: Próximos cambios del canal de notificaciones push
description: Próximos cambios del canal de notificaciones push
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: db035a41515e94836bdfbfc3d620586dc1f5ce31
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# Cambios del canal de notificaciones push {#push-upgrade}

Puede utilizar Campaign para enviar notificaciones push a dispositivos Android y iOS. Para ello, Campaign se basa en servicios de suscripción específicos. Algunos cambios importantes en el servicio Android Firebase Cloud Messaging (FCM) se lanzarán en 2024 y pueden afectar a su implementación de Adobe Campaign. Es posible que sea necesario actualizar la configuración de los servicios de suscripción para los mensajes push de Android a fin de admitir este cambio.

Además, Adobe recomienda encarecidamente pasar a la conexión basada en tokens a APNS en lugar de a una conexión basada en certificados, que es más segura y escalable.

Para garantizar un servicio ininterrumpido, debe actualizar las aplicaciones móviles registradas con Adobe Campaign para incorporar los mecanismos de autenticación más recientes para FCM (Android) y APN (iOS).


[Obtenga más información sobre cómo configurar los certificados de las aplicaciones móviles en Adobe Campaign Standard](configuring-a-mobile-application.md#channel-specific-config)


## Servicio Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### ¿Qué ha cambiado? {#fcm-changes}

Como parte del esfuerzo continuo de Google por mejorar sus servicios, las API de FCM existentes dejarán de usarse el **20 de junio de 2024**. Obtenga más información acerca del protocolo HTTP de Firebase Cloud Messaging en [Documentación de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

A partir de la versión [24.1](../../rn/using/release-notes.md), Adobe Campaign Standard admite las API HTTP v1 para enviar mensajes de notificación push de Android.

### ¿Se ha visto afectado? {#fcm-impact}

Si ya utiliza Adobe Campaign Standard para enviar notificaciones push, la implementación debe actualizarse.

La transición a las API más recientes es obligatoria para evitar cualquier interrupción del servicio.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below

* If any of your active push notification service uses the **HTTP (legacy)** API, your setup will be directly impacted by this change. You must review your current configurations and move to the newer APIs as described below.

* If your setup exclusively uses the **HTTP v1** API for Android push notifications, then you are already in compliance and no further action will be required on your part.-->

### ¿Cómo realizar la actualización? {#fcm-transition-procedure}

#### Requisitos previos {#fcm-transition-prerequisites}

* La compatibilidad con el modo **HTTP v1 API** se ha agregado en la versión 24.1. Si su entorno se está ejecutando en una versión anterior, un requisito previo para este cambio es actualizar su entorno a la [última versión de Campaign Standard](../../rn/using/release-notes.md).

* El archivo JSON de la cuenta del servicio Android Firebase Admin SDK es necesario para mover la aplicación móvil a HTTP v1. Obtenga información sobre cómo obtener este archivo en [Documentación de Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Si sigue utilizando esta versión heredada del SDK, debe actualizar la implementación con el SDK de Adobe Experience Platform. Obtenga información sobre cómo migrar al SDK de Adobe Experience Platform en [este artículo](sdkv4-migration.md).

* Asegúrese de tener el permiso **Configuración de aplicación móvil** en la recopilación de datos de Adobe Experience Platform Mobile antes de realizar los pasos siguientes. [Más información](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html?lang=es#adobe-experience-platform-data-collection-permissions){target="_blank"}.


#### Procedimiento de transición {#fcm-transition-steps}

Para mover el entorno a HTTP v1, siga estos pasos:

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Seleccione la aplicación móvil específica que requiere la actualización del certificado.

1. Marque la casilla **[!UICONTROL Update app credentials]**.

   ![](assets/push_technote_5.png)

1. Proporcione el ID de aplicación (nombre del paquete de Android) del archivo `build.gradle` de su proyecto de Android. Por ejemplo, `com.android.test.testApp`. Asegúrese de utilizar ID diferentes para los entornos de ensayo y producción.

1. Cargue el archivo de clave privada JSON de Android.

   ![](assets/push_technote_3.png)

1. Haga clic en el botón **Save**.

>[!NOTE]
>
>Una vez aplicados estos cambios, todos los nuevos envíos de notificaciones push a dispositivos Android utilizan la API HTTP v1. Los envíos push existentes en reintento, en curso y en uso siguen utilizando la API HTTP (heredada).


## Servicio de notificaciones push de Apple iOS (APN) {#apns-push-upgrade}

### ¿Qué ha cambiado? {#ios-changes}

Como recomienda Apple, debe proteger sus comunicaciones con el servicio de notificaciones push de Apple (APN) mediante tokens de autenticación sin estado.

La autenticación basada en tokens ofrece una forma sin estado de comunicarse con APNS. La comunicación sin estado es más rápida que la comunicación basada en certificados porque no requiere que los APN busquen el certificado u otra información relacionada con el servidor de su proveedor. El uso de la autenticación basada en token ofrece otras ventajas:

* Puede utilizar el mismo token desde varios servidores de proveedores.

* Puede utilizar un token para distribuir notificaciones para todas las aplicaciones de la empresa.

Obtenga más información acerca de las conexiones basadas en tokens a APN en [Documentación para desarrolladores de Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Standard admite conexiones basadas en tokens y en certificados. Si la implementación depende de una conexión basada en certificados, Adobe le recomienda encarecidamente que la actualice a una conexión basada en tokens.

### ¿Se ha visto afectado? {#ios-impact}

Si la implementación actual depende de solicitudes basadas en certificados para conectarse a APNS, se verá afectado. Se recomienda la transición a una conexión basada en token.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below:

![](assets/filter-services-ios.png)


* If any of your active push notification service uses the **Certificate-based authentication** mode (.p12), your current implementations should be reviewed and moved to a **Token-based authentication** mode (.p8) as described below.

* If your setup exclusively uses the **Token-based authentication** mode for iOS push notifications, then your implementation is already up-to-date and no further action will be required on your part.-->

### ¿Cómo realizar la actualización? {#ios-transition-procedure}

#### Requisitos previos {#ios-transition-prerequisites}

* La compatibilidad con el modo **Autenticación basada en tokens** se ha agregado en [24.1](../../rn/using/release-notes.md). Si su entorno se está ejecutando en una versión anterior, un requisito previo para este cambio es actualizar su entorno a la [última versión de Campaign Standard](../../rn/using/release-notes.md).

* Necesita una clave de firma de token de autenticación de APNS para generar los tokens que utiliza su servidor. Usted solicita esta clave desde su cuenta de desarrollador de Apple, como se explica en [Documentación para desarrolladores de Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.


#### Procedimiento de transición {#ios-transition-steps}

Para mover las aplicaciones móviles de iOS al modo de autenticación basado en tokens, siga estos pasos:

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Seleccione la aplicación móvil específica que requiere la actualización del certificado.

1. Marque la casilla **[!UICONTROL Update app credentials]**.

   ![](assets/push_technote_2.png)

1. Proporcione el **ID de aplicación** (ID de paquete de iOS). Puede encontrar el ID del paquete de iOS (ID de aplicación) en el destino principal de la aplicación en Xcode.

1. Cargue su **archivo de certificado p8 de iOS**.

1. Complete la configuración de conexión de APNS **[!UICONTROL Key Id]** y **[!UICONTROL iOS Team Id]**.

   ![](assets/push_technote_4.png)

1. Haga clic en **[!UICONTROL Save]**.

La aplicación de iOS ahora se mueve al modo de autenticación basado en token.

## Preguntas frecuentes{#push-upgrade-faq}

+++¿Podemos mantener el mismo appID en la instancia de stage y prod?

En el caso de las aplicaciones móviles de iOS, puede utilizar el mismo ID de aplicación, que es el ID del paquete de aplicaciones de iOS, para los entornos de ensayo y producción. Sin embargo, en Android, el ID de la aplicación debe ser único para cada entorno. Por lo tanto, se recomienda anexar &quot;fase&quot; al ID de aplicación creado en el entorno de ensayo

+++


+++¿Podemos migrar solo la aplicación de Android?

No, tanto las aplicaciones de Android como las de iOS deben migrarse según los pasos descritos anteriormente.

+++

+++¿Qué tipo de verificación necesitamos realizar después de la migración?

Nuestra recomendación es llevar a cabo la validación funcional de todos los casos de uso relacionados con push.

+++

+++¿Qué hacer cuando se produce el error &quot;No autorizado&quot; al guardar la aplicación móvil?

Parece ser un problema de permisos relacionado con la recopilación de datos de Adobe Experience Platform. Para resolver esto, debe agregar los permisos &quot;Mobile&quot; y &quot;Mobile App Configuration&quot; en Adobe Admin Console, tal como se describe en la sección Requisitos previos de este artículo.

+++

+++¿Se requieren cambios en el código de la aplicación móvil?

No, solo se requieren los cambios relacionados con la configuración en Firebase y en la cuenta de desarrollador de aplicaciones. No es necesario realizar cambios en la aplicación móvil del cliente.

+++

+++¿Es necesario actualizar el certificado de iOS cada año?

No, después de esta migración, no es necesario actualizar el certificado de iOS cada año.

+++

+++¿Qué sucede si no se realiza esta migración?

Los mensajes push de Android empezarán a fallar después del 20 de junio de 2024, según la notificación de Google. [Más información](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

+++

+++¿Pueden los clientes volver a migrar a FCM después de completar la migración a FCMv1?

Sí, los clientes podrán volver a migrar a FCM hasta el 20 de junio de 2024. Después de esta fecha, la opción de migración ya no estará disponible.

+++

+++¿Se admite la migración de la API HTTP v1 en la aplicación móvil SDK V4?

No, los clientes deben migrar primero su aplicación móvil al SDK V5 y, a continuación, continuar con la migración anterior. Deben hacerlo como una prioridad, ya que su servicio push empezará a fallar a partir de junio de 2024, según la notificación de Google.

+++

+++¿El cambio en la instancia de fase tendrá algún impacto en la instancia de producción?

No, los cambios en la aplicación móvil de fase no afectan a la instancia de producción.

+++
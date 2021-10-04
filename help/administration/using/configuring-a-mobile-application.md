---
title: Configuración de una aplicación móvil
description: Descubra cómo configurar Adobe Campaign para que envíe notificaciones push o mensajes en la aplicación mediante SDK V4 o SDK de Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 6%

---

# Configuración de una aplicación móvil{#configuring-a-mobile-application}

## Configuración de una aplicación móvil mediante los SDK para Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Las implementaciones de notificaciones push y en la aplicación deben realizarlas usuarios expertos. Para obtener ayuda, póngase en contacto con el ejecutivo de cuentas de Adobe o con el socio de servicios profesionales.

Para enviar notificaciones push y mensajes en la aplicación con la aplicación SDK de Experience Platform, se debe configurar una aplicación móvil en el Experience Platform Launch de Adobe Experience Platform Experience Platform y configurarla en Adobe Campaign.

Para obtener más información sobre la función obsoleta SDK de la versión 4 de Mobile, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Una vez configurada una aplicación móvil, puede recuperar los datos PII recopilados para crear o actualizar perfiles de la base de datos. Para obtener más información, consulte esta sección: [Creación y actualización de información de perfil basada en datos de aplicaciones móviles](../../channels/using/updating-profile-with-mobile-app-data.md).

Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK para Adobe Experience Platform, consulte esta [página](https://helpx.adobe.com/es/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para completar la configuración, complete los siguientes pasos:

1. En Adobe Campaign, asegúrese de que puede acceder a lo siguiente:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Si no es así, póngase en contacto con el equipo de su cuenta.

1. Compruebe que el usuario tiene los permisos necesarios en Adobe Campaign Standard y Experience Platform Launch.
   * En Adobe Campaign Standard, asegúrese de que el usuario de IMS forma parte de los perfiles de usuario y administrador estándar del producto. Este paso permite al usuario iniciar sesión en Adobe Campaign Standard, navegar a la página de la aplicación móvil del SDK de Experience Platform y ver las propiedades de la aplicación móvil que ha creado en Experience Platform Launch.

   * En Experience Platform Launch, asegúrese de que el usuario de IMS forme parte de un perfil de producto de Experience Platform Launch.
Este paso permite al usuario iniciar sesión en Experience Platform Launch para crear y ver las propiedades. Para obtener más información sobre los perfiles de producto en Experience Platform Launch, consulte Creación de un perfil de producto. En el perfil de producto, no debe haber permisos establecidos en la empresa o en las propiedades, pero el usuario debe poder iniciar sesión.

   Para completar tareas adicionales como instalar una extensión, publicar una aplicación, configurar entornos, etc., debe configurar permisos en el perfil del producto.

1. En el Experience Platform Launch, cree un **[!UICONTROL Mobile property]**. Para obtener más información, consulte [Configuración de una propiedad móvil](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. En el Experience Platform Launch, haga clic en la pestaña **[!UICONTROL Extensions]**, vaya a **[!UICONTROL Catalog]** y busque la extensión **[!UICONTROL Adobe Campaign Standard]**. Para obtener más información, consulte [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Para admitir casos de uso de ubicación en el Campaign Standard, instale la extensión **[!UICONTROL Places]** y la extensión **[!UICONTROL Places Monitor]**.
   * Instale la extensión **[!UICONTROL Places]** en el Experience Platform Launch. Consulte [esta página](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Instale la extensión **[!UICONTROL Places Monitor]** en el Experience Platform Launch. Consulte [esta página](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. En Adobe Campaign Standard, configure la propiedad móvil que ha creado en Experience Platform Launch. Consulte [Configuración de la aplicación de Adobe Experience Platform Launch en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Añada la configuración específica del canal a la configuración de la aplicación móvil.
Para obtener más información, consulte [Configuración de aplicaciones específicas del canal en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Si es necesario, puede eliminar la propiedad del Experience Platform Launch.
Para obtener más información, consulte [Eliminación de la aplicación Experience Platform Launch](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronización del AEPSDK de la aplicación móvil desde el flujo de trabajo técnico de Launch {#aepsdk-workflow}

Después de crear y configurar la propiedad móvil en Experience Platform Launch, el flujo de trabajo técnico **[!UICONTROL Sync Mobile app AEPSDK from Launch]** sincronizará las propiedades móviles de Adobe Launch importadas en Adobe Campaign Standard.

De forma predeterminada, el flujo de trabajo técnico se inicia cada 15 minutos. Si es necesario, se puede reiniciar manualmente:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra el flujo de trabajo **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** .

   ![](assets/launch_10.png)

1. Haga clic en la actividad **[!UICONTROL Scheduler]**.

1. Seleccione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

El flujo de trabajo ahora se reiniciará y sincronizará con las propiedades móviles de Launch de Adobe importadas en Adobe Campaign Standard.

## Configuración de la aplicación de Adobe Experience Platform Launch en Adobe Campaign {#set-up-campaign}

Para utilizar una propiedad móvil de Experience Platform Launch en Campaign, también debe configurar esta propiedad en Adobe Campaign. En Adobe Campaign, asegúrese de que el usuario de IMS forma parte de los perfiles de usuario y administrador estándar del producto.

Debe esperar a que se ejecute el flujo de trabajo técnico y sincronizar la propiedad móvil de Launch con Adobe Campaign. A continuación, puede configurarlo en Adobe Campaign.

Para obtener más información sobre el flujo de trabajo técnico de la aplicación móvil de sincronización AEPSDK desde Launch, consulte esta [sección](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>De forma predeterminada, los administradores con la unidad organizativa configurada en ALL pueden editar la aplicación móvil.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleccione la aplicación móvil creada en Experience Platform Launch.
Su **[!UICONTROL Property Status]** debe ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >De forma predeterminada, para recuperar la lista de aplicaciones móviles creadas en Launch de Adobe, el Campaign Standard utiliza el valor definido en la opción NmsServer_URL para buscar propiedades coincidentes.
   >
   >En algunos casos, el punto final de Campaign para una aplicación móvil puede ser diferente del definido en NmsServer_URL. En ese caso, defina el punto final en la opción Launch_URL_Campaign . Campaign utilizará el valor de esta opción para buscar propiedades coincidentes en Adobe Launch.

   ![](assets/launch_4.png)

1. Puede cambiar la unidad organizativa de la aplicación móvil en la sección **[!UICONTROL Access Authorization]** para limitar el acceso a esta aplicación móvil a unidades de organización específicas. Para obtener más información, consulte esta página.

   En este caso, el administrador puede asignar unidades organizativas secundarias seleccionándolas en la lista desplegable.

   ![](assets/launch_12.png)

1. Para establecer la conexión entre Campaign y el Experience Platform Launch, haga clic en **[!UICONTROL Save]**.

1. Compruebe que el estado de la aplicación móvil haya cambiado de **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Cuando la extensión de Experience Platform Launch Campaign muestra que la clave se ha configurado correctamente, también puede comprobar que la propiedad se ha configurado correctamente en Campaign.

   ![](assets/launch_5.png)

1. Para que esta configuración tenga efecto, los cambios deben publicarse en Experience Platform Launch.

   Para obtener más información, consulte [Configuración de publicación](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configuración de aplicaciones específicas del canal en Adobe Campaign {#channel-specific-config}

La aplicación móvil ya está lista para su uso en Campaign para notificaciones push o envíos en la aplicación. Ahora puede configurarlo aún más si es necesario para crear eventos que almacenen en déclencheur los mensajes en la aplicación o carguen certificados push.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleccione la aplicación móvil que ha creado y configurado en Experience Platform Launch.

1. En la pestaña **[!UICONTROL Mobile application properties]**, puede empezar a añadir eventos disponibles en la aplicación móvil para los mensajes en la aplicación.

1. Para configurar los eventos, haga clic en **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Escriba un nombre y una descripción.

   ![](assets/launch_7.png)

1. Haga clic en **[!UICONTROL Add]**.

   El evento ya está disponible en la ficha Déclencheur al crear un mensaje en la aplicación. Para obtener más información, consulte [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. En la sección **[!UICONTROL Device-specific settings]** de un panel de aplicaciones móviles, proporcione los detalles de la aplicación, incluido el certificado para iOS y la clave de servidor para Android para cada dispositivo.

   Una vez cargado el certificado, un mensaje le notifica que la carga se ha realizado correctamente y muestra la fecha de caducidad del certificado.

   >[!NOTE]
   >
   >Después de añadir correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede añadir una plataforma APNS (producción o simulación de pruebas) a la aplicación MCPNS.

   ![](assets/launch_8.png)

1. Haga clic en la pestaña **[!UICONTROL Mobile application subscribers]** para ver una lista de suscriptores y otra información sobre estos suscriptores, por ejemplo, si han excluido sus notificaciones.

## Eliminación de la aplicación Adobe Experience Platform Launch {#delete-app}

No se puede deshacer la eliminación de la aplicación Experience Platform Launch.

>[!CAUTION]
>
>No se puede deshacer la eliminación de la aplicación Experience Platform Launch.

Para eliminar la aplicación Experience Platform Launch, complete los pasos en [Eliminación de propiedades móviles](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Una vez eliminada la aplicación, en Adobe Campaign, compruebe si el estado de la propiedad de la aplicación se ha actualizado correctamente a Eliminado en Launch.

Al hacer clic en la aplicación en Adobe Campaign, puede elegir eliminar completamente esta aplicación de Adobe Campaign haciendo clic en Eliminar de Campaign.

![](assets/launch_9.png)

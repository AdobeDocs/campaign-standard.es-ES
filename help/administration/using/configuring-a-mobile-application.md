---
title: Configuración de una aplicación móvil
description: Obtenga información sobre cómo configurar Adobe Campaign para que envíe notificaciones push o mensajes en la aplicación mediante el SDK de Experience Platform
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 1619e1f434742b89d0f0802c40e82d7b59773a59
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 2%

---

# Configuración de una aplicación móvil{#configuring-a-mobile-application}

## Configuración de una aplicación móvil mediante los SDK de Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launch se ha convertido en un conjunto de tecnologías de recopilación de datos en Adobe Experience Platform. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte la [siguiente documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html) para obtener una referencia consolidada de los cambios terminológicos.

Tenga en cuenta que las implementaciones de notificaciones push e en la aplicación deben realizarlas usuarios expertos. Para obtener ayuda, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales.

Para enviar notificaciones push y mensajes en la aplicación con la aplicación de SDK de Experience Platform, se debe configurar una aplicación móvil en la interfaz de usuario de recopilación de datos y en Adobe Campaign.

Una vez configurada una aplicación móvil, puede recuperar los datos PII que recopiló para crear o actualizar perfiles de la base de datos. Para obtener más información, consulte esta sección: [Creación y actualización de información de perfil basada en datos de aplicaciones móviles](../../channels/using/updating-profile-with-mobile-app-data.md).

Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante el uso de los SDK para Adobe Experience Platform, consulte esta sección [página](../../administration/using/supported-mobile-use-cases.md).

Para completar la configuración, complete los siguientes pasos:

1. En Adobe Campaign, asegúrese de que puede acceder a lo siguiente:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Si no es así, póngase en contacto con el equipo de su cuenta.

1. Compruebe que el usuario tenga los permisos necesarios en Adobe Campaign Standard y en Adobe Experience Platform.
   * En Adobe Campaign Standard, asegúrese de que el usuario de IMS forme parte de los Perfiles de producto de usuario y administrador estándar. Este paso permite al usuario iniciar sesión en Adobe Campaign Standard, navegar a la página de la aplicación móvil del SDK de Experience Platform y ver las propiedades de la aplicación móvil que ha creado en la IU de recopilación de datos.

   * En la IU de recopilación de datos, asegúrese de que el usuario de IMS forme parte de un perfil de producto de Experience Platform Launch.
Este paso permite al usuario iniciar sesión en la interfaz de usuario de recopilación de datos para crear y ver las propiedades. Para obtener más información sobre los perfiles de producto en la IU de recopilación de datos, consulte [Crear el perfil de producto](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html#gain-admin-rights-for-a-tags-product-profile). En el perfil del producto no debe haber permisos establecidos en la empresa o las propiedades, pero el usuario debe poder iniciar sesión.

   Para completar tareas adicionales como instalar una extensión, publicar una aplicación, configurar entornos, etc., debe establecer permisos en el perfil del producto.

1. En la IU de recopilación de datos, cree un **[!UICONTROL Mobile property]**. Para obtener más información, consulte [Configuración de una propiedad móvil](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property).

1. En la IU de recopilación de datos, haga clic en **[!UICONTROL Extensions]** pestaña, vaya a **[!UICONTROL Catalog]** y busque la variable **[!UICONTROL Adobe Campaign Standard]** extensión. Para obtener más información, consulte [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

1. Para admitir casos de uso de ubicación en Campaign Standard, instale **[!UICONTROL Places]** en la IU de recopilación de datos. Consulte [esta página](https://developer.adobe.com/client-sdks/solution/places).

1. En Adobe Campaign Standard, configure la propiedad móvil que ha creado en la IU de recopilación de datos. Consulte [Configuración de la aplicación de Adobe Experience Platform Launch en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Añada la configuración específica del canal a la configuración de la aplicación móvil.
Para obtener más información, consulte [Configuración de aplicaciones específicas del canal en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Si es necesario, puede eliminar la propiedad de etiquetas.
Para obtener más información, consulte [Eliminación de la aplicación](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Flujo de trabajo técnico Sincronizar aplicación móvil AEPSDK desde Launch {#aepsdk-workflow}

Después de crear y configurar la propiedad móvil en la interfaz de usuario de recopilación de datos, **[!UICONTROL Sync Mobile app AEPSDK from Launch]** El flujo de trabajo técnico de ahora sincronizará las propiedades móviles de etiqueta importadas en Adobe Campaign Standard.

De forma predeterminada, el flujo de trabajo técnico se inicia cada 15 minutos. Si es necesario, se puede reiniciar manualmente:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra el **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** flujo de trabajo.

   ![](assets/launch_10.png)

1. Haga clic en **[!UICONTROL Scheduler]** actividad.

1. Seleccione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

El flujo de trabajo ahora se reiniciará y sincronizará las propiedades móviles de etiquetas importadas en Adobe Campaign Standard.

## Configuración de la aplicación en Adobe Campaign {#set-up-campaign}

Para utilizar una propiedad móvil de etiqueta en Campaign, también debe configurar esta propiedad en Adobe Campaign. En Adobe Campaign, asegúrese de que el usuario de IMS forme parte de los Perfiles de producto de usuario y administrador estándar.

Debe esperar a que se ejecute el flujo de trabajo técnico y sincronizar la propiedad móvil de etiquetas con Adobe Campaign. A continuación, puede configurarlo en Adobe Campaign.

Para obtener más información sobre el flujo de trabajo técnico de la aplicación móvil de sincronización AEPSDK desde Launch, consulte esta sección [sección](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>De forma predeterminada, los administradores con la unidad organizativa configurada en TODO pueden editar la aplicación móvil.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleccione la aplicación móvil que creó en la interfaz de usuario de la recopilación de datos.
Su **[!UICONTROL Property Status]** debería ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >De forma predeterminada, para recuperar la lista de aplicaciones móviles creadas en la interfaz de usuario de recopilación de datos, Campaign Standard utiliza el valor definido en la opción NmsServer_URL para buscar propiedades coincidentes.
   >
   >En algunos casos, el punto final de Campaign para una aplicación móvil puede ser diferente del definido en NmsServer_URL. En ese caso, defina el punto final en `Launch_URL_Campaign` opción. Campaign utilizará el valor de esta opción para buscar propiedades coincidentes en la IU de recopilación de datos.

   ![](assets/launch_4.png)

1. Puede cambiar la unidad organizativa de la aplicación móvil en el **[!UICONTROL Access Authorization]** para limitar el acceso a esta aplicación móvil a unidades organizativas específicas. Para obtener más información, consulte esta página.

   En este caso, el administrador puede asignar unidades organizativas secundarias seleccionándolas en la lista desplegable.

   ![](assets/launch_12.png)

1. Para establecer la conexión entre Campaign y las etiquetas en Adobe Experience Platform, haga clic en **[!UICONTROL Save]**.

1. Compruebe que el estado de la aplicación móvil ha cambiado de **[!UICONTROL Ready to Configure]** hasta **[!UICONTROL Configured]**.

   Cuando la extensión de Campaign muestra que la clave se ha configurado correctamente, también puede verificar que la propiedad se haya configurado correctamente en Campaign.

   ![](assets/launch_5.png)

1. Para que esta configuración surta efecto, los cambios deben publicarse en la interfaz de usuario de la recopilación de datos.

   Para obtener más información, consulte [Publicar configuración](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Configuración de aplicaciones específicas del canal en Adobe Campaign {#channel-specific-config}

La aplicación móvil ya está lista para utilizarse en Campaign para notificaciones push o envíos en la aplicación. Ahora puede configurarlo aún más si es necesario para crear eventos que almacenarán en déclencheur los mensajes en la aplicación o cargarán certificados push.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleccione la aplicación móvil que creó y configuró en la interfaz de usuario de la recopilación de datos.

1. En el **[!UICONTROL Mobile application properties]** , puede empezar a añadir eventos disponibles en la aplicación móvil para los mensajes en la aplicación.

1. Para configurar los eventos, haga clic en **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Escriba un nombre y una descripción.

   ![](assets/launch_7.png)

1. Haga clic en **[!UICONTROL Add]**.

   El evento ahora está disponible en la pestaña Déclencheur al crear un mensaje en la aplicación. Para obtener más información, consulte [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. En el **[!UICONTROL Device-specific settings]** de un tablero de aplicaciones móviles, proporcione los detalles de la aplicación para cada dispositivo.

   * +++ Para iOS

     Introduzca los siguientes detalles de la aplicación:

      * **ID de aplicación (ID de paquete de iOS)**: Consulte [Documentación de Apple](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) para obtener más información sobre el ID de paquete.
      * **Archivo de certificado iOS (P8)**: arrastre y suelte la clave de autenticación .p8. Para obtener instrucciones sobre cómo generar el archivo de autenticación .p8, consulte su [cuenta de desarrollador de Apple](https://developer.apple.com/account/ios/authkey/create).
      * **ID de clave**: Consulte [Documentación de Apple](https://developer.apple.com/help/account/manage-keys/get-a-key-identifier/) para obtener más información sobre Key ID.
      * **Identificador de equipo de iOS**: Consulte [Documentación de Apple](https://developer.apple.com/help/account/manage-your-team/locate-your-team-id//) para obtener más información sobre el iOS Team ID.

        ![](assets/mobile_app_ios_config.png)
+++

   * +++ Para Android

     Introduzca los siguientes detalles de la aplicación:

      * **ID de aplicación (nombre del paquete de Android)**: Consulte [Documentación de Android](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores) para obtener más información sobre Package name.
      * **Archivo De Clave De Android (Json)**: arrastre y suelte el archivo de clave privada .json. Para obtener instrucciones sobre cómo generar el archivo de clave privada .json, consulte la [Documentación para desarrolladores de Firebase](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments).

        ![](assets/mobile_app_android_config.png)
+++

1. Una vez cargado el certificado, un mensaje le notifica que la carga se realizó correctamente y muestra la fecha de caducidad del certificado.

1. Haga clic en **[!UICONTROL Mobile application subscribers]** para ver una lista de suscriptores y otra información sobre estos suscriptores, por ejemplo, si se excluyeron de las notificaciones.

## Eliminación de la aplicación {#delete-app}

>[!CAUTION]
>
>No se puede deshacer la eliminación de su aplicación.

Para eliminar la aplicación, complete los pasos en [Eliminación de propiedades móviles](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui).

Una vez eliminada la aplicación, en Adobe Campaign, compruebe si el estado de la propiedad de la aplicación se ha actualizado correctamente a Eliminado en Launch.

Al hacer clic en la aplicación en Adobe Campaign, puede optar por eliminar completamente esta aplicación de Adobe Campaign haciendo clic en Eliminar de Campaign.

![](assets/launch_9.png)

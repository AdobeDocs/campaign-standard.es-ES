---
title: Configuración de una aplicación móvil
description: Descubra cómo configurar Adobe Campaign para enviar notificaciones push o mensajes en la aplicación mediante SDK V4 o el SDK de la plataforma de experiencia.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

---


# Configuración de una aplicación móvil{#configuring-a-mobile-application}

## Configuración de una aplicación móvil mediante los SDK de Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Los usuarios expertos deben realizar las implementaciones de notificaciones push y en la aplicación. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales.

Para enviar notificaciones push y mensajes en la aplicación con la aplicación del SDK de la plataforma de experiencia, se debe configurar una aplicación móvil en el Experience Platform Launch de la plataforma de experiencia de Adobe Experience Platform y configurarla en Adobe Campaign.

Para obtener más información sobre la función obsoleta SDK de Mobile versión 4, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Una vez configurada una aplicación móvil, puede recuperar los datos PII recopilados para crear o actualizar perfiles de la base de datos. Para obtener más información sobre esto, consulte esta sección: [Creación y actualización de información de perfil basada en datos](../../channels/using/updating-profile-with-mobile-app-data.md)de aplicaciones móviles.

Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK de la plataforma Adobe Experience, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para completar la configuración, complete los siguientes pasos:

1. En Adobe Campaign, asegúrese de tener acceso a lo siguiente:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**
   Si no es así, póngase en contacto con el equipo de su cuenta.

1. Compruebe que el usuario tiene los permisos necesarios en Adobe Campaign Standard y Experience Platform Launch.
   * En Adobe Campaign Standard, asegúrese de que el usuario de IMS forme parte de los Perfiles de usuario y administrador estándar del producto. Este paso permite al usuario iniciar sesión en Adobe Campaign Standard, navegar hasta la página de la aplicación móvil del SDK de la plataforma de experiencia y realizar la vista de las propiedades de la aplicación móvil que ha creado en Experience Platform Launch.

   * En Experience Platform Launch, asegúrese de que su usuario de IMS forme parte de un perfil de producto Experience Platform Launch.
Este paso permite al usuario iniciar sesión en Experience Platform Launch para crear y vista de las propiedades. Para obtener más información acerca de los perfiles de productos en Experience Platform Launch, consulte Crear el perfil de productos. En el perfil del producto, no debe haber permisos establecidos en la compañía o en las propiedades, pero el usuario debe poder iniciar sesión.
   Para completar tareas adicionales como instalar una extensión, publicar una aplicación, configurar entornos, etc., debe definir permisos en el perfil del producto.

1. En Experience Platform Launch, cree un **[!UICONTROL Mobile property]**. Para obtener más información, consulte [Configuración de una propiedad](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)móvil.

1. En Experience Platform Launch, haga clic en la **[!UICONTROL Extensions]** ficha, vaya a **[!UICONTROL Catalog]** y busque la **[!UICONTROL Adobe Campaign Standard]** extensión. Para obtener más información, consulte [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Para admitir casos de uso de ubicación en Campaign Standard, instale la **[!UICONTROL Places]** extensión y la **[!UICONTROL Places Monitor]** extensión.
   * Instale la extensión en el Experience Platform Launch **[!UICONTROL Places]** . Consulte [esta página](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Instale la extensión en el Experience Platform Launch **[!UICONTROL Places Monitor]** . Consulte [esta página](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. En Adobe Campaign Standard, configure la propiedad móvil que ha creado en Experience Platform Launch. Consulte [Configuración de la aplicación Adobe Experience Platform Launch en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Añada la configuración específica del canal a la configuración de la aplicación móvil.
Para obtener más información, consulte Configuración de aplicaciones específicas para [Canales en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Si es necesario, puede eliminar la propiedad Experience Platform Launch.
Para obtener más información, consulte [Eliminación de la aplicación](../../administration/using/configuring-a-mobile-application.md#delete-app)Experience Platform Launch.

## Sincronizar el AEPSDK de la aplicación móvil desde el flujo de trabajo técnico de Launch {#aepsdk-workflow}

>[!IMPORTANT]
>
>Esta función es una función beta en Adobe Campaign desde la versión 20.3. Deberá enviar un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para que el flujo de trabajo **[!UICONTROL sync Mobile app AEPSDK from Launch]** técnico esté habilitado en la instancia de Adobe Campaign.

Después de crear y configurar la propiedad móvil en Experience Platform Launch, el flujo de trabajo **[!UICONTROL Sync Mobile app AEPSDK from Launch]** técnico sincronizará las propiedades móviles de Adobe Launch importadas en Adobe Campaign Standard.

De forma predeterminada, el flujo de trabajo técnico se inicio cada 15 minutos. Si es necesario, se puede reiniciar manualmente:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra el **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** flujo de trabajo.

   ![](assets/launch_10.png)

1. Haga clic en la **[!UICONTROL Scheduler]** actividad.

1. Seleccione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

El flujo de trabajo se reiniciará y sincronizará con las propiedades móviles de Adobe Launch importadas en Adobe Campaign Standard.

## Configuración de la aplicación Adobe Experience Platform Launch en Adobe Campaign {#set-up-campaign}

Para utilizar una propiedad móvil Experience Platform Launch en Campaña, también debe configurar esta propiedad en Adobe Campaign. En Adobe Campaign, asegúrese de que el usuario de IMS forme parte de los Perfiles de usuario y administrador estándar del producto.

Para los usuarios con el indicador de la función Sincronizar AEPSDK de la aplicación móvil desde Iniciar flujo de trabajo técnico activado, deberá esperar a que el flujo de trabajo técnico se ejecute y sincronice la propiedad Iniciar móvil con Adobe Campaign. A continuación, puede configurarlo en Adobe Campaign.

Para obtener más información sobre el indicador de la función Sincronizar AEPSDK de la aplicación móvil desde Iniciar flujo de trabajo técnico, consulte esta [sección](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>De forma predeterminada, los administradores con la unidad organizativa configurada en ALL pueden editar la aplicación móvil.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleccione la aplicación móvil que ha creado en Experience Platform Launch.
Debe **[!UICONTROL Property Status]** ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >De forma predeterminada, para recuperar la lista de las aplicaciones móviles creadas en Adobe Launch, Campaign Standard utiliza el valor definido en la opción NmsServer_URL para buscar propiedades coincidentes.
En algunos casos, el extremo de Campaña de una aplicación móvil puede ser diferente del definido en NmsServer_URL. En ese caso, defina el punto final en la opción Launch_URL_Campaña. Campaña utilizará el valor de esta opción para buscar propiedades coincidentes en Adobe Launch.

   ![](assets/launch_4.png)

1. Puede cambiar la unidad organizativa de la aplicación móvil en la sección **[!UICONTROL Access Authorization]** para limitar el acceso a esta aplicación móvil a unidades de organización específicas. Para obtener más información, consulte esta página.

   Aquí, el administrador puede asignar unidades de suborganización seleccionándolas en la lista desplegable.

   ![](assets/launch_12.png)

1. Para establecer la conexión entre Campaña y Experience Platform Launch, haga clic en **[!UICONTROL Save]**.

1. Compruebe que el estado de la aplicación móvil ha cambiado de **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Cuando la extensión de Campaña Experience Platform Launch muestra que la clave se ha configurado correctamente, también puede comprobar que la propiedad se ha configurado correctamente en Campaña.

   ![](assets/launch_5.png)

1. Para que esta configuración surta efecto, los cambios deben publicarse en Experience Platform Launch.

   Para obtener más información, consulte Configuración [de](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)publicación.

## Configuración de aplicaciones específicas de Canal en Adobe Campaign {#channel-specific-config}

La aplicación móvil ya está lista para utilizarse en Campaña para notificaciones push o envíos en la aplicación. Ahora puede configurarlo aún más si es necesario para crear eventos que activen los mensajes en la aplicación o carguen certificados push.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleccione la aplicación móvil que ha creado y configurado en Experience Platform Launch.

1. En la **[!UICONTROL Mobile application properties]** ficha, puede añadir inicios de eventos disponibles en la aplicación móvil para los mensajes en la aplicación.

1. Para configurar sus eventos, haga clic en **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Escriba un nombre y una descripción.

   ![](assets/launch_7.png)

1. Haga clic **[!UICONTROL Add]**.

   El evento ya está disponible en la ficha Activadores al crear un mensaje en la aplicación. Para obtener más información, consulte [Preparación y envío de un mensaje](../../channels/using/preparing-and-sending-an-in-app-message.md)en la aplicación.

1. En la **[!UICONTROL Device-specific settings]** sección de un panel de aplicaciones móviles, proporcione los detalles de la aplicación, incluido el certificado para iOS y la clave del servidor para Android.

   Una vez cargado el certificado, un mensaje le notifica que la carga se realizó correctamente y muestra la fecha de caducidad del certificado.

   >[!NOTE]
   >
   >Después de agregar correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede agregar una plataforma APNS (producción o simulación de pruebas) a la aplicación MCPNS.

   ![](assets/launch_8.png)

1. Haga clic en la **[!UICONTROL Mobile application subscribers]** ficha para ver una lista de suscriptores y otra información sobre estos suscriptores, por ejemplo, si exclusión las notificaciones.

## Eliminación de la aplicación Adobe Experience Platform Launch {#delete-app}

No se puede deshacer la eliminación de la aplicación Experience Platform Launch.

>[!CAUTION]
>
>No se puede deshacer la eliminación de la aplicación Experience Platform Launch.

Para eliminar la aplicación Experience Platform Launch, complete los pasos en [Eliminación de propiedades](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)móviles.

Después de eliminar la aplicación, en Adobe Campaign, compruebe si el estado de la propiedad de la aplicación se ha actualizado correctamente a Eliminado en inicio.

Al hacer clic en la aplicación en Adobe Campaign, puede elegir eliminar completamente esta aplicación del Adobe Campaign haciendo clic en Eliminar de la Campaña.

    ![](assets/launch_9.png)

---
title: Configuración de una aplicación móvil
description: Descubra cómo configurar Adobe Campaign para que envíe notificaciones push o mensajes en la aplicación mediante SDK V4 o el SDK de la plataforma de experiencia.
page-status-flag: nunca activado
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: configurar-canales
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configuración de una aplicación móvil{#configuring-a-mobile-application}

Las notificaciones push o los mensajes en la aplicación se reciben en aplicaciones móviles que primero deben configurarse en Adobe Mobile Services según el canal que desee utilizar.

* Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign aprovechando los SDK de la plataforma Adobe Experience. Consulte [Uso del SDK](#using-adobe-experience-platform-sdk)de la plataforma Adobe Experience.

* Para enviar solo notificaciones Push, puede configurar la integración entre Adobe Campaign y Adobe Mobile Service con SDK V4. Consulte [Uso del SDK V4](#using-sdk-v4).

Una vez que las aplicaciones móviles se hayan configurado en Adobe Campaign aprovechando el SDK V4 de Experience Cloud Mobile o el SDK de la plataforma de experiencia, un administrador deberá configurarlas en el menú [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] .

>[!CAUTION]
>
>Los usuarios expertos deben realizar las implementaciones de notificaciones push y en la aplicación. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales.

Una vez configurada una aplicación móvil, puede recuperar los datos PII recopilados para crear o actualizar perfiles de la base de datos. Para obtener más información sobre esto, consulte esta sección: [Creación y actualización de información de perfil basada en datos](../../channels/using/updating-profile-with-mobile-app-data.md)de aplicaciones móviles.

## Uso del SDK de Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK de la plataforma Adobe Experience, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para enviar notificaciones push y mensajes In-App con la aplicación del SDK de la plataforma de experiencia, se debe configurar una aplicación móvil en el lanzamiento de la plataforma de experiencia de la plataforma de experiencia de Adobe Experience Platform y configurarla en Adobe Campaign. Para ver los pasos detallados para configurar la aplicación móvil con el SDK de la plataforma de experiencia, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga los pasos a continuación para iniciar la configuración:

1. Asegúrese de tener acceso a los **[!UICONTROL Mobile]** canales: Notificación push y mensaje en la aplicación en Adobe Campaign. Si no es así, póngase en contacto con el equipo de su cuenta.

   ![](assets/launch_1.png)

1. Cree la aplicación móvil en Inicio de plataforma de experiencia creando una propiedad de tipo Móvil. Para obtener más información, consulte la documentación de [Inicio](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) de plataforma de experiencia.
1. Instale la extensión de la **[!UICONTROL Adobe Campaign Standard]** aplicación móvil en Inicio de plataforma de experiencia:

   Para obtener más información sobre las extensiones, consulte la documentación de [lanzamiento](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) de la plataforma de experiencias.

1. Configure las reglas para la aplicación en Adobe Launch; consulte [Configuración de la aplicación en Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure la aplicación Adobe Launch en Adobe Campaign Standard; consulte [Configuración de la aplicación Adobe Launch en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Agregue una configuración específica de canal a la configuración de aplicaciones móviles; consulte Configuración de aplicaciones específicas de [canal en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Uso del SDK V4 {#using-sdk-v4}

Los SDK V4 y los SDK de la plataforma Adobe Experience son compatibles con la notificación push, a diferencia de In-App. Para ver los pasos detallados para utilizar las notificaciones push con la aplicación móvil, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Un administrador de la interfaz de Adobe Campaign debe configurar las aplicaciones móviles que reciben notificaciones push. Al configurar tanto Adobe Campaign como Adobe Mobile Services, podrá utilizar los datos de su aplicación móvil para sus campañas.

Para poder enviar notificaciones push, debe:

1. Asegúrese de tener acceso al canal en Adobe Campaign **[!UICONTROL Mobile app]** .
1. Configure la aplicación móvil en:

   * [Espacio de trabajo de Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado de la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Experience Cloud Mobile en la aplicación móvil.

1. Defina los datos que desea recopilar de los suscriptores de la aplicación. Los suscriptores de la aplicación móvil que tienen un perfil en la base de datos de Adobe Campaign se concilian según los criterios definidos.

   Para obtener más información, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Asegúrese de que la configuración se ha completado correctamente iniciando la aplicación móvil en el dispositivo e iniciando sesión. Asegúrese de seleccionar recibir notificaciones.
1. A continuación, en el menú avanzado de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleccione la aplicación móvil en la lista para mostrar sus propiedades. La información de suscripción se muestra en la lista de suscriptores.

   ![](assets/push_notif_mobile_app.png)

1. Para comprobar las aplicaciones móviles a las que se ha suscrito un perfil, en el **[!UICONTROL Profiles & Audiences > Profiles]** menú, seleccione un perfil y haga clic en el **[!UICONTROL Edit profile properties]** botón de la derecha. Las aplicaciones móviles se muestran en la **[!UICONTROL Mobile App Subscriptions]** ficha.

   ![](assets/push_notif_subscriptions.png)
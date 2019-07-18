---
title: Configuración de una aplicación móvil
seo-title: Configuración de una aplicación móvil
description: Configuración de una aplicación móvil
seo-description: Descubra cómo configurar Adobe Campaign para enviar notificaciones push o mensajes en la aplicación mediante SDK V 4 o SDK de plataforma de Experience Platform.
page-status-flag: no activado nunca
uuid: 63 e 1476 a -7875-4 f 48-ba 9 e -97 f 1 a 0007 e 42
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: configurar canales
discoiquuid: 2 a 14500 f -5 ede -4131-8 b 1 a-b 7 fd 65 b 7 e 3 aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d148014d1b90712e78b8af17d7ddee2659329ed

---


# Configuring a mobile application{#configuring-a-mobile-application}

Las notificaciones push o los mensajes en la aplicación se reciben en aplicaciones móviles que primero deben configurarse en Adobe Mobile Services según el canal que desee utilizar.

* Para enviar mensajes en la aplicación y notificaciones push, es necesario configurar las aplicaciones móviles en Adobe Campaign aprovechando los SDK de la Plataforma de Adobe Experience. See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Para enviar únicamente notificaciones Push, puede configurar la integración entre Adobe Campaign y Adobe Mobile Services mediante SDK V 4. See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>Las notificaciones Push y las implementaciones desde la propia aplicación deben realizarlas los usuarios expertos. Si necesita recibir ayuda, póngase en contacto con su ejecutivo de cuentas de Adobe o con el socio de servicios profesionales.

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

Para enviar notificaciones push y mensajes en la aplicación con la aplicación SDK de Experience Platform, se debe configurar una aplicación móvil en Adobe Experience Platform Experience Platform Experience Platform Launch y configurada en Adobe Campaign. For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga los pasos a continuación para iniciar la configuración:

1. Make sure you can access the **[!UICONTROL Mobile]** channels: Push notification and In-App message in Adobe Campaign. Si no es así, póngase en contacto con el equipo de su cuenta.

   ![](assets/launch_1.png)

1. Cree la aplicación móvil en Launch Platform Launch creando una propiedad de tipo Móvil. For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign (Beta)]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard-beta) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign) .

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

La notificación Push es compatible con SDK V 4 y SDK de plataforma de Adobe Experience, a diferencia de en la aplicación. For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Las aplicaciones móviles que reciban notificaciones push deben ser configuradas por un administrador en la interfaz de Adobe Campaign. Al configurar Adobe Campaign y Adobe Mobile Services, podrá utilizar los datos de su aplicación móvil para sus campañas.

Para poder enviar notificaciones push, debe:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configure la aplicación móvil en:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado desde la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Mobile Cloud Mobile en su aplicación móvil.

1. Defina los datos que desee recopilar de los suscriptores de la aplicación. Los suscriptores de la aplicación móvil que tienen un perfil en la base de datos de Adobe Campaign se reconcilian según los criterios definidos.

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication) .

1. Asegúrese de que la configuración se haya completado correctamente al iniciar la aplicación móvil en el dispositivo e iniciar sesión. Asegúrese de recibir notificaciones.
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleccione la aplicación móvil de la lista para mostrar sus propiedades. La información de suscripción se muestra bajo la lista de suscriptores.

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)

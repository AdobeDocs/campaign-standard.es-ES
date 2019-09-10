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
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# Configuración de una aplicación móvil{#configuring-a-mobile-application}

Las notificaciones push o los mensajes en la aplicación se reciben en aplicaciones móviles que primero deben configurarse en Adobe Mobile Services según el canal que desee utilizar.

* Para enviar mensajes en la aplicación y notificaciones push, es necesario configurar las aplicaciones móviles en Adobe Campaign aprovechando los SDK de la Plataforma de Adobe Experience. Consulte [Uso del SDK de Adobe Experience Platform](#using-adobe-experience-platform-sdk).

* Para enviar únicamente notificaciones Push, puede configurar la integración entre Adobe Campaign y Adobe Mobile Services mediante SDK V 4. Consulte [Uso de SDK V 4](#using-sdk-v4).

Una vez configuradas las aplicaciones móviles en Adobe Campaign, aprovechando el SDK móvil de Experience Cloud V 4 o Experience Platform SDK, es necesario configurarlas por un administrador en el menú [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] .

>[!CAUTION]
>
>Las notificaciones Push y las implementaciones desde la propia aplicación deben realizarlas los usuarios expertos. Si necesita recibir ayuda, póngase en contacto con su ejecutivo de cuentas de Adobe o con el socio de servicios profesionales.

Una vez configurada la aplicación móvil, puede recuperar los datos PII que ha recopilado para crear o actualizar perfiles desde la base de datos. Para obtener más información, consulte esta sección: [Creación y actualización de información de perfil en base a datos de aplicaciones móviles](../../channels/using/updating-profile-with-mobile-app-data.md).

## Uso del SDK de Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK de la Plataforma de Adobe Experience, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para enviar notificaciones push y mensajes en la aplicación con la aplicación SDK de Experience Platform, se debe configurar una aplicación móvil en Adobe Experience Platform Experience Platform Experience Platform Launch y configurada en Adobe Campaign. Para obtener los pasos detallados para configurar la aplicación móvil mediante el SDK de plataforma de Experience Platform, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga los pasos a continuación para iniciar la configuración:

1. Asegúrese de acceder a **[!UICONTROL Mobile]** los canales: Notificación push y mensaje en la aplicación en Adobe Campaign. Si no es así, póngase en contacto con el equipo de su cuenta.

   ![](assets/launch_1.png)

1. Cree la aplicación móvil en Launch Platform Launch creando una propiedad de tipo Móvil. Para obtener más información, consulte [la documentación de Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) Platform Launch.
1. Instale **[!UICONTROL Adobe Campaign Standard]** la extensión para su aplicación móvil en Launch Platform Launch:

   Para obtener más información sobre las extensiones, consulte [la documentación de Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) Platform Launch.

1. Configurar reglas para la aplicación en Adobe Launch, consulte [Configuración de la aplicación en Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure su aplicación Adobe Launch en Adobe Campaign Standard, consulte [Configuración de la aplicación Adobe Launch en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Agregue configuración específica de canal a su configuración de aplicación móvil, consulte [Configuración de aplicación específica de canal en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Uso de SDK V 4 {#using-sdk-v4}

La notificación Push es compatible con SDK V 4 y SDK de plataforma de Adobe Experience, a diferencia de en la aplicación. Para obtener los pasos detallados para utilizar notificaciones push con su aplicación móvil, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Las aplicaciones móviles que reciban notificaciones push deben ser configuradas por un administrador en la interfaz de Adobe Campaign. Al configurar Adobe Campaign y Adobe Mobile Services, podrá utilizar los datos de su aplicación móvil para sus campañas.

Para poder enviar notificaciones push, debe:

1. Asegúrese de acceder al **[!UICONTROL Mobile app]** canal en Adobe Campaign.
1. Configure la aplicación móvil en:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Realice la configuración específica de la aplicación móvil:

   * Empaquete el archivo de configuración descargado desde la interfaz de Adobe Mobile Services con la aplicación móvil.
   * Integre el SDK de Mobile Cloud Mobile en su aplicación móvil.

1. Defina los datos que desee recopilar de los suscriptores de la aplicación. Los suscriptores de la aplicación móvil que tienen un perfil en la base de datos de Adobe Campaign se reconcilian según los criterios definidos.

   Para obtener más información, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Asegúrese de que la configuración se haya completado correctamente al iniciar la aplicación móvil en el dispositivo e iniciar sesión. Asegúrese de recibir notificaciones.
1. A continuación, en el menú avanzado de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleccione la aplicación móvil de la lista para mostrar sus propiedades. La información de suscripción se muestra bajo la lista de suscriptores.

   ![](assets/push_notif_mobile_app.png)

1. Para comprobar las aplicaciones móviles a las que se ha suscrito un perfil, en **[!UICONTROL Profiles & Audiences > Profiles]** el menú, seleccione un perfil y haga clic en **[!UICONTROL Edit profile properties]** el botón de la derecha. Las aplicaciones móviles se enumeran en **[!UICONTROL Mobile App Subscriptions]** la ficha.

   ![](assets/push_notif_subscriptions.png)
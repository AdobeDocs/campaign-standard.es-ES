---
title: Configuración de una aplicación móvil
description: Descubra cómo configurar Adobe Campaign para que envíe notificaciones push o mensajes en la aplicación mediante el SDK V4 o el SDK de la plataforma de experiencia.
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
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Configuración de una aplicación móvil{#configuring-a-mobile-application}

Las notificaciones push o los mensajes en la aplicación se reciben en aplicaciones móviles que primero deben configurarse en Adobe Campaign Standard en función del canal que desee utilizar.

Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign aprovechando los SDK de la plataforma Adobe Experience. Consulte [Uso del SDK](#using-adobe-experience-platform-sdk)de la plataforma Adobe Experience.

Una vez que las aplicaciones móviles se hayan configurado en Adobe Campaign aprovechando el SDK V4 de Experience Cloud Mobile o el SDK de la plataforma de experiencia, un administrador deberá configurarlas en el menú [!UICONTROL Administration] > [!UICONTROL Channels] > [!UICONTROL Mobile app] .

>[!IMPORTANT]
>
>Los usuarios expertos deben realizar las implementaciones de notificaciones push y en la aplicación. Si necesita asistencia, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales.

Una vez configurada una aplicación móvil, puede recuperar los datos PII recopilados para crear o actualizar perfiles de la base de datos. Para obtener más información sobre esto, consulte esta sección: [Creación y actualización de información de perfil basada en datos](../../channels/using/updating-profile-with-mobile-app-data.md)de aplicaciones móviles.

Para obtener instrucciones generales sobre envíos con dispositivos móviles en Adobe Campaign Standard, consulte esta [página](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Uso del SDK de Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Para obtener más información sobre los distintos casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK de la plataforma Adobe Experience, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para enviar notificaciones push y mensajes In-App con la aplicación del SDK de la plataforma de experiencia, se debe configurar una aplicación móvil en el lanzamiento de la plataforma de experiencia de la plataforma de experiencia de Adobe Experience Platform y configurarla en Adobe Campaign. Para ver los pasos detallados para configurar la aplicación móvil con el SDK de la plataforma de experiencia, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga los pasos a continuación para iniciar la configuración:

1. Asegúrese de tener acceso a los **[!UICONTROL Mobile]**canales: Notificación push y mensaje en la aplicación en Adobe Campaign. Si no es así, póngase en contacto con el equipo de su cuenta.

   ![](assets/launch_1.png)

1. Cree la aplicación móvil en Inicio de plataforma de experiencia creando una propiedad de tipo Móvil. Para obtener más información, consulte la documentación de [Inicio](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) de plataforma de experiencia.
1. Instale la extensión de la **[!UICONTROL Adobe Campaign Standard]**aplicación móvil en Inicio de plataforma de experiencia:

   Para obtener más información sobre las extensiones, consulte la documentación de [lanzamiento](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) de la plataforma de experiencias.

1. Configure las reglas para la aplicación en Adobe Launch; consulte [Configuración de la aplicación en Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure la aplicación Adobe Launch en Adobe Campaign Standard; consulte [Configuración de la aplicación Adobe Launch en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Agregue la configuración específica del canal a la configuración de la aplicación móvil; consulte Configuración de la aplicación específica del [canal en Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

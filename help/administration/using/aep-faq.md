---
solution: Campaign Standard
product: campaign
title: Preguntas más frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
description: Preguntas más frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---


# Preguntas más frecuentes sobre la integración del SDK de Experience Platform {#aep-faq}

Para enviar notificaciones push y mensajes en la aplicación con la aplicación SDK de Experience Platform, se debe configurar una aplicación móvil en el SDK de Adobe Experience Platform y en Adobe Campaign.

La sección siguiente lista preguntas comunes sobre esta sincronización.

Para obtener más información sobre la inserción o en la aplicación, consulte las siguientes preguntas más frecuentes:

* [Preguntas más frecuentes sobre notificaciones Push](../../channels/using/about-push-notifications.md#push-faq)
* [Preguntas más frecuentes en la aplicación](../../channels/using/about-in-app-messaging.md#in-app-faq)
* [Preguntas más frecuentes sobre el flujo de trabajo técnico de sincronización con Launch](../../administration/using/syncwithlaunch-faq.md)

## Recursos útiles antes de iniciar {#resource-mobile-property}

Consulte los siguientes recursos para obtener más información sobre el SDK de Adobe Experience Platform y la integración de Campaign Standard:

* Iniciar/Móvil [Vídeo de información general](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [Guía de consejos y trucos](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## ¿Está disponible la integración del SDK de Adobe Experience Platform tanto para Adobe Campaign Standard como para Adobe Campaign Classic? {#aep-validity}

Sí, la integración [!DNL Adobe Experience Platform SDK] está disponible tanto para Adobe Campaign Standard como para Adobe Campaign Classic. Debe instalar el **[!UICONTROL Extension]** correspondiente mediante [!DNL Adobe Launch] para habilitar la integración.

Para obtener más información, consulte [esta página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

## ¿Qué capacidades facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign? {#aep-capabilities}

Consulte la tabla siguiente para obtener más información sobre estas funciones.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] incluye eventos de lugares como déclencheur para mensajes en la aplicación (N/D para notificaciones push), lo que enriquece los perfiles con  [!DNL Places] datos y la compatibilidad con las notificaciones locales. Consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md) para obtener más información. <br>[!DNL Places] la integración limitada incluye perfiles enriquecidos con  [!DNL Places] datos.

## ¿Qué caso de uso facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign Standard? {#aep-use-cases}

Se admiten los siguientes casos de uso:

* Adquirir una **[!UICONTROL Mobile Profile]** en Campaña (identificada por ECID en **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** ficha)
* Enriquecer un **[!UICONTROL Mobile Profile]** en Adobe Campaign (requiere **[!UICONTROL Custom resource Extension]** de la tabla appSubscriberRcp)
* Adquirir un distintivo push para enviar mensajes push (requiere la opción del usuario de recibir mensajes push)
* Envío de mensajes push y en la aplicación
* Rastree la interacción del usuario con los mensajes push y en la aplicación y proporcione informes al respecto

## ¿Qué tengo que hacer para adquirir un Perfil móvil en Campaña? {#mobile-profile-campaign}

Para ello, siga los pasos a continuación:

1. Configure un **[!UICONTROL Mobile property]** en [!DNL Launch].
1. Instale la extensión de Adobe Campaign Standard. Tenga en cuenta que la extensión de Adobe Campaign Standard también requiere **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** y **[!UICONTROL Lifecycle]** extensiones que se instalan de forma predeterminada en [!DNL Launch].
   * Los usuarios deben configurar el tiempo de espera de sesión en la extensión **[!UICONTROL Mobile Core]**, lo que afecta a la frecuencia de los eventos del ciclo vital.
   * Una vez configurada la extensión, los usuarios deben agregar las dependencias adecuadas en la aplicación móvil mediante Cocoapods para iOS y Gradle para Android. Siga las indicaciones [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Siempre tome las versiones más recientes de las bibliotecas.
   * En Aplicación móvil, registre **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** y **[!UICONTROL Signal]** extensiones. Siga las indicaciones [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Una vez registradas las extensiones, inicio ACPCore. Para Android, asegúrese de setApplication onCreate(). Siga las instrucciones exactas que se proporcionan en Instrucciones de instalación móvil para su propiedad móvil en Launch.
   * También se necesitarán las siguientes API de SDK. Implemente las API de Inicio y pausa del ciclo vital tal como se describe [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) para Android y aquí para iOS.
1. Configure un **[!UICONTROL Mobile Property]** en Adobe Campaign Standard. Siga el procedimiento [aquí](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## ¿Qué tengo que hacer para enriquecer un Perfil móvil en Campaña? {#enrich-mobile-profile}

Debe configurar un postback CollectPII (consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) e implementar la API CollectPII desde el SDK (consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## ¿Con qué frecuencia debe activarse una llamada a CollectPII? {#collect-pii}

El objetivo de la llamada CollectPII es enriquecer el Perfil móvil en Campaña. Debe activarse cada vez que haya nueva información significativa que los clientes deseen agregar al perfil en función de sus casos de uso y necesidades comerciales.

## ¿Se pueden activar llamadas CollectPII en respuesta a varios eventos de déclencheur? {#collect-pii-calls}

Sí. Según las necesidades de su empresa, puede activar llamadas de CollectPII en respuesta al inicio de sesión de usuario en la aplicación, o bien comprar algo o evento de ciclo vital o usuario que entra en una geofence, etc. En resumen, una interacción del usuario con la aplicación que genera la información que desea utilizar para el enriquecimiento de Perfil.

## ¿Puedo simplemente activar llamadas CollectPII en respuesta a todos los eventos móviles? {#collect-pii-events}

La frecuencia y el diseño de las llamadas CollectPII deben estar dictados por necesidades comerciales y no deben activarse ciegamente ya que crea una carga extra en la base de datos.

### Cuando intento acceder a las aplicaciones de Adobe Experience Platform en Campaña o en Launch, a veces aparece un error de propiedad no disponible. {#aep-error}

Se trata de un problema conocido que se produce debido a la caducidad del token. Debe intentar iniciar sesión y cerrar sesión.

## ¿Cuáles serían algunas recomendaciones de recursos útiles para obtener más información sobre el SDK de Adobe Experience Platform (anteriormente conocido como SDK V5)?{#resource-aep}

Consulte los siguientes recursos:

* SDK de Experience Platform [documentación](https://aep-sdks.gitbook.io/docs/)
* Introducción al SDK de Launch y Experience Platform [documentación](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Actualización al SDK de Experience Platform [documentación](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK [documentación](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Se ha producido el error &quot;No tiene acceso de escritura en envío&quot; al crear un envío de notificación push. {#write-access-error}

Debe comprobar lo siguiente:

* La aplicación móvil debe asignarse a la unidad organizativa del usuario que necesita crear y enviar envíos push. El usuario de una unidad organizativa secundaria no puede crear un envío push mediante una aplicación asignada a la unidad organizativa principal.

* La campaña o el programa dentro del cual se crea el envío push deben asignarse a la unidad organizativa del usuario que necesita crear y enviar envíos push. El usuario de la unidad organizativa secundaria no puede crear un envío push en una campaña o programa asignado a la unidad organizativa principal.
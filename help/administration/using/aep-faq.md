---
title: Preguntas frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
description: Preguntas frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---

# Preguntas más frecuentes sobre la integración del SDK de Experience Platform {#aep-faq}

Para enviar notificaciones push y mensajes en la aplicación con la aplicación SDK de Experience Platform, se debe configurar una aplicación móvil en el SDK de Adobe Experience Platform y configurarla en Adobe Campaign.

La sección siguiente enumera preguntas comunes sobre esta sincronización.

Para obtener más información sobre push o en la aplicación, consulte las siguientes preguntas frecuentes:

* [Preguntas frecuentes sobre notificaciones push](../../channels/using/about-push-notifications.md#push-faq)
* [Preguntas frecuentes en la aplicación](../../channels/using/in-app-faq.md)
* [Preguntas frecuentes sobre el flujo de trabajo técnico Sincronización con Launch](../../administration/using/syncwithlaunch-faq.md)

## Recursos útiles antes de empezar {#resource-mobile-property}

Consulte los siguientes recursos para obtener más información sobre la integración del SDK y el Campaign Standard de Adobe Experience Platform:

* Vídeo de información general [de Launch/Mobile](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Guía de consejos y trucos [de Launch/Mobile](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## ¿Está disponible la integración del SDK de Adobe Experience Platform tanto para Adobe Campaign Standard como para Adobe Campaign Classic? {#aep-validity}

Sí, la integración [!DNL Adobe Experience Platform SDK] está disponible tanto para Adobe Campaign Standard como para Adobe Campaign Classic. Debe instalar el **[!UICONTROL Extension]** correspondiente a través de [!DNL Adobe Launch] para habilitar la integración.

Para obtener más información, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

## ¿Qué capacidades facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign? {#aep-capabilities}

Consulte la siguiente tabla para obtener más información sobre estas funciones.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] La integración incluye eventos places como déclencheur para los mensajes en la aplicación (N/D para notificaciones push), lo que enriquece los perfiles con  [!DNL Places] datos y la compatibilidad con notificaciones locales. Consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md) para obtener más información. <br>[!DNL Places] la integración limitada incluye el enriquecimiento de perfiles con  [!DNL Places] datos.

## ¿Qué caso de uso facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign Standard? {#aep-use-cases}

Se admiten los siguientes casos de uso:

* Adquirir un **[!UICONTROL Mobile Profile]** en Campaign (identificado por ECID en la pestaña **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** )
* Enriquecimiento de **[!UICONTROL Mobile Profile]** en Adobe Campaign (requiere **[!UICONTROL Custom resource Extension]** de la tabla appSubscriberRcp)
* Adquirir un token push para enviar mensajes push (se requiere la inclusión del usuario para recibir mensajes push)
* Envío de mensajes push y en la aplicación
* Rastree la interacción del usuario con los mensajes push y en la aplicación y proporcione informes sobre ello

## ¿Qué tengo que hacer para adquirir un perfil móvil en Campaign? {#mobile-profile-campaign}

Para ello, siga los pasos a continuación:

1. Configure un **[!UICONTROL Mobile property]** en [!DNL Launch].
1. Instale la extensión de Adobe Campaign Standard. Tenga en cuenta que la extensión de Adobe Campaign Standard también requiere **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** y **[!UICONTROL Lifecycle]** extensiones que se instalan de forma predeterminada en [!DNL Launch].
   * Los usuarios deben configurar el tiempo de espera de sesión en la extensión **[!UICONTROL Mobile Core]** , lo que afecta a la frecuencia de los eventos de ciclo vital.
   * Una vez configurada la extensión, los usuarios deben agregar las dependencias adecuadas en la aplicación móvil mediante Cocoapods para iOS y Gradle para Android. Siga las indicaciones [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Utilice siempre las versiones más recientes de las bibliotecas.
   * En Aplicación móvil, registre las extensiones **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** y **[!UICONTROL Signal]**. Siga las indicaciones [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Una vez registradas las extensiones, inicie ACPCore. Para Android, asegúrese de setApplication onCreate(). Siga las instrucciones exactas que se proporcionan en Instrucciones de instalación de Mobile para su propiedad móvil en Launch.
   * También se necesitarán las siguientes API de SDK. Implemente las API de inicio y pausa del ciclo vital tal como se describe [aquí](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) para Android y aquí para iOS.
1. Configure un **[!UICONTROL Mobile Property]** en Adobe Campaign Standard. Siga el procedimiento [aquí](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## ¿Qué tengo que hacer para enriquecer un perfil móvil en Campaign? {#enrich-mobile-profile}

Debe configurar un postback de CollectPII (consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) e implementar la API de CollectPII desde el SDK (consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## ¿Con qué frecuencia se debe activar una llamada a CollectPII? {#collect-pii}

El objetivo de la llamada de CollectPII es enriquecer el perfil móvil en Campaign. Debe activarse siempre que haya nueva información significativa que los clientes deseen añadir al perfil según sus casos de uso y necesidades comerciales.

## ¿Se pueden activar llamadas de CollectPII como respuesta a varios eventos de déclencheur? {#collect-pii-calls}

Sí. Según sus necesidades comerciales, puede activar llamadas de CollectPII en respuesta al inicio de sesión del usuario en la aplicación, o comprar algo o evento de ciclo de vida o al usuario que entra en una geovalla, etc. En resumen, una interacción del usuario con la aplicación que genera la información que desea utilizar para el enriquecimiento de perfiles.

## ¿Puedo activar llamadas de CollectPII como respuesta a todos los eventos de Mobile? {#collect-pii-events}

La frecuencia y el diseño de las llamadas de CollectPII deben estar dictados por las necesidades del negocio y no deben activarse ciegamente ya que crea carga extra en la base de datos.

### Cuando intento acceder a aplicaciones de Adobe Experience Platform en Campaign o Launch, a veces obtengo un error de propiedad no disponible. {#aep-error}

Este es un problema conocido y se produce debido a la caducidad del token. Debe intentar iniciar sesión y salir.

## ¿Cuáles serían algunas recomendaciones de recursos útiles para obtener más información sobre el SDK de Adobe Experience Platform (anteriormente conocido como SDK V5)?{#resource-aep}

Consulte los siguientes recursos:

* SDK de Experience Platform [documentación](https://aep-sdks.gitbook.io/docs/)
* Introducción al SDK [documentación](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) de Launch y Experience Platform
* Actualización al SDK de Experience Platform [documentation](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* SDK de Experience Platform de Github [documentación](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Aparece el error &quot;No tiene acceso de escritura en la entrega&quot; al crear una entrega de notificación push. {#write-access-error}

Debe comprobar lo siguiente:

* La aplicación móvil debe asignarse a la unidad organizativa del usuario que necesita crear y enviar envíos push. El usuario de una unidad organizativa secundaria no puede crear una entrega push mediante una aplicación asignada a la unidad organizativa principal.

* La campaña o el programa en el que se crea la entrega push deben asignarse a la unidad organizativa del usuario que necesita crear y enviar entregas push. El usuario de la unidad organizativa secundaria no puede crear una entrega push en una campaña o programa asignado a la unidad organizativa principal.

---
title: Preguntas frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
description: Preguntas frecuentes sobre la integración de Adobe Experience Platform SDK y Adobe Campaign
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 2%

---

# Preguntas frecuentes sobre la integración de Experience Platform SDK {#aep-faq}

Para enviar notificaciones push y mensajes en la aplicación con la aplicación de SDK de Experience Platform, se debe configurar una aplicación móvil en el SDK de Adobe Experience Platform y en Adobe Campaign.

La sección siguiente enumera preguntas comunes sobre esta sincronización.

Para obtener más información sobre notificaciones push o en la aplicación, consulte las siguientes preguntas frecuentes:

* [Preguntas frecuentes sobre notificaciones push](../../channels/using/about-push-notifications.md#push-faq)
* [Preguntas frecuentes en la aplicación](../../channels/using/in-app-faq.md)
* [Preguntas frecuentes sobre la sincronización de etiquetas en Adobe Experience Platform](../../administration/using/syncwithlaunch-faq.md)

## Recursos útiles antes de empezar {#resource-mobile-property}

Consulte los recursos siguientes para obtener más información sobre la integración del SDK y el Campaign Standard de Adobe Experience Platform:

* [Vídeo de información general](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video) de Launch/Mobile
* [Guía de sugerencias y trucos para Launch/Mobile](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## ¿La integración del SDK de Adobe Experience Platform está disponible tanto para Adobe Campaign Standard como para Adobe Campaign Classic? {#aep-validity}

Sí, la integración de [!DNL Adobe Experience Platform SDK] está disponible tanto para Adobe Campaign Standard como para Adobe Campaign Classic. Debe instalar el(la) **[!UICONTROL Extension]** correspondiente(a) a través de [!DNL Data Collection UI] para habilitar la integración.

Para obtener más información, consulte esta [página](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

## ¿Qué capacidades facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign? {#aep-capabilities}

Consulte la tabla siguiente para obtener más información sobre estas funciones.

![](assets/faq.png)

>[!NOTE]
>
>La integración de [!DNL Places] incluye eventos de places como déclencheur para mensajes en la aplicación (N/D para notificaciones push), lo que enriquece los perfiles con datos de [!DNL Places] y compatibilidad con notificaciones locales. Consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md) para obtener más información. La integración limitada de <br>[!DNL Places] incluye perfiles ampliables con datos de [!DNL Places].

## ¿Qué caso de uso facilita la integración del SDK de Adobe Experience Platform en Adobe Campaign Standard? {#aep-use-cases}

Se admiten los siguientes casos de uso:

* Adquirir un(a) **[!UICONTROL Mobile Profile]** en Campaign (identificado(a) por ECID en **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** tab)
* Enriquecimiento de **[!UICONTROL Mobile Profile]** en Adobe Campaign (requiere **[!UICONTROL Custom resource Extension]** de la tabla appSubscriberRcp)
* Adquirir un token push para enviar mensajes push (requiere la inclusión del usuario para recibir mensajes push)
* Envío de mensajes push y en la aplicación
* Rastree la interacción del usuario con mensajes push y en la aplicación y proporcione informes al respecto

## ¿Qué tengo que hacer para adquirir un perfil móvil en Campaign? {#mobile-profile-campaign}

Para ello, siga los pasos a continuación:

1. Configurar un **[!UICONTROL Mobile property]** en [!DNL Launch].
1. Instale la extensión de Adobe Campaign Standard. Tenga en cuenta que la extensión de Adobe Campaign Standard también requiere las extensiones **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** y **[!UICONTROL Lifecycle]** que están instaladas de forma predeterminada en [!DNL Launch].
   * Los usuarios deben configurar el tiempo de espera de sesión en la extensión **[!UICONTROL Mobile Core]**, lo cual afecta la frecuencia de los eventos del ciclo vital.
   * Una vez configurada la extensión, los usuarios deben agregar las dependencias adecuadas en la aplicación móvil mediante Cocoapods para iOS y Gradle para Android. Siga las instrucciones [aquí](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).
   * Utilice siempre las versiones más recientes de las bibliotecas.
   * En la aplicación móvil, registre las extensiones **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** y **[!UICONTROL Signal]**. Siga las instrucciones [aquí](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core).
   * Una vez registradas las extensiones, inicie ACPCore. Para Android, asegúrese de setApplication onCreate(). Siga exactamente las instrucciones proporcionadas en Instrucciones de instalación de Mobile para su propiedad móvil en Launch.
   * También se requerirán las siguientes API de SDK. Implemente las API de inicio y pausa del ciclo vital como se describe [aquí](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android) para Android y aquí para iOS.
1. Configurar un **[!UICONTROL Mobile Property]** en Adobe Campaign Standard. Siga el procedimiento [aquí](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## ¿Qué tengo que hacer para enriquecer un perfil móvil en Campaign? {#enrich-mobile-profile}

Debe configurar un postback de CollectPII (consulte esta [página](../../administration/using/configuring-rules-launch.md#pii-postback)) e implementar la API de CollectPII desde el SDK (consulte esta [página](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference)).

## ¿Con qué frecuencia se debe activar una llamada a CollectPII? {#collect-pii}

El objetivo de la llamada CollectPII es enriquecer el perfil móvil en Campaign. Debe activarse siempre que haya información significativa nueva que los clientes deseen añadir al perfil en función de sus casos de uso y necesidades comerciales.

## ¿Pueden activarse las llamadas a CollectPII en respuesta a múltiples eventos de déclencheur? {#collect-pii-calls}

Sí. Según las necesidades de su empresa, puede activar las llamadas a CollectPII en respuesta al inicio de sesión del usuario en la aplicación o al comprar algo, un evento del ciclo vital, o al entrar en un geoperímetro, etc. En resumen, una interacción de un usuario con la aplicación que genera información que desearía utilizar para el enriquecimiento del perfil.

## ¿Puedo activar llamadas a CollectPII en respuesta a todos los eventos móviles? {#collect-pii-events}

La frecuencia y el diseño de las llamadas a CollectPII deben estar dictados por las necesidades empresariales y no deben activarse a ciegas, ya que crean una carga adicional en la base de datos.

### Cuando intento acceder a aplicaciones de Adobe Experience Platform en Campaign o Launch, a veces recibo un error de propiedad no disponible. {#aep-error}

Se trata de un problema conocido que ocurre debido a la caducidad del token. Debe intentar cerrar la sesión y volver a iniciarla.

## ¿Cuáles serían algunas recomendaciones de recursos útiles para obtener más información sobre el SDK de Adobe Experience Platform (anteriormente conocido como SDK V5)?{#resource-aep}

Consulte los siguientes recursos:

* [documentación](https://developer.adobe.com/client-sdks/documentation/) del SDK de Experience Platform
* Introducción al SDK de Launch &amp; Experience Platform [documentation](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* Actualizando al SDK de Experience Platform [documentation](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/)
* [documentación](https://github.com/Adobe-Marketing-Cloud/acp-sdks/) del SDK de Experience Platform de Github

## Aparece el error &quot;No tiene acceso de escritura en la entrega&quot; al crear una entrega de notificación push. {#write-access-error}

Debe comprobar lo siguiente:

* La aplicación móvil debe asignarse a la unidad organizativa del usuario que necesita crear y enviar envíos push. El usuario de una unidad organizativa secundaria no puede crear una entrega push con una aplicación asignada a la unidad organizativa principal.

* La campaña o el programa dentro del cual se crea la entrega push debe asignarse a la unidad organizativa del usuario que necesita crear y realizar las entregas push. El usuario de la unidad organizativa secundaria no puede crear una entrega push en una campaña o programa asignado a la unidad organizativa principal.

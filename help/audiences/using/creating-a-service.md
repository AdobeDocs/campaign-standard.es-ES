---
title: Creación de un servicio
seo-title: Creación de un servicio
description: Creación de un servicio
seo-description: Aprenda a crear su primer servicio y configúrelo para enviar confirmaciones de correo electrónico a sus suscriptores.
page-status-flag: no activado nunca
uuid: 0 d 95 d 852-0 f 22-4 b 7 b-b 301-8 fb 4844 c 3 ca 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: administración de suscripciones
discoiquuid: 6 b 7788 fe-fa 6 c -472 a -97 db -765595 ce 1589
context-tags: service, wizard; servicio, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

Para poder administrar las suscripciones, primero debe crear un servicio y configurarlo. La configuración de un nuevo servicio permite especificar las confirmaciones de correo electrónico que recibirán los perfiles al suscribirse o cancelar la suscripción del servicio. También debe definir las páginas de aterrizaje de suscripción y sin suscripción vinculadas al servicio. Por ejemplo, un vínculo de suscripción de servicio insertado en un mensaje de correo electrónico automáticamente dirigirá el perfil a la página de aterrizaje de suscripción que se especifique en el servicio.

Para configurar un servicio:

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. Si crea un nuevo servicio, simplemente siga los pasos que se muestran en la pantalla.

   Hay disponible una plantilla de servicio predeterminada. Esta plantilla está preconfigurada con páginas de aterrizaje predeterminadas y mensajes de correo electrónico de confirmación. Puede crear otras plantillas para definir configuraciones específicas. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **Service properties** section, accessed via the ![](assets/edit_darkgrey-24px.png) button in the service dashboard, configure the confirmation messages for subscriptions and unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. Seleccione una plantilla de mensaje de confirmación para suscripciones y cancelaciones. Hay tres modos disponibles:

   * **[!UICONTROL No message]**: este modo permite crear un servicio sin un mensaje de confirmación.
   * **[!UICONTROL Default message]**: este modo utilizará el mensaje predeterminado de suscripción o cancelación de suscripción. Los mensajes de confirmación predeterminados son genéricos y son los mismos para todos los servicios que utilicen el modo predeterminado.
   * **[!UICONTROL Custom message]**: este modo le permite gestionar mensajes de confirmación personalizados, específicos para cada servicio. You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. Guarde el servicio. Ahora está listo para utilizarse.

Una vez creado el servicio, puede empezar a ascenderlo.

**Temas relacionados:**

* [Gestión de un vídeo de suscripciones](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) y servicios
* [Promoción de un servicio](../../audiences/using/promoting-a-service.md)
* [Creación de una audiencia realizada por suscriptores](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vinculación de un formulario a un servicio en una página de aterrizaje](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)


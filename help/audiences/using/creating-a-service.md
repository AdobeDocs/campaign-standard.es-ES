---
title: Creación de un servicio
seo-title: Creación de un servicio
description: Creación de un servicio
seo-description: Obtenga información sobre cómo crear su primer servicio y configurarlo para enviar confirmaciones de correo electrónico a sus suscriptores.
page-status-flag: nunca activado
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar suscripciones
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: servicio,asistente;servicio,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 60424543028fa4df548d6d5bcfb1e9acc4131132

---


# Creación de un servicio{#creating-a-service}

Para poder administrar las suscripciones, primero debe crear un servicio y configurarlo. La configuración de un nuevo servicio le permite especificar las confirmaciones de correo electrónico que los perfiles recibirán cuando se suscriban o cancelen la suscripción al servicio. También definirá las páginas de aterrizaje de suscripción y cancelación de suscripción vinculadas al servicio. Por ejemplo, un vínculo de suscripción de servicio insertado en un correo electrónico dirigirá automáticamente el perfil a la página de aterrizaje de suscripción especificada en el servicio.

Para configurar un servicio:

1. En el menú avanzado **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Services]** mediante el logotipo de Adobe Campaign, agregue un nuevo servicio o seleccione uno existente. Si crea un nuevo servicio, simplemente siga los pasos que se muestran en la pantalla.

   Hay disponible una plantilla de servicio predeterminada. Esta plantilla está preconfigurada con páginas de aterrizaje y correos electrónicos de confirmación predeterminados. Puede crear otras plantillas para definir configuraciones específicas. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. En la **[!UICONTROL Service properties]** sección, a la que se accede a través del ![](assets/edit_darkgrey-24px.png) botón del panel de servicios, configure los mensajes de confirmación de suscripciones y cancelaciones.

   ![](assets/lp_service_parameters.png)

1. Fill in the **[!UICONTROL Service label]** field. La etiqueta de servicio es obligatoria cuando se utiliza un mensaje de confirmación personalizado.

1. Seleccione una plantilla de mensaje de confirmación para suscripciones y suscripciones. Hay tres modos disponibles:

   * **[!UICONTROL No message]**:: este modo le permite crear un servicio sin un mensaje de confirmación.
   * **[!UICONTROL Default message]**:: este modo utilizará el mensaje transaccional de confirmación de suscripción o cancelación de suscripción predeterminado. Los mensajes de confirmación predeterminados son genéricos y serán los mismos para todos los servicios que utilicen el modo predeterminado.

      >[!NOTE]
      >
      >Para modificar un mensaje predeterminado, haga clic en su etiqueta en la sección **[!UICONTROL Service properties]** o selecciónelo en la lista de mensajes transaccionales de Adobe Campaign, después de marcar la **[!UICONTROL Show internal transactional messages]** casilla.

   * **[!UICONTROL Custom message]**:: este modo le permite gestionar mensajes de confirmación personalizados, específicos para cada servicio. A continuación, seleccione el **[!UICONTROL Custom subscription event configuration]** que está asociado a una plantilla de mensaje [](../../channels/using/about-transactional-messaging.md) transaccional específica. Para obtener más información sobre esto, consulte [Confirmación de la suscripción a un servicio](../../audiences/using/confirming-subscription-to-a-service.md).

1. Guarde el servicio. Ahora está listo para ser utilizado.

Una vez creado un servicio, puede empezar a promocionarlo.

**Temas relacionados:**

* [Administración de un servicio y un vídeo de suscripciones](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html)
* [Promoción de un servicio](../../audiences/using/promoting-a-service.md)
* [Creación de una audiencia formada por suscriptores](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vinculación de un formulario a un servicio en una página de aterrizaje](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)


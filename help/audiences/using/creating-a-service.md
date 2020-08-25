---
title: Creación de un servicio
description: Aprenda a crear su primer servicio y configurarlo para enviar confirmaciones de correo electrónico a sus suscriptores.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---


# Creación de un servicio{#creating-a-service}

Para poder administrar suscripciones, primero debe crear un servicio y configurarlo. La configuración de un nuevo servicio le permite especificar las confirmaciones de correo electrónico que los perfiles van a recibir cuando se suscriban o cancelen su suscripción al servicio. También debe definir las páginas de aterrizaje de suscripción y de cancelación de suscripción vinculadas al servicio. Por ejemplo, un vínculo de suscripción de servicio insertado en un correo electrónico dirige automáticamente el perfil a la página de aterrizaje de suscripción especificada en el servicio.

Para configurar un servicio:

1. En el logotipo de Adobe Campaign, vaya al menú avanzado **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** y añada un servicio nuevo o seleccione uno existente. Si crea un nuevo servicio, simplemente siga los pasos que se muestran en la pantalla.

   Hay disponible una plantilla de servicio predeterminada. Esta plantilla está preconfigurada con páginas de aterrizaje predeterminadas y correos electrónicos de confirmación. Puede crear otras plantillas para definir configuraciones específicas. Para obtener más información, consulte la sección [Administración de plantillas](../../start/using/marketing-activity-templates.md).

1. En el panel del servicio, haga clic en el botón ![](assets/edit_darkgrey-24px.png) para acceder a la sección **[!UICONTROL Service properties]** y configure los mensajes de confirmación para suscripciones y cancelaciones de suscripción.

   ![](assets/lp_service_parameters.png)

1. Seleccione la opción **[!UICONTROL Subscriptions with an expiration date]** para establecer la duración de validez de la suscripción.

   ![](assets/lp_service_expiration.png)

   Puede usar la fecha de vencimiento en una actividad de segmentación para perfiles de destinatario suscritos a un servicio que no ha caducado.

1. Rellene el campo **[!UICONTROL Service label]**. La etiqueta de servicio es obligatoria cuando se utiliza un mensaje de confirmación personalizado.

1. Seleccione una plantilla de mensaje de confirmación para suscripciones y cancelaciones de suscripción. Hay tres modos disponibles:

   * **[!UICONTROL No message]**: este modo le permite crear un servicio sin un mensaje de confirmación.
   * **[!UICONTROL Default message]**: este modo utiliza el mensaje transaccional predeterminado de la suscripción o de la cancelación de la suscripción. Los mensajes de confirmación predeterminados son genéricos y son los mismos para todos los servicios que utilicen el modo predeterminado.

      >[!NOTE]
      >
      >Para modificar un mensaje predeterminado, haga clic en su etiqueta en la sección **[!UICONTROL Service properties]** o marque la casilla **[!UICONTROL Show internal transactional messages]** para seleccionarlo después en la lista de mensajes transaccionales de Adobe Campaign.

   * **[!UICONTROL Custom message]**: este modo le permite gestionar mensajes de confirmación personalizados, específicos para cada servicio. A continuación, seleccione la **[!UICONTROL Custom subscription event configuration]** que está asociada a una plantilla del [mensaje transaccional](../../channels/using/getting-started-with-transactional-msg.md) específica. Para obtener más información sobre esto, consulte [Confirmación de la suscripción a un servicio](../../audiences/using/confirming-subscription-to-a-service.md).

1. Guarde el servicio. Ahora está listo para usarlo.

Una vez creado un servicio, puede empezar a promoverlo.

**Temas relacionados:**

* Vídeo sobre la [Administración de un servicio y sus suscripciones](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/profiles-and-audiences/services-and-subscriptions.translate.html)
* [Promoción de un servicio](../../audiences/using/promoting-a-service.md)
* [Creación de una audiencia de suscriptores](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vinculación de una página de aterrizaje a un servicio](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)

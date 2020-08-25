---
title: Confirmación de la suscripción a un servicio
description: Siga estos pasos para configurar un mensaje de confirmación para los perfiles que se suscriben a un servicio en Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 100%

---


# Confirmación de la suscripción a un servicio{#confirming-subscription-to-a-service}

## Acerca del envío de confirmación de suscripción {#sending-subscription-confirmation}

En esta sección se describe cómo enviar un correo electrónico de confirmación personalizado y automático a los perfiles que se suscriben a un servicio específico.

Si desea enviar un mensaje de confirmación de una suscripción (o una cancelación de suscripción) a un servicio, puede utilizar el mensaje predeterminado o uno personalizado. Los pasos para seleccionar un mensaje de confirmación se describen en la sección [Creación de un servicio](../../audiences/using/creating-a-service.md).

Si decide utilizar el mensaje predeterminado, puede editar su contenido con las siguientes limitaciones:
* Solo puede personalizar el contenido del mensaje con campos limitados desde el contexto de evento.
* Este mensaje es el mismo para todos los servicios que utilicen el modo predeterminado.

Para enviar un correo electrónico de confirmación específico para un servicio determinado, puede crear un mensaje personalizado en el que también puede aprovechar campos de personalización de otros recursos. Para ello, debe crear y configurar un mensaje transaccional. Se puede hacer referencia a este mensaje:
* Desde el propio servicio. Para obtener más información, consulte [Configuración del mensaje de confirmación desde un servicio](#configuring-confirmation-message-from-service).
* Desde una página de aterrizaje de suscripción. Para obtener más información, consulte [Configuración del mensaje de confirmación desde una página de aterrizaje](#configuring-confirmation-message-from-landing-page).

## Configuración del mensaje de confirmación desde un servicio {#configuring-confirmation-message-from-service}

Por ejemplo, desea enviar automáticamente un mensaje de confirmación a los visitantes del sitio web cuando se suscriban a la newsletter de su marca.

Debe configurar un mensaje de correo electrónico transaccional y hacer referencia a ese mensaje desde el servicio deseado (en este caso, suscripción a la newsletter de su marca). Para enriquecer el mensaje transaccional con la información del servicio, puede definir una reconciliación al crear el evento.

Al configurarlo desde el servicio, el mensaje transaccional de confirmación se envía solo la primera vez que cada visitante se suscriba a ese servicio. Si un perfil ya está suscrito, no se envía ningún mensaje de confirmación.

### Paso 1: crear el correo electrónico de confirmación {#step-1--create-the-confirmation-email-1}

Se envía automáticamente un correo electrónico de confirmación a cada perfil que se suscriba a la newsletter (a través de una página de aterrizaje o por cualquier otro medio). La suscripción se considera un evento y el correo electrónico es un [mensaje transaccional](../../channels/using/getting-started-with-transactional-msg.md) que se envía a cada perfil que se suscribe al servicio.

A continuación se describen los pasos para crear el correo electrónico de confirmación. Como se hace referencia al mensaje transaccional en el servicio, primero debe crearlo.

#### Creación del evento {#create-the-event-1}

El correo electrónico de confirmación es un mensaje transaccional, ya que reacciona ante un evento: la suscripción a un servicio. Este mensaje se envía para confirmar la suscripción a la newsletter.

1. Cree un evento en el menú **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, accesible desde el logotipo de Adobe Campaign.
1. Introduzca una etiqueta, seleccione una dimensión de segmentación y haga clic en **[!UICONTROL Create]**.

   Los pasos de configuración se presentan en la sección [Configuración de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md).

1. En la sección **[!UICONTROL Fields]**, haga clic en **[!UICONTROL Create element]** y añada **[!UICONTROL publicLabel]** a la estructura de datos para habilitar la reconciliación.

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >El campo **[!UICONTROL publicLabel]** es obligatorio. Si no lo añade a la estructura de datos del evento, Adobe Campaign no puede realizar la reconciliación con el servicio. Al suscribirse a un servicio, este campo se rellena con el **[!UICONTROL Service label]** del servicio correspondiente.

1. En la sección **[!UICONTROL Enrichment]**, haga clic en **[!UICONTROL Create element]** y seleccione el recurso de destino **[!UICONTROL Service]**.

   ![](assets/confirmation_enrichment-service.png)

1. En la sección **[!UICONTROL Join definition]**, asigne el campo **[!UICONTROL publicLabel]** del recurso **[!UICONTROL Service]** al campo **[!UICONTROL publicLabel]** de configuración del evento.

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >Esto le permite usar campos de personalización del recurso **[!UICONTROL Service]** en el mensaje transaccional.

1. Guarde la configuración de evento y haga clic en **[!UICONTROL Publish]** para publicarlo.

El evento está listo. Ahora puede diseñar el mensaje de correo electrónico transaccional.

#### Diseño del mensaje de confirmación {#design-the-confirmation-message-1}

El correo electrónico de confirmación es un mensaje transaccional basado en el evento que acaba de publicar.

1. En el logotipo de Adobe Campaign, seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** y haga clic en **[!UICONTROL Transactional messages]**.
1. Seleccione el correo electrónico transaccional correspondiente al evento que acaba de publicar.

1. Haga clic en la sección **[!UICONTROL Content]** y seleccione una plantilla de correo electrónico. Para obtener más información sobre la edición de contenido de mensaje transaccional, consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).
1. Como tiene acceso directo a todos los campos del recurso **[!UICONTROL Service]**, puede seleccionar cualquier campo del nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event (rtEvent)]** > **[!UICONTROL Event context (ctx)]** > **[!UICONTROL Service]** para personalizar el contenido.

   ![](assets/confirmation_personalization-service.png)

   Para obtener más información sobre cómo personalizar un mensaje transaccional, consulte [esta sección](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

1. Vista previa del mensaje con un perfil de prueba. Para obtener más información, consulte [Definición de un perfil de prueba en un mensaje transaccional](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

1. Haga clic en **[!UICONTROL Save & close]** para guardar el contenido.
1. Publique el mensaje transaccional. Consulte [Publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

### Paso 2: crear y configurar el servicio {#step-2--create-and-configure-the-service-1}

1. Desde el logotipo de Adobe Campaign, en el menú avanzado seleccione **Perfiles y audiencias** > **Servicios** para crear un servicio.
1. En el panel de servicios, seleccione el botón ![](assets/edit_darkgrey-24px.png) y vaya a la sección **[!UICONTROL Service properties]**.
1. Rellene el campo **[!UICONTROL Service label]**.

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >Debe completar este campo para habilitar la reconciliación con el mensaje transaccional.

1. En la sección **[!UICONTROL Confirmation messages]**, seleccione **[!UICONTROL Custom message]**: este modo le permite hacer referencia a un mensaje de confirmación específico para perfiles suscritos a su servicio.
1. Seleccione la **[!UICONTROL Custom subscription event configuration]** asociada al mensaje transaccional que ha creado.

   ![](assets/confirmation_service-confirmation-message.png)

1. Haga clic en **[!UICONTROL Confirm]** para guardar el servicio.

Ahora, cada vez que un perfil se suscribe a este servicio, recibe el mensaje transaccional que ha definido, con campos personalizados asignados al servicio seleccionado.

>[!NOTE]
>
>Solo se envía un mensaje la primera vez que el usuario se suscribe.

## Configuración del mensaje de confirmación desde una página de aterrizaje {#configuring-confirmation-message-from-landing-page}

También puede hacer referencia al mensaje de confirmación desde una página de aterrizaje de suscripción mediante la opción **[!UICONTROL Start sending messages]** de la sección **[!UICONTROL Job]** de la página de aterrizaje.

Al hacer referencia al mensaje de confirmación de la página de aterrizaje, se envía un mensaje cada vez que se envía la página de aterrizaje (incluso si el perfil ya está suscrito).

### Paso 1: crear el correo electrónico de confirmación {#step-1--create-the-confirmation-email-2}

Se envía automáticamente un correo electrónico de confirmación a cada perfil que se suscribe a la newsletter mediante una página de aterrizaje. La suscripción se considera un evento y el correo electrónico es un [mensaje transaccional](../../channels/using/getting-started-with-transactional-msg.md) que se envía a cada perfil que se suscribe al servicio.

A continuación se describen los pasos para crear estos elementos. Como en la página de aterrizaje se hace referencia al mensaje transaccional, primero debe crearlo.

#### Creación del evento {#create-the-event-2}

El correo electrónico de confirmación es un [mensaje transaccional](../../channels/using/getting-started-with-transactional-msg.md), ya que reacciona ante un evento: la suscripción a un servicio. Este mensaje se envía para confirmar la suscripción a la newsletter.

1. Cree un evento en el menú **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, accesible desde el logotipo de Adobe Campaign.
1. Introduzca una etiqueta, seleccione una dimensión de segmentación y haga clic en **[!UICONTROL Create]**.

   Los pasos de configuración se presentan en la sección [Configuración de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md).

1. En la sección **[!UICONTROL Fields]**, haga clic en **[!UICONTROL Create element]** y añada **[!UICONTROL serviceName]** a la estructura de datos para habilitar la reconciliación.

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >El campo **[!UICONTROL serviceName]** es obligatorio. Si no lo añade a la estructura de datos de evento, Adobe Campaign no puede realizar la reconciliación con el servicio suscrito.

1. En la sección **[!UICONTROL Enrichment]**, haga clic en **[!UICONTROL Create element]** y seleccione el recurso de destino **[!UICONTROL Service]**.
1. En la sección **[!UICONTROL Join definition]**, asigne el campo **[!UICONTROL serviceName]** del recurso **[!UICONTROL Service]** al campo **[!UICONTROL name]** de configuración del evento.

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >Esto le permite usar campos de personalización del recurso [!UICONTROL Service] en el mensaje transaccional.

#### Diseño del mensaje de confirmación {#design-the-confirmation-message-2}

Los pasos para diseñar el mensaje transaccional se describen en esta [sección](#design-the-confirmation-message-1).

### Paso 2: crear y configurar el servicio {#step-2--create-and-configure-the-service-2}

1. Desde el logotipo de Adobe Campaign, seleccione en el menú avanzado **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** y cree un servicio.
1. En el panel de servicios, seleccione el botón ![](assets/edit_darkgrey-24px.png) y vaya a la sección **[!UICONTROL Service properties]**.
1. Rellene el campo **[!UICONTROL Service label]**. Esta etiqueta se muestra en el mensaje de confirmación y en la página de aterrizaje de suscripción.
1. Haga clic en **[!UICONTROL Confirm]** para guardar el servicio.

### Paso 3: crear y configurar la página de aterrizaje {#step-3--create-and-configure-the-landing-page}

Cree una página de aterrizaje de suscripción que se publicará en su sitio web.

Para crear y configurar esta página de aterrizaje, siga los pasos a continuación:

1. Diseñe una [nueva página de aterrizaje](../../channels/using/getting-started-with-landing-pages.md) basada en la plantilla **[!UICONTROL Subscription]**.
1. Edite las propiedades de la página de aterrizaje. En la sección **[!UICONTROL Job]** > **[!UICONTROL Specific actions]**, seleccione la opción **[!UICONTROL Specific service]** y elija el servicio que acaba de crear en la lista desplegable.

   ![](assets/confirmation_lp-specific-service.png)

1. Seleccione la opción **[!UICONTROL Start sending message]** y elija el mensaje transaccional que acaba de crear en la lista desplegable.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Personalice el contenido de la página de aterrizaje.

1. [Prueba y publicación](../../channels/using/testing-publishing-landing-page.md) de una página de aterrizaje.

Ahora, cada vez que un perfil se suscribe a la newsletter enviando la página de aterrizaje, recibe el mensaje de confirmación que ha definido con los campos personalizados asignados al servicio.

>[!NOTE]
>
>Se envía un mensaje cada vez que se envía la página de aterrizaje, aunque el perfil ya esté suscrito.

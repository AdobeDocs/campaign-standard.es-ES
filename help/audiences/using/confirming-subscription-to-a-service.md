---
title: Confirmación de la suscripción a un servicio
seo-title: Confirmación de la suscripción a un servicio
description: Confirmación de la suscripción a un servicio
seo-description: Siga estos pasos para configurar un mensaje de confirmación para los perfiles suscritos a un servicio en Adobe Campaign.
page-status-flag: nunca activado
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar suscripciones
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---


# Confirmación de la suscripción a un servicio{#confirming-subscription-to-a-service}

## Acerca del envío de confirmación de suscripción {#sending-subscription-confirmation}

Esta sección describe cómo enviar un correo electrónico de confirmación personalizado y automático a los perfiles que se suscriben a un servicio específico.

Si desea enviar un mensaje de confirmación de una suscripción (o cancelación de la suscripción) a un servicio, puede utilizar el mensaje predeterminado o un mensaje personalizado. The steps for selecting a confirmation message are presented in the Creating a service section.[](../../audiences/using/creating-a-service.md)

If you choose to use the default message, you can edit its content with the following limitations:
* You can only personalize the message content with limited fields from the event context.
* This message will be the same for all services that use the default mode.

To send a specific confirmation email for a given service, you can create a custom message, in which you will also be able to leverage personalization fields from other resources. To do this, you must create and configure a transactional message. This message can be referenced :
* From the service itself. For more on this, see Configuring confirmation message from a service.[](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-service)
* From a subscription landing page. For more on this, see Configuring confirmation message from a landing page.[](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-landing-page)

## Configuring confirmation message from a service {#configuring-confirmation-message-from-service}

For example, you want to automatically send a confirmation message to the visitors of your website when they subscribe to your brand newsletter.

Debe configurar un correo electrónico transaccional y hacer referencia a ese mensaje desde el servicio deseado (en este caso, suscribirse a su newsletter de marca). In order to enrich the transactional message with service information, you can define a reconciliation when creating the event.

Al configurarlo desde el servicio, el mensaje transaccional de confirmación se enviará sólo la primera vez que cada visitante se suscriba a ese servicio. If a profile is already subscribed, no confirmation message will be sent again to that profile.

### Paso 1: Crear el correo electrónico de confirmación {#step-1--create-the-confirmation-email-1}

Se enviará automáticamente un correo electrónico de confirmación a cada perfil que se suscriba a la newsletter (a través de una página de aterrizaje o de cualquier otro medio). La suscripción se considera un evento y el correo electrónico es un mensaje [](../../channels/using/about-transactional-messaging.md) transaccional que se dirigirá a cada perfil que se suscriba al servicio.

A continuación se describen los pasos para crear el correo electrónico de confirmación. Dado que el mensaje transaccional será referenciado en el servicio, primero debe crearlo.

#### Crear el evento {#create-the-event-1}

El correo electrónico de confirmación es un mensaje transaccional a medida que reacciona a un evento: la suscripción a un servicio. Este mensaje se enviará para confirmar la suscripción a la newsletter.

1. Cree un evento en el menú **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** , accesible desde el logotipo de Adobe Campaign.
1. Introduzca una etiqueta, seleccione una dimensión de objetivo y haga clic en **[!UICONTROL Create]**.

   Los pasos de configuración se presentan en la sección [Configuración de mensajes](../../administration/using/configuring-transactional-messaging.md) transaccionales.

1. En la **[!UICONTROL Fields]** sección, haga clic en **[!UICONTROL Create element]** y agregue **[!UICONTROL publicLabel]** a la estructura de datos para habilitar la reconciliación.

   ![](assets/confirmation_publicLabel-field.png)

   >[NOTA]
   >
   >El **[!UICONTROL publicLabel]** campo es obligatorio. Si no lo agrega a la estructura de datos del evento, Adobe Campaign no podrá realizar la reconciliación con el servicio. Al suscribirse a un servicio, este campo se rellenará con el nombre **[!UICONTROL Service label]** del servicio correspondiente.

1. En la **[!UICONTROL Enrichment]** sección, haga clic en **[!UICONTROL Create element]** y seleccione el recurso de **[!UICONTROL Service]** destino.

   ![](assets/confirmation_enrichment-service.png)

1. En la **[!UICONTROL Join definition]** sección , asigne el **[!UICONTROL publicLabel]** campo del **[!UICONTROL Service]** recurso al **[!UICONTROL publicLabel]** campo de configuración del evento.

   ![](assets/confirmation_publicLabel-join.png)

   >[NOTA]
   >
   >Esto le permitirá utilizar campos de personalización del **[!UICONTROL Service]** recurso en el mensaje transaccional.

1. Guarde la configuración del evento y haga clic en **[!UICONTROL Publish]** para publicarlo.

El evento está listo. Ahora puede diseñar el mensaje de correo electrónico transaccional.

#### Diseño del mensaje de confirmación {#design-the-confirmation-message-1}

El correo electrónico de confirmación es un mensaje transaccional basado en el evento que acaba de publicar.

1. From the Adobe Campaign logo, select  &gt;  and click .**[!UICONTROL Marketing plans]****[!UICONTROL Transactional messages]****[!UICONTROL Transactional messages]**
1. Seleccione el correo electrónico de transacción correspondiente al evento que acaba de publicar.

1. Haga clic en la **[!UICONTROL Content]** sección y seleccione una plantilla de correo electrónico. Para obtener más información sobre la edición de contenido de mensajes transaccionales, consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.
1. As you have direct access to all fields from the  resource, you can select any field from the  &gt;  &gt;  &gt; node to personalize your content.**[!UICONTROL Service]****[!UICONTROL Context]****[!UICONTROL Real-time event (rtEvent)]****[!UICONTROL Event context (ctx)]****[!UICONTROL Service]**

   ![](assets/confirmation_personalization-service.png)

   Para obtener más información sobre cómo personalizar un mensaje transaccional, consulte [esta sección](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

1. Preview your message using a test profile. For more on this, see Defining a test profile in a transactional message.[](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)

1. Click  to save your content.**[!UICONTROL Save & close]**
1. Publish the transactional message. See Publishing a transactional message.[](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)

### Step 2: Create and configure the service {#step-2--create-and-configure-the-service-1}

1. En el menú avanzado **Perfiles y audiencias** &gt; **Servicios** mediante el logotipo de Adobe Campaign, cree un servicio.
1. Go to the  section, accessed via the  button in the service dashboard.**[!UICONTROL Service properties]**![](assets/edit_darkgrey-24px.png)
1. Fill in the **[!UICONTROL Service label]** field.

   ![](assets/confirmation_service-label.png)

   >[NOTA]
   >
   >Debe completar este campo para habilitar la reconciliación con el mensaje transaccional.

1. En la **[!UICONTROL Confirmation messages]** sección, seleccione **[!UICONTROL Custom message]**: este modo le permite hacer referencia a un mensaje de confirmación específico para perfiles suscritos a su servicio.
1. Seleccione el mensaje **[!UICONTROL Custom subscription event configuration]** asociado con la transacción que ha creado.

   ![](assets/confirmation_service-confirmation-message.png)

1. Click **[!UICONTROL Confirm]** and save the service.

Ahora, cada vez que un perfil se suscribe a este servicio, recibe el mensaje transaccional que ha definido, con campos personalizados asignados al servicio seleccionado. Solo se enviará un mensaje la primera vez que el usuario se suscriba.

## Configuración del mensaje de confirmación desde una página de aterrizaje {#configuring-confirmation-message-from-landing-page}

También puede hacer referencia al mensaje de confirmación desde una página de aterrizaje de suscripción mediante la **[!UICONTROL Start sending messages]** opción de la **[!UICONTROL Job]** sección de la página de aterrizaje.

Al hacer referencia al mensaje de confirmación desde la página de aterrizaje, se enviará un mensaje cada vez que se envíe la página de aterrizaje (incluso si el perfil ya está suscrito).

### Paso 1: Crear el correo electrónico de confirmación {#step-1--create-the-confirmation-email-2}

Se enviará automáticamente un correo electrónico de confirmación a cada perfil que se suscriba a la newsletter a través de una página de aterrizaje. La suscripción se considera un evento y el correo electrónico es un mensaje [](../../channels/using/about-transactional-messaging.md) transaccional que se dirigirá a cada perfil que se suscriba al servicio.

A continuación se describen los pasos para crear estos elementos. Como en la página de aterrizaje se hará referencia al mensaje transaccional, primero debe crearlo.

#### Crear el evento {#create-the-event-2}

El mensaje de correo electrónico de confirmación es un mensaje [](../../channels/using/about-transactional-messaging.md) transaccional a medida que reacciona a un evento: la suscripción a un servicio. Este mensaje se enviará para confirmar la suscripción a la newsletter.

1. Cree un evento en el menú **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** , accesible desde el logotipo de Adobe Campaign.
1. Introduzca una etiqueta, seleccione una dimensión de objetivo y haga clic en **[!UICONTROL Create]**.

   Los pasos de configuración se presentan en la sección [Configuración de mensajes](../../administration/using/configuring-transactional-messaging.md) transaccionales.

1. En la **[!UICONTROL Fields]** sección, haga clic en **[!UICONTROL Create element]** y agregue **[!UICONTROL serviceName]** a la estructura de datos para habilitar la reconciliación.

   ![](assets/confirmation_serviceName-field.png)

   >[NOTA]
   >
   >El **[!UICONTROL serviceName]** campo es obligatorio. Si no lo agrega a la estructura de datos del evento, Adobe Campaign no podrá realizar la reconciliación con el servicio suscrito.

1. En la **[!UICONTROL Enrichment]** sección, haga clic en **[!UICONTROL Create element]** y seleccione el recurso de **[!UICONTROL Service]** destino.
1. En la **[!UICONTROL Join definition]** sección , asigne el **[!UICONTROL serviceName]** campo del **[!UICONTROL Service]** recurso al **[!UICONTROL name]** campo de configuración del evento.

   ![](assets/confirmation_serviceName-join.png)

   >[NOTA]
   >
   >Esto le permitirá utilizar campos de personalización del [!UICONTROL Service] recurso en el mensaje transaccional.

#### Diseño del mensaje de confirmación {#design-the-confirmation-message-2}

Los pasos para diseñar el mensaje transaccional se presentan en esta [sección](../../audiences/using/confirming-subscription-to-a-service.md#design-the-confirmation-message-1).

### Paso 2: Crear y configurar el servicio {#step-2--create-and-configure-the-service-2}

1. En el menú avanzado **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Services]** mediante el logotipo de Adobe Campaign, cree un servicio.
1. Vaya a la **[!UICONTROL Service properties]** sección, a la que se accede mediante el ![](assets/edit_darkgrey-24px.png) botón del panel de servicios.
1. Fill in the **[!UICONTROL Service label]** field. Esta etiqueta se mostrará en el mensaje de confirmación y en la página de inicio de la suscripción.
1. Click **[!UICONTROL Confirm]** and save the service.

### Paso 3: Crear y configurar la página de aterrizaje {#step-3--create-and-configure-the-landing-page}

Cree una página de inicio de suscripción que se publicará en su sitio web.

Para crear y configurar esta página de aterrizaje, siga los pasos a continuación:

1. Diseñar una [nueva página](../../channels/using/about-landing-pages.md) de aterrizaje basada en la **[!UICONTROL Subscription]** plantilla.
1. Edite las propiedades de la página de aterrizaje. En la sección **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** , seleccione la **[!UICONTROL Specific service]** opción y elija el servicio que acaba de crear en la lista desplegable.

   ![](assets/confirmation_lp-specific-service.png)

1. Seleccione la **[!UICONTROL Start sending message]** opción y elija el mensaje transaccional que acaba de crear en la lista desplegable.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Personalice el contenido de la página de aterrizaje.

1. [Pruebe y publique](../../channels/using/sharing-a-landing-page.md) la página de aterrizaje.

Ahora, cada vez que un perfil se suscribe a la newsletter enviando la página de aterrizaje, recibe el mensaje de confirmación que definió con los campos personalizados asignados al servicio.

>[NOTA]
>
>Se enviará un mensaje cada vez que se envíe la página de aterrizaje, aunque el perfil ya esté suscrito.

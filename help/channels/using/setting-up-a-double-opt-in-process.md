---
title: Configuración de un proceso de selección doble
seo-title: Configuración de un proceso de selección doble
description: Configuración de un proceso de selección doble
seo-description: Siga estos pasos para configurar un proceso de selección doble mediante páginas de aterrizaje en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 23 e 6 c 4 c 2-e 2 c 7-472 f-b 616-36 a 95225 ac 1 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: landing-pages
discoiquuid: 1 a 24504 e -7 f 9 d -4297-b 39 e-c 5 f 085 b 0 f 388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6dd0c32259d942a0fb790f345cd13800a57e814a

---


# Setting up a double opt-in process{#setting-up-a-double-opt-in-process}

## About double opt-in {#about-double-opt-in}

El mecanismo de selección doble es una práctica recomendada al enviar correos electrónicos. Protege a la plataforma de direcciones de correo electrónico incorrectas o no válidas, bots de spam y evita posibles quejas no deseadas.

El principio es enviar un mensaje de correo electrónico para confirmar el acuerdo del visitante antes de almacenarlo como'perfiles'en la base de datos de campaña: El visitante completa una página de aterrizaje en línea, luego recibe un correo electrónico y tiene que hacer clic en el vínculo de confirmación para finalizar su suscripción.

![](assets/optin_mechanism.png)

Para configurar esto, debe:

1. Cree y publique una página de aterrizaje para que los visitantes puedan registrarse y suscribirse. Esta página de aterrizaje estará disponible desde un sitio web. Visitors who fill in and submit this landing page will be stored in the database but ‘blacklisted', in order not to receive any communication before the final validation (see [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Cree y envíe automáticamente el correo electrónico de selección, con un vínculo de confirmación. Este correo electrónico dirigirá a la población que envió la página de aterrizaje. Se basará en una plantilla de correo electrónico que permita segmentar perfiles de «no participación».
1. Redirija a una página de aterrizaje de confirmación. Esta página de aterrizaje final le enviará un botón de confirmación: los visitantes deben hacer clic en él. Puede diseñar un correo electrónico de bienvenida para enviarlo como confirmación y, por ejemplo, agregar una oferta especial en el correo electrónico para nuevos destinatarios.

Estos pasos deben configurarse en Adobe Campaign en un orden específico para que todos los parámetros estén habilitados correctamente.

## Step 1: Create the confirmation landing page {#step-1--create-the-confirmation-landing-page}

El proceso para configurar el mecanismo de selección doble comienza con la creación de la página de aterrizaje de confirmación: esta página se mostrará cuando los visitantes hayan hecho clic en el correo electrónico de confirmación para registrarse.

Para crear y configurar esta página de aterrizaje, debe:

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**CONFIRMATION**'.

   If you need to use [services](../../audiences/using/about-subscriptions.md), you can also use the **[!UICONTROL Subscription (sub)]** template.

1. Edit the landing page properties and under the **[!UICONTROL Access and loading]** section, unselect the option **[!UICONTROL Authorize unidentified visitors]**, select **[!UICONTROL Preload visitor data]** (this one is not mandatory).

   ![](assets/optin_confirmlp_param.png)

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   Set the value to **false** and click **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Este contexto elimina el campo de lista negra para poder enviar correos electrónicos. We will see later that the first landing page was setting this field to **true** before confirmation, to prevent from sending emails to non-confirmed profiles. For more on this, see [Step 3: Create the acquisition landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-3--create-the-acquisition-landing-page).

1. Personalice el contenido de la página de aterrizaje: Puede mostrar datos personalizados y cambiar la etiqueta del botón de confirmación a'Clic aquí para confirmar mi suscripción ', por ejemplo.

   ![](assets/optin_confirmlp_design.png)

1. Adapte el contenido de la página de confirmación para informar a los suscriptores de que están registrados.

   ![](assets/optin_confimlp_page2.png)

1. [Pruebe y publique](../../channels/using/sharing-a-landing-page.md) la página de aterrizaje.

## Step 2: Create the confirmation email {#step-2--create-the-confirmation-email}

Una vez creada la página de aterrizaje de confirmación, puede diseñar el correo electrónico de confirmación: este correo electrónico se enviará automáticamente a cada visitante que valide la página de aterrizaje de adquisición. Esta validación se considera un evento y el correo electrónico es un mensaje transaccional vinculado a una regla de tipología específica que permite dirigir poblaciones de exclusión.

A continuación se describen los pasos para crear estos elementos. Debe seguirlos antes de crear la página de aterrizaje de adquisición, ya que esta plantilla de correo electrónico se hará referencia a ella.

### Create the event {#create-the-event}

The confirmation email is a [transactional message](../../channels/using/about-transactional-messaging.md) as it reacts to an event: the validation of the form. Primero debe crear el evento y, a continuación, crear la plantilla del mensaje de transacción.

1. Create an event, from the **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** menu, accessible from the Adobe Campaign logo, and enter the label '**CONFIRM**'.
1. Select the **[!UICONTROL Profile]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. In the **[!UICONTROL Fields]** section, click **[!UICONTROL Create element]** and add the **[!UICONTROL email]** in the data structure to enable reconciliation.
1. In the **[!UICONTROL Enrichment]** section, click **[!UICONTROL Create element]** and select the target resource **[!UICONTROL Profile]**. You can then map on the **[!UICONTROL email]** in the **[!UICONTROL Join definition]** section, or any other composite reconciliation key, depending on your needs.

   ![](assets/optin_eventcreate_join.png)

   If you need to use services, you can also add the **[!UICONTROL serviceName]**.

1. Select **[!UICONTROL Profile]** as the **[!UICONTROL Targeting enrichment]** in the dropdown list.
1. Click **[!UICONTROL Publish]** to publish the event.

El evento está listo. Ahora puede diseñar la plantilla de correo electrónico. This template must include a link to the **CONFIRMATION** landing page created before. For more on this, see [Design the confirmation message](../../channels/using/setting-up-a-double-opt-in-process.md#design-the-confirmation-message).

### Create the typology rule {#create-the-typology-rule}

You need to create a specific [typology rule](../../administration/using/about-typology-rules.md), by duplicating an out-of-box one. Esta regla permite enviar mensajes a los perfiles que no confirmaron aún su acuerdo y siguen bloqueados. De forma predeterminada, las reglas de tipología excluyen los perfiles de exclusión (es decir, bloqueados). Para crear esta regla de tipología, siga estos pasos:

1. From the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** and click **[!UICONTROL Typologies]**.
1. Duplicate the out-of-box typology **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Once duplication confirmed, edit the new typology and enter the label **TYPOLOGY_PROFILE**.
1. Remove the **blacklisted address** rule.
1. Click **[!UICONTROL Save]**.

Ahora, esta tipología se puede asociar al correo electrónico de confirmación.

### Design the confirmation message {#design-the-confirmation-message}

El correo electrónico de confirmación es un mensaje de transacción basado en el evento creado anteriormente. Siga los pasos a continuación para crear este mensaje:

1. From the Adobe Campaign logo, select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** and click **[!UICONTROL Transactional messages]**.
1. Edit the **CONFIRM** email template and personalize it. Puede cargar un contenido existente o utilizar una plantilla lista para usar.
1. Add a link to the **CONFIRMATION** landing page, and click **[!UICONTROL Confirm]** to save modifications.

   ![](assets/optin_email_selectlp.png)

1. Edite las propiedades de la plantilla de correo electrónico. In the **[!UICONTROL Advanced parameters]** &gt; **[!UICONTROL Preparation]** section, select the **TYPOLOGY_PROFILE** typology created before.
1. Guarde y publique el mensaje de transacción.

## Step 3: Create the acquisition landing page {#step-3--create-the-acquisition-landing-page}

Debe crear la página inicial de adquisición de adquisición: este formulario de op-in se publicará en su sitio web.

Para crear y configurar esta página de aterrizaje, debe:

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**ACQUISITION**'.
1. Edit the landing page properties: in the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   and set the value to **true**.

   Esto es obligatorio para forzar la lista negra y evitar enviar mensajes a los visitantes que no confirmaron su acuerdo. The validation of the CONFIRMATION landing page will set this field to **false** after confirmation. For more on this, see [Step 1: Create the confirmation landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-1--create-the-confirmation-landing-page).

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** section, select the option **[!UICONTROL Start sending messages]**.
1. In the associated drop-down list, choose the **CONFIRM** transactional message template you created.

   ![](assets/optin_acquisition_startoption.png)

1. Personalice el contenido de la página de aterrizaje, según su marca y los datos que necesite adquirir. You can display personalized data and change the label of the confirmation button to **Confirm my subscription** for example.

   ![](assets/optin_acquisition_page1.png)

1. Personalice la página de confirmación para informar al nuevo suscriptor de que necesita validar su suscripción.

   ![](assets/optin_acquisition_page2.png)

1. [Pruebe y publique](../../channels/using/sharing-a-landing-page.md) la página de aterrizaje.

Ahora se configura un mecanismo de selección doble. You can run and test the procedure from end to end, starting from the public URL of this **[!UICONTROL ACQUISITION]** landing page. Esta URL se muestra en el tablero de página de aterrizaje.

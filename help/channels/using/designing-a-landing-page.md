---
title: Diseño de una página de aterrizaje
seo-title: Diseño de una página de aterrizaje
description: Diseño de una página de aterrizaje
seo-description: Siga estos pasos para diseñar el contenido de una página de aterrizaje y vincularlo a un servicio.
page-status-flag: no activado nunca
uuid: de 6 fe 190-835 c -40 fd -8101-a 809 b 430 b 423
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: landing-pages
discoiquuid: bd 77 d 6 f 0-3143-4030-a 91 b -988 a 2 bebc 534
context-tags: Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Designing a landing page{#designing-a-landing-page}

## About content design {#about-content-design}

Landing pages are created as any [marketing activity](../../start/using/marketing-activities.md#about-marketing-activities).

Al diseñar una página de aterrizaje, debe definir el contenido de:

* la página misma,
* la página de confirmación,
* la página de error.

Utilice el conmutador en la barra de acciones para mostrar y configurar cada una de estas páginas.

El contenido de estas páginas se diseña mediante el editor de contenido de campaña. Refer to [Design content](../../designing/using/about-landing-page-content-design.md).

## Mapping form fields {#mapping-form-fields}

Los campos de entrada se utilizan para almacenar o actualizar datos en la base de datos de campaña. Para ello, debe vincular campos de base de datos con zona de entrada, botón de opción o bloques de tipo de casilla de verificación. Para ello:

1. Seleccione un bloque en la página de aterrizaje.
1. Complete the **[!UICONTROL Form data]** part in the palette.

   ![](assets/editing_lp_content_4.png)

1. Choose a database field to link with the form field in the **[!UICONTROL Field]** selection zone.

   When the **[!UICONTROL Mandatory]** option is checked, the page can only be submitted if the user has completed this field. Si no se completa un campo obligatorio, aparecerá un mensaje de error cuando el usuario valide la página.

   >[!NOTE]
   >
   >Landing pages can only be mapped with **Profiles**.

1. Define the field type by choosing, for example **[!UICONTROL Text]**, **[!UICONTROL Number]**,or **[!UICONTROL Date]** in the **[!UICONTROL HTML type of the field]** selection area.

>[!NOTE]
>
>Los campos predeterminados de las páginas de aterrizaje integradas están preconfigurados. Puede modificarlas según sea necesario.

## Submitting the form {#submitting-the-form}

Puede seleccionar la acción que realizar cuando el visitante haga clic en el botón de envío. Para ello:

1. Seleccione el botón de envío de la página de aterrizaje.
1. Seleccione la acción en la lista desplegable del panel izquierdo. Possible actions are: **[!UICONTROL Refresh]** (to refresh the page) and **[!UICONTROL Next page]** (to display the confirmation page).

   ![](assets/editing_lp_content_5.png)

Además, puede cambiar la etiqueta del botón o configurar un vínculo específico. Para ello:

1. Seleccione el botón Enviar.
1. Click on the ![](assets/lp_link_properties.png) button in the left panel.
1. Introduzca la etiqueta del botón, seleccione el tipo de vínculo, sus propiedades y el destino.

   ![](assets/lp_link_custom.png)

## Linking a form to a service {#linking-a-form-to-a-service}

Puede vincular un formulario a un servicio para que los perfiles puedan suscribirse a un servicio específico al validar las páginas de aterrizaje.

Los parámetros para vincular una página de aterrizaje permiten especificar el tipo de acción realizado y si la página de aterrizaje está vinculada específicamente a un único servicio o si es genérico.

Para seleccionar el servicio que desea vincular, debe:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Choose **[!UICONTROL Subscription]** in the **[!UICONTROL Specific actions]** drop-down list.

   ![](assets/lp_parameters_5.png)

1. Select **[!UICONTROL Specific service]** to link the landing page to a single service. No seleccione esta opción si desea utilizar varios servicios con la página de aterrizaje.

   Use the **[!UICONTROL Specified service in the URL]** option to allow the landing page to be used for several services. Por lo tanto, debe hacer referencia a la página de aterrizaje al configurar el servicio.

### Confirm a landing page submission {#confirm-a-landing-page-submission}

Cuando un visitante envía una página de aterrizaje, puede configurar las acciones activadas. Para ello:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Under the **[!UICONTROL Specific actions]** section, select **[!UICONTROL Start sending message]** to determine the sending of an automatic message, for example to confirm subscription to a service. Es necesario seleccionar una plantilla de envío de correo electrónico.

   Tenga en cuenta que si ya se ha configurado un mensaje de confirmación en el nivel de servicio, no debe seleccionar ninguno en esta pantalla para evitar enviar varios mensajes de confirmación. Refer to [Configure a service](../../audiences/using/creating-a-service.md).

1. Create **[!UICONTROL Additional data]** to enable storing additional data when the landing page is being submitted. Estos datos no son visibles para las personas que visitan la página. Solo se tienen en cuenta los valores constantes.

   ![](assets/lp_parameters_6.png)

## Setting permissions and pre-loading data {#setting-permissions-and-pre-loading-data}

El acceso a una página de aterrizaje puede restringirse a los visitantes identificados, que provienen de un vínculo de un mensaje enviado por Campaign por ejemplo. En este caso, puede cargar previamente sus datos en la página de aterrizaje. Para ello:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Access & loading]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   Si un visitante de la página corresponde a un perfil de la base de datos, sus datos se muestran en los campos del formulario que se asignan con los datos de la base de datos y se tienen en cuenta los elementos de personalización de la página de aterrizaje.

   ![](assets/lp_parameters_3.png)

También puede:

* Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.
* Authorize any visitor to access the landing page, using the **[!UICONTROL Authorize unidentified visitors]** option.

## Setting Google reCAPTCHA {#setting-google-recaptcha}

Puede configurar Google recaptcha V 3 con su página de aterrizaje para protegerla del correo no deseado y de los abusos provocados por bots. Para poder utilizarla con su página de aterrizaje, primero debe crear una cuenta externa. For more information on how to configure it, refer to this [section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Una vez configurada la cuenta externa de Google recaptcha V 3, puede agregarla a su página de aterrizaje:

1. Before publishing your landing page, access the page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon from you landing page dashboard.

   ![](assets/lp_parameters_google3.png)

1. Unfold the **[!UICONTROL Access & loading]** menu.
1. Check the **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** option.
1. Seleccione la cuenta externa de Google recaptcha previamente creada.

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

La página de aterrizaje ahora está configurada con Google recaptcha, que se puede ver en la parte inferior de la página.

![](assets/lp_parameters_google2.png)

A continuación, Google recaptcha devolverá una puntuación basada en las interacciones de los usuarios con su página. To check your score, connect to your [Google admin console](https://g.co/recaptcha/admin).

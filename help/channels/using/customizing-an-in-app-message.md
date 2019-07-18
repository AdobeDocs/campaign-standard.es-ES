---
title: Personalización de un mensaje en la aplicación
seo-title: Personalización de un mensaje en la aplicación
description: Personalización de un mensaje en la aplicación
seo-description: Aprenda a personalizar los mensajes en la aplicación con varias opciones.
page-status-flag: no activado nunca
uuid: 1 d 9 c 08 ed -4 de 5-440 d-bf 51-4 a 437 eec 67 d 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajería en la aplicación
discoiquuid: c 9 c 3 e 033-e 319-447 b -8 d 87-ff 7 dd 4941876
context-tags: delivery, inappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Customizing an In-App message{#customizing-an-in-app-message}

Para perfeccionar el mensaje en la aplicación, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas al diseñar una aplicación.

El editor de contenido en la aplicación permite elegir entre dos modos de mensaje en la aplicación:

* [Plantilla de mensaje](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): Esta plantilla le permite personalizar completamente su In-App con imágenes o botones de acción.
* [Mensaje personalizado](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): esta plantilla permite importar HTML personalizado.

![](assets/inapp_customize_1.png)

**Temas relacionados:**

* [Envío del mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Informes dentro de la aplicación](../../reporting/using/in-app-report.md)

## Customizing with a message template {#customizing-with-a-message-template}

### Layout {#layout}

The **[!UICONTROL Layout]** drop-down provides you with four different options to choose from depending on your messaging needs:

* **[!UICONTROL Full page]**: Este tipo de diseño abarca toda la pantalla de los dispositivos de audiencia.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Large modal]**: Este diseño aparece en una ventana de estilo de alerta grande, la aplicación sigue estando visible en segundo plano.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Small modal]**: Este diseño aparece como una ventana pequeña de tipo alert, la aplicación sigue estando visible en segundo plano.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Alert]**: Este tipo de diseño aparece como un mensaje de alerta nativo de OS.

   Solo puede admitir componentes de texto y botón.

* **[!UICONTROL Local notification]**: Este tipo de diseño aparece como un mensaje de pancarta.

   Solo puede admitir sonido, texto y destino. For more on local notification, refer to [Customizing a local notification message type](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Cada tipo de maquetación se puede previsualizar en diferentes dispositivos, como teléfono, tableta, plataforma, por ejemplo Android o iOS y orientación, por ejemplo horizontal o vertical en la ventana derecha del editor de contenido.

![](assets/inapp_customize_4.png)

### Media {#media}

The **[!UICONTROL Media]** drop-down allows you to add media to your In-App message to create a compelling experience for end user.

1. Select your **[!UICONTROL Media Type]** between image and video.
1. For the **[!UICONTROL Image]** media type, enter your URL in the **[!UICONTROL Media URL]** field based on the supported formats.

   If needed, you can also enter the path to a **[!UICONTROL Bundled image]** which can be used if the device is offline.

   ![](assets/inapp_customize_5.png)

1. For the **[!UICONTROL Video]** media type, enter your URL in the **[!UICONTROL Media URL]** field.

   Then, enter your **[!UICONTROL Video poster]** to be used while the video is downloading on the audience devices or until users tap the play button.

   ![](assets/inapp_customize_6.png)

### Text {#text}

Si es necesario, también puede agregar un título y contenido de mensaje al mensaje en la aplicación. Para personalizar mejor el mensaje en la aplicación, puede agregar diferentes campos de personalización, bloques de contenido y texto dinámico al contenido.

1. In the **[!UICONTROL Text]** drop-down, add a title in the **[!UICONTROL Message title]** field.

   ![](assets/inapp_customize_9.png)

1. Add your content in the **[!UICONTROL Message content]** field.
1. To further personalize your text, click the ![](assets/edit_darkgrey-24px.png) icon to add personalization fields.

   ![](assets/inapp_customize_8.png)

1. Escriba el contenido del mensaje y añada los campos de personalización si es necesario.

   For more information on personalization field, refer to this [section](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Compruebe el contenido del mensaje en la ventana de vista previa.

   ![](assets/inapp_customize_11.png)

### Buttons {#buttons}

Puede agregar hasta dos botones al mensaje en la aplicación.

1. In the **[!UICONTROL Buttons]** drop-down, enter the text of your first button in the **[!UICONTROL Primary]** category.

   ![](assets/inapp_customize_12.png)

1. Choose which of the two actions **[!UICONTROL Dismiss]** and **[!UICONTROL Redirect]** will be assigned to your primary button.
1. In the **[!UICONTROL Secondary]** category, add a second button to your In-App if needed by entering your text.
1. Seleccione la acción asociada al segundo botón.
1. If you chose the **[!UICONTROL Redirect]** action, enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field.

   ![](assets/inapp_customize_13.png)

1. Enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field, if you chose the **[!UICONTROL Redirect]** action,
1. Compruebe el contenido del mensaje en la ventana de vista previa o haga clic en el botón Vista previa.

   Refer to the [Previewing the In-App message](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) page.

   ![](assets/inapp_customize_11.png)

### Settings {#settings}

1. In the **[!UICONTROL Settings]** category, select your background color between light and dark.
1. Choose to display or not a close button with the **[!UICONTROL Show close button]** option to provide users a way to dismiss the In-App message.
1. Select if your button alignment will be horizontal or vertical with the **[!UICONTROL Button alignment]** option.
1. Elija si el mensaje en la aplicación se puede revocar automáticamente o no después de unos segundos.

   ![](assets/inapp_customize_7.png)

## Customizing a local notification message type {#customizing-a-local-notification-message-type}

Las notificaciones locales solo pueden activarse por una aplicación en un momento concreto y en función de un evento. Avisarán a los usuarios de que algo está sucediendo en su aplicación incluso sin tener acceso a Internet.

Para personalizar una notificación local:

1. From your **[!UICONTROL Content]** page, select **[!UICONTROL Local notification]** in the **[!UICONTROL Layout]** category

   ![](assets/inapp_customize_17.png)

1. Under the **[!UICONTROL Text]** category, type down your **[!UICONTROL Message title]** and **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. Under the **[!UICONTROL Advanced option]** category, in the **[!UICONTROL Wait to display]** field, choose how long in seconds your local notification will be displayed on screen once your event is triggered.
1. In the **[!UICONTROL Sound]** field, enter the filename of the sound file, without the extension, to be played by the mobile device when the local notification is received.

   El archivo de sonido se reproduce al enviar la notificación si el archivo se define en el paquete de la aplicación móvil. De lo contrario, se reproduce el sonido predeterminado del dispositivo.

   ![](assets/inapp_customize_19.png)

1. Specify a destination to redirect your users when they interact with your local notification in the **[!UICONTROL Deeplink URL]** field.
1. Para pasar datos personalizados en la carga útil en forma de pares de valor clave, puede agregar campos personalizados a la notificación local. In the **[!UICONTROL Custom fields]** category, click the **[!UICONTROL Create an element]** button.
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   Tenga en cuenta que la gestión y el propósito de los campos personalizados es completamente hasta la aplicación móvil.

1. In the **[!UICONTROL Apple options]** category, fill in the **[!UICONTROL Category]** fields to add a category ID for custom actions if available in your Apple mobile application.

## Customizing with a custom HTML message {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>El mensaje HTML personalizado no admite personalización de contenido.

The **[!UICONTROL Custom message]** mode allows you to directly import one of your pre-configured HTML message.

Para ello, basta con arrastrar y soltar o seleccionar el archivo desde el equipo.

Your file must have a specific layout which can be found by clicking the **Download the sample file** option.

![](assets/inapp_customize_16.png)

También puede encontrar una lista de requisitos personalizados HTML para una importación correcta en Adobe Campaign.

![](assets/inapp_customize_3.png)

Una vez importado el HTML, puede encontrar una vista previa del archivo en diferentes dispositivos en la ventana de vista previa.

## Previewing the In-App message {#previewing-the-in-app-message}

Antes de enviar el mensaje en la aplicación, puede probar con los perfiles de prueba para comprobar qué verá la audiencia objetivo cuando reciban la entrega.

1. Click the **[!UICONTROL Preview]** button.

   ![](assets/inapp_sending_2.png)

1. Click the **[!UICONTROL Select a test profile]** button and select one of your test profiles to start previewing your delivery. For more information on test profiles, refer to this [section](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Compruebe su mensaje en distintos dispositivos, como Android, teléfonos iphone o incluso tablets. También puede comprobar si los campos de personalización están recuperando los datos correctos.

   ![](assets/inapp_sending_3.png)

1. Ahora puede enviar su mensaje y medir su impacto con los informes de entrega. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


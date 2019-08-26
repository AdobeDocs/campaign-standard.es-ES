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
source-git-commit: 43183a3adc35da3dac807a888f1b694fbb9a623c

---


# Personalización de un mensaje en la aplicación{#customizing-an-in-app-message}

Para perfeccionar el mensaje en la aplicación, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas al diseñar una aplicación.

El editor de contenido en la aplicación permite elegir entre dos modos de mensaje en la aplicación:

* [Plantilla de mensaje](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): Esta plantilla le permite personalizar completamente su In-App con imágenes o botones de acción.
* [Mensaje personalizado](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): esta plantilla permite importar HTML personalizado.

![](assets/inapp_customize_1.png)

**Temas relacionados:**

* [Envío del mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Informes dentro de la aplicación](../../reporting/using/in-app-report.md)

## Personalización con una plantilla de mensaje {#customizing-with-a-message-template}

### Diseño {#layout}

La **[!UICONTROL Layout]** lista desplegable le proporciona cuatro opciones diferentes para elegir según sus necesidades de mensajería:

* **[!UICONTROL Full page]**: Este tipo de diseño abarca toda la pantalla de los dispositivos de audiencia.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Large modal]**: Este diseño aparece en una ventana de estilo de alerta grande, la aplicación sigue estando visible en segundo plano.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Small modal]**: Este diseño aparece como una ventana pequeña de tipo alert, la aplicación sigue estando visible en segundo plano.

   Admite los componentes multimedia (imagen, vídeo), texto y botón.

* **[!UICONTROL Alert]**: Este tipo de diseño aparece como un mensaje de alerta nativo de OS.

   Solo puede admitir componentes de texto y botón.

* **[!UICONTROL Local notification]**: Este tipo de diseño aparece como un mensaje de pancarta.

   Solo puede admitir sonido, texto y destino. Para obtener más información sobre la notificación local, consulte [Personalización de un tipo de mensaje de notificación local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Cada tipo de maquetación se puede previsualizar en diferentes dispositivos, como teléfono, tableta, plataforma, por ejemplo Android o iOS y orientación, por ejemplo horizontal o vertical en la ventana derecha del editor de contenido.

![](assets/inapp_customize_4.png)

### Medios {#media}

La **[!UICONTROL Media]** lista desplegable permite agregar medios al mensaje en la aplicación para crear una experiencia convincente para el usuario final.

1. Seleccione la **[!UICONTROL Media Type]** imagen y el vídeo.
1. Para el tipo **[!UICONTROL Image]** de papel, introduzca su URL en **[!UICONTROL Media URL]** el campo según los formatos admitidos.

   Si es necesario, también puede introducir la ruta a una **[!UICONTROL Bundled image]** que puede utilizarse si el dispositivo está sin conexión.

   ![](assets/inapp_customize_5.png)

1. Para el tipo **[!UICONTROL Video]** de papel, introduzca su URL en **[!UICONTROL Media URL]** el campo.

   A continuación, introduzca su **[!UICONTROL Video poster]** que se utilizará mientras se descarga el vídeo en los dispositivos de audiencia o hasta que los usuarios toquen el botón de reproducción.

   ![](assets/inapp_customize_6.png)

### Texto {#text}

Si es necesario, también puede agregar un título y contenido de mensaje al mensaje en la aplicación. Para personalizar mejor el mensaje en la aplicación, puede agregar diferentes campos de personalización, bloques de contenido y texto dinámico al contenido.

1. En la **[!UICONTROL Text]** lista desplegable, agregue un título en **[!UICONTROL Message title]** el campo.

   ![](assets/inapp_customize_9.png)

1. Agregue el contenido en **[!UICONTROL Message content]** el campo.
1. Para personalizar aún más el texto, haga clic ![](assets/edit_darkgrey-24px.png) en el icono para agregar campos de personalización.

   ![](assets/inapp_customize_8.png)

1. Escriba el contenido del mensaje y añada los campos de personalización si es necesario.

   Para obtener más información sobre el campo de personalización, consulte esta [sección](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Compruebe el contenido del mensaje en la ventana de vista previa.

   ![](assets/inapp_customize_11.png)

### Botones {#buttons}

Puede agregar hasta dos botones al mensaje en la aplicación.

1. En la **[!UICONTROL Buttons]** lista desplegable, introduzca el texto del primer botón de la **[!UICONTROL Primary]** categoría.

   ![](assets/inapp_customize_12.png)

1. Elija cuál de las dos acciones **[!UICONTROL Dismiss]** y **[!UICONTROL Redirect]** se asignará al botón principal.
1. En **[!UICONTROL Secondary]** la categoría, agregue un segundo botón a la aplicación si es necesario introduciendo su texto.
1. Seleccione la acción asociada al segundo botón.
1. Si elige **[!UICONTROL Redirect]** la acción, introduzca su URL web o el vínculo profundo en **[!UICONTROL Destination URL]** el campo.

   ![](assets/inapp_customize_13.png)

1. Ingrese la URL Web o el vínculo profundo en el **[!UICONTROL Destination URL]** campo, si elige **[!UICONTROL Redirect]** la acción,
1. Compruebe el contenido del mensaje en la ventana de vista previa o haga clic en el botón Vista previa.

   Consulte la [Vista previa de la página del mensaje](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) en la aplicación.

   ![](assets/inapp_customize_11.png)

### Configuración {#settings}

1. En **[!UICONTROL Settings]** la categoría, seleccione el color de fondo entre claro y oscuro.
1. Elija mostrar o no un botón de cierre con **[!UICONTROL Show close button]** la opción de proporcionar a los usuarios una forma de ignorar el mensaje en la aplicación.
1. Seleccione si la alineación de botones será horizontal o vertical con **[!UICONTROL Button alignment]** la opción.
1. Elija si el mensaje en la aplicación se puede revocar automáticamente o no después de unos segundos.

   ![](assets/inapp_customize_7.png)

## Personalización de un tipo de mensaje de notificación local {#customizing-a-local-notification-message-type}

Las notificaciones locales solo pueden activarse por una aplicación en un momento concreto y en función de un evento. Avisarán a los usuarios de que algo está sucediendo en su aplicación incluso sin tener acceso a Internet.

Para personalizar una notificación local:

1. Desde **[!UICONTROL Content]** la página, seleccione **[!UICONTROL Local notification]** en la **[!UICONTROL Layout]** categoría

   ![](assets/inapp_customize_17.png)

1. Debajo **[!UICONTROL Text]** de la categoría, escriba su **[!UICONTROL Message title]** y **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. En **[!UICONTROL Advanced option]** la categoría, en **[!UICONTROL Wait to display]** el campo, elija el tiempo en segundos que la notificación local se mostrará en la pantalla una vez que se active el evento.
1. En **[!UICONTROL Sound]** el campo, introduzca el nombre de archivo del archivo de sonido, con la extensión, que reproducirá el dispositivo móvil cuando reciba la notificación local.

   El archivo de sonido se reproduce al enviar la notificación si el archivo se define en el paquete de la aplicación móvil. De lo contrario, se reproduce el sonido predeterminado del dispositivo.

   ![](assets/inapp_customize_19.png)

1. Especifique un destino para redirigir a los usuarios cuando interactúen con su notificación local en **[!UICONTROL Deeplink URL]** el campo.
1. Para pasar datos personalizados en la carga útil en forma de pares de valor clave, puede agregar campos personalizados a la notificación local. En **[!UICONTROL Custom fields]** la categoría, haga clic en **[!UICONTROL Create an element]** el botón.
1. Escriba el **[!UICONTROL Keys]****[!UICONTROL Values]** que corresponda a cada clave.

   Tenga en cuenta que la gestión y el propósito de los campos personalizados es completamente hasta la aplicación móvil.

1. En **[!UICONTROL Apple options]** la categoría, rellene **[!UICONTROL Category]** los campos para agregar un ID de categoría para acciones personalizadas, si está disponible en la aplicación móvil de Apple.

## Personalización con un mensaje HTML personalizado {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>El mensaje HTML personalizado no admite personalización de contenido.

El **[!UICONTROL Custom message]** modo permite importar directamente uno de los mensajes HTML preconfigurados.

Para ello, basta con arrastrar y soltar o seleccionar el archivo desde el equipo.

El archivo debe tener un diseño específico que se puede encontrar haciendo clic en la **opción Descargar archivo** de ejemplo.

![](assets/inapp_customize_16.png)

También puede encontrar una lista de requisitos personalizados HTML para una importación correcta en Adobe Campaign.

![](assets/inapp_customize_3.png)

Una vez importado el HTML, puede encontrar una vista previa del archivo en diferentes dispositivos en la ventana de vista previa.

## Vista previa del mensaje en la aplicación {#previewing-the-in-app-message}

Antes de enviar el mensaje en la aplicación, puede probar con los perfiles de prueba para comprobar qué verá la audiencia objetivo cuando reciban la entrega.

1. Haga clic en **[!UICONTROL Preview]** el botón.

   ![](assets/inapp_sending_2.png)

1. Haga clic en **[!UICONTROL Select a test profile]** el botón y seleccione uno de los perfiles de prueba para empezar a previsualizar el envío. Para obtener más información sobre los perfiles de prueba, consulte esta [sección](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Compruebe su mensaje en distintos dispositivos, como Android, teléfonos iphone o incluso tablets. También puede comprobar si los campos de personalización están recuperando los datos correctos.

   ![](assets/inapp_sending_3.png)

1. Ahora puede enviar su mensaje y medir su impacto con los informes de entrega. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


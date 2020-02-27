---
title: Uso de imágenes
description: Descubra cómo administrar imágenes en correos electrónicos con el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 881c89272884c6340e170ab13e84612a5af19acd

---


# Uso de imágenes {#images}

## Inserción de imágenes{#inserting-images}

Puede insertar imágenes en sus correos electrónicos y páginas de aterrizaje.

Los siguientes tipos de imágenes están disponibles según la configuración:

* Imágenes locales
* Imágenes compartidas desde Adobe Experience Cloud: consulte [Uso de Campaign y los recursos del servicio](../../integrating/using/working-with-campaign-and-assets-core-service.md) principal / Recursos On Demand
* Imágenes dinámicas de Adobe Target: consulte [Uso de Campaign y Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Si decide agregar una imagen directamente editando la versión HTML del correo electrónico, no debe llamar a los archivos **externos en una etiqueta** &lt;script> de la página HTML. Estos archivos no se importan en el servidor de Adobe Campaign.

### Inserción de imágenes en un correo electrónico {#inserting-images-in-an-email}

1. Agregue un componente de estructura. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.
1. Dentro de este componente de estructura, agregue un componente **[!UICONTROL Image]** de contenido.

   ![](assets/des_insert_images_1.png)

1. Haga clic **[!UICONTROL Browse]**. Arrastre y suelte una imagen o haga clic para seleccionar un archivo del equipo.

   ![](assets/des_insert_images_2.png)

1. Seleccione el componente de contenido que acaba de añadir.
1. Compruebe las propiedades de la imagen y ajústelas si es necesario.

   ![](assets/des_insert_images_3.png)

## Configuración de propiedades de imagen{#setting-up-image-properties}

Al seleccionar un bloque que contiene una imagen, se ofrecen las siguientes propiedades en la paleta:

* **Activar personalización** permite personalizar el origen de la imagen. Consulte [Personalización de un origen](../../designing/using/personalization.md#personalizing-an-image-source)de imagen.
* **El título** de imagen permite definir un título para la imagen.
* **El texto** alternativo (correo electrónico) o el **rótulo** (página de aterrizaje) permite definir el rótulo vinculado a la imagen (corresponde al atributo HTML **alt** ).
* Al editar un correo electrónico, **Estilo** permite especificar el tamaño, el fondo y el borde de la imagen.
* Al editar una página de aterrizaje, **Dimensiones** permite especificar el tamaño de la imagen en píxeles.

El editor le permite trabajar con **todos los tipos** de imágenes cuyos formatos son compatibles con los navegadores. Para ser compatible con el editor, las animaciones **de tipo** &quot;Flash&quot; deben insertarse en una página HTML de la siguiente manera:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->
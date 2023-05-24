---
title: Trabajar con imágenes
description: Descubra cómo administrar imágenes en correos electrónicos con el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Trabajar con imágenes {#images}

## Inserción de imágenes{#inserting-images}

Puede insertar imágenes en los correos electrónicos y en las páginas de aterrizaje.

Los siguientes tipos de imágenes están disponibles, según la configuración:

* Imágenes locales
* Imágenes compartidas desde Adobe Experience Cloud: consulte [Uso de Campaign y del servicio principal de Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Imágenes dinámicas de Adobe Target: consulte [Uso de Campaign y Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Si decide agregar una imagen directamente editando la versión del correo electrónico del HTML, no debe llamar a **archivos externos en una etiqueta &lt;script>** de la página del HTML. Estos archivos no se importan en el servidor de Adobe Campaign.

### Inserción de imágenes en un correo electrónico {#inserting-images-in-an-email}

1. Añada un componente de estructura. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Agregar un componente de estructura. Dentro de este componente de estructura, agregue un componente de contenido **[!UICONTROL Image]**.

   ![](assets/des_insert_images_1.png)

1. Haga clic en **[!UICONTROL Browse]**. Arrastre y suelte una imagen o haga clic para seleccionar un archivo del equipo.

   ![](assets/des_insert_images_2.png)

1. Seleccione el componente de contenido que acaba de añadir.
1. Compruebe las propiedades de la imagen y ajústelas si es necesario.

   ![](assets/des_insert_images_3.png)

## Setting up image properties{#setting-up-image-properties}

Al seleccionar un bloque que contiene una imagen, se ofrecen las siguientes propiedades en la paleta:

* **Habilitar personalización** le permite personalizar el origen de la imagen. Ver [Personalización de un origen de imagen](../../designing/using/personalization.md#personalizing-an-image-source).
* **Image Title** le permite definir un título para la imagen.
* **Texto alternativo** (correo electrónico) o **Pie de ilustración** (página de aterrizaje) permite definir el pie de ilustración vinculado a la imagen (corresponde al atributo de HTML **alt**).
* Al editar un correo electrónico, **Estilo** le permite especificar el tamaño, el fondo y el borde de la imagen.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

El editor permite trabajar con **todos los tipos de imágenes** cuyos formatos son compatibles con los navegadores. Para ser compatible con el editor, las animaciones de tipo &quot;Flash&quot; **** deben insertarse en una página de HTML de la siguiente manera:

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

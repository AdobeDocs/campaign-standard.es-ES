---
title: Administración de imágenes en correos electrónicos
seo-title: Administración de imágenes en correos electrónicos
description: Administración de imágenes en correos electrónicos
seo-description: Descubra cómo administrar imágenes en correos electrónicos con el Diseñador de correo electrónico.
page-status-flag: nunca activado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: diseñar
content-type: referencia
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Imágenes {#images}

## Inserción de imágenes{#inserting-images}

Puede insertar imágenes en sus correos electrónicos y páginas de aterrizaje.

Los siguientes tipos de imágenes están disponibles según la configuración:

* Imágenes locales
* Imágenes compartidas desde Adobe Experience Cloud: consulte [Uso de Campaign y los recursos del servicio](../../integrating/using/working-with-campaign-and-assets-core-service.md) principal / Recursos On Demand
* Imágenes dinámicas de Adobe Target: consulte [Uso de Campaign y Target](../../integrating/using/about-campaign-target-integration.md)

Si está activada, puede modificar imágenes con el SDK de Adobe Creative. Consulte [Modificación de imágenes con el SDK](#modifying-images-with-the-adobe-creative-sdk)de Adobe Creative.

>[!CAUTION]
>
>Si decide agregar una imagen directamente editando la versión HTML del correo electrónico, no debe llamar a los archivos **externos en una etiqueta** &lt;script&gt; de la página HTML. Estos archivos no se importan en el servidor de Adobe Campaign.

### Inserción de imágenes en un correo electrónico {#inserting-images-in-an-email}

1. Agregue un componente de estructura. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.
1. Dentro de este componente de estructura, agregue un componente **[!UICONTROL Image]** de contenido.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. Arrastre y suelte una imagen o haga clic para seleccionar un archivo del equipo.

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

El editor le permite trabajar con **todos los tipos** de imágenes cuyos formatos son compatibles con los navegadores. Para ser compatible con el editor, las animaciones **de tipo** "Flash" deben insertarse en una página HTML de la siguiente manera:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

## Modificación de imágenes con el SDK de Adobe Creative{#modifying-images-with-the-adobe-creative-sdk}

Puede editar imágenes y utilizar un conjunto completo de funciones con tecnología Adobe Creative SDK para mejorar las imágenes directamente en el editor de contenido al editar correos electrónicos o páginas de aterrizaje.

El editor de imágenes ofrece un potente componente de interfaz de usuario de edición de imágenes con todas las funciones que le permite editar imágenes y aplicar efectos y marcos, etiquetas adhesivas originales de alta calidad, superposiciones hermosas, divertidas funciones como cambio de inclinación y bienvenida de color, ajustes de nivel profesional y mucho más.

Para modificar una imagen con el SDK de Adobe Creative:

1. Seleccione la imagen.
1. En la barra de herramientas, haga clic en el icono de Creative Cloud.

   ![](assets/des_creative_sdk_icon.png)

1. Seleccione la herramienta que desee utilizar mediante los iconos de la parte superior de la ventana para modificar la imagen.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Haga clic **[!UICONTROL Save]** cuando se hayan realizado las modificaciones. La imagen actualizada se guarda en el servidor de Adobe Campaign y está lista para utilizarse.

>[!NOTE]
Las herramientas ofrecidas en el editor de imágenes no se pueden personalizar.

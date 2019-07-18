---
title: Inserción de imágenes
seo-title: Inserción de imágenes
description: Inserción de imágenes
seo-description: Descubra cómo añadir imágenes al contenido.
page-status-flag: no activado nunca
uuid: ac 42 b 1 d 3-50 ad -4323-b 474-1 e 50 e 468901 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: uso de imágenes
discoiquuid: ede 832 ac -96 e 5-41 e 1-8390-6669 ba 30 d 4 d 8
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Inserting images{#inserting-images}

Puede insertar imágenes en sus correos electrónicos y páginas de aterrizaje.

Los siguientes tipos de imágenes están disponibles según la configuración:

* Imágenes locales
* Images shared from Adobe Experience Cloud - refer to [Working with Campaign and Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamic images from Adobe Target - refer to [Working with Campaign and Target](../../integrating/using/about-campaign-target-integration.md)

Si está habilitado, puede modificar imágenes con el SDK de Adobe Creative. See [Modifying images with the Adobe Creative SDK](../../designing/using/modifying-images-with-the-adobe-creative-sdk.md).

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script&gt; tag** of the HTML page. Estos archivos no se importarán al servidor de Adobe Campaign.

## Inserting images in an email {#inserting-images-in-an-email}

1. Agregue un componente de estructura. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inside this structure component, add an **[!UICONTROL Image]** content component.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. Arrastre y suelte una imagen o haga clic para seleccionar un archivo del equipo.

   ![](assets/des_insert_images_2.png)

1. Seleccione el componente de contenido que acaba de agregar.
1. Compruebe las propiedades de la imagen y ajuste las mismas si es necesario.

   ![](assets/des_insert_images_3.png)

## Inserting images in a landing page {#inserting-images-in-a-landing-page}

1. En un contenido de página de aterrizaje, seleccione un bloque que contenga una imagen.
1. Select the **[!UICONTROL Insert]** button.

   ![](assets/des_insert_images_lp_1.png)

1. Choose **[!UICONTROL Local image]** from the contextual toolbar.

   ![](assets/des_insert_images_lp_2.png)

1. Seleccione un archivo.

   ![](assets/des_insert_images_lp_3.png)

1. Ajuste las propiedades de la imagen según sea necesario.

   ![](assets/des_insert_images_lp_4.png)


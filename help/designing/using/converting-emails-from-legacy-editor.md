---
title: 'Conversión del correo electrónico del editor heredado al diseñador de correo electrónico '
description: Descubra cómo se utilizan los correos electrónicos creados en el correo electrónico del editor heredado al diseñador de correo electrónico.
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
source-git-commit: 1de0f5362f3c77fec4b66e330a2d2723f4a0f212

---


# Conversión del contenido de correo electrónico del editor heredado {#converting-an-html-content}

Inicio que trabaja con el Diseñador de correo electrónico y genera plantillas y fragmentos reutilizables a partir del HTML de correo electrónico creado en el Editor preexistente.

Este caso de uso permite crear una plantilla de diseñador de correo electrónico mediante un correo electrónico HTML y dividirla en componentes HTML en el Diseñador de correo electrónico.

>[!CAUTION]
>
>Esta sección está dirigida a usuarios avanzados familiarizados con el código HTML.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar una edición in-situ.

## Preparación del contenido del correo electrónico

1. Seleccione un correo electrónico HTML.
1. Identifique las secciones para dividir el correo electrónico HTML.
1. Corte los diferentes bloques del HTML.

## Crear la estructura de correo electrónico

1. Abra el **[!UICONTROL Email Designer]** para crear un contenido de correo electrónico vacío.
1. Defina los atributos de nivel de cuerpo: colores de fondo, anchura, etc. Para obtener más información sobre esto, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.
1. Añada tantos componentes de estructura como secciones. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.

## Añadir contenido HTML

1. Añada un componente HTML a cada componente de estructura. Para obtener más información sobre esto, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie y pegue el HTML en todos los componentes.

## Administrar el estilo del correo electrónico {#manage-the-style-of-your-email}

1. Cambie a **[!UICONTROL Mobile view]**. Para obtener más información, consulte [esta sección](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

1. Para solucionarlo, cambie al modo de código fuente y copie y pegue la sección de estilo en una nueva sección de estilo. Por ejemplo:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Asegúrese de agregar el estilo después de esto en otra etiqueta de estilo personalizada.
   >
   >No modifique la CSS generada por el Diseñador de correo electrónico:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Go back to the mobile view to check that your content is correctly displayed and save your changes.

## Caso de uso

Intentemos convertir este correo electrónico, creado en el editor heredado, en una **[!UICONTROL Email Designer]** plantilla.

## Identify the section of your email

We can identify 11 sections in this email.

![](assets/html-dce-view-mail.png)

To identify which element is which section of the HTML, you can select it.

![](assets/breadcrumbs.png)

To see the HTML version of the email, click **[!UICONTROL Show source]**.

### Create the email template and its structure

1. Drag and drop **[!UICONTROL Structure Components]**  reflecting the layout of our email.

We need to create 11 structure components.

![](assets/structure-components-migration.png)

### Inserción de componentes de contenido HTML

1. Insert an **[!UICONTROL HTML component]**  in each **[!UICONTROL structure component]** .

![](assets/html-components.png)

1. For each section, click **[!UICONTROL Show source code]** .

![](assets/show-source-code.png)

1. Inserte la sección HTML.

1. Haga clic **[!UICONTROL Save]**.

You can now check the rendering of your email.

![](assets/migrated-email-result.png)

### Administración de estilos para adaptarse a la vista móvil

Inserte elementos CSS para garantizar que el correo electrónico sea adecuado para la vista móvil.

1. Cambie al código fuente y copie y pegue la sección de estilo en una nueva sección de estilo.

Para obtener más información sobre esto, consulte [Administrar el estilo de su correo electrónico](#manage-the-style-of-your-email).

El correo electrónico heredado ya está disponible en el Diseñador de correo electrónico.
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 8%

---


# Conversión del contenido de correo electrónico del editor heredado {#converting-an-html-content}

Inicio que trabaja con el Diseñador de correo electrónico y genera plantillas y fragmentos reutilizables a partir del HTML de correo electrónico creado en el Editor preexistente.

Este caso de uso permite crear una plantilla de diseñador de correo electrónico mediante un correo electrónico HTML y dividirla en componentes HTML en el Diseñador de correo electrónico.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar una edición in-situ.

>[!IMPORTANT]
>
>Esta sección está dirigida a usuarios avanzados familiarizados con el código HTML.

## Preparación del contenido del correo electrónico

1. Seleccione un correo electrónico HTML.
1. Identifique las secciones para dividir el correo electrónico HTML.
1. Corte los diferentes bloques del HTML.

## Crear la estructura de correo electrónico

1. Abra el **[!UICONTROL Email Designer]** para crear un contenido de correo electrónico vacío.
1. Defina los atributos de nivel de cuerpo: colores de fondo, anchura, etc. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).
1. Añada tantos componentes de estructura como secciones. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Añadir contenido HTML

1. Añada un componente HTML a cada componente de estructura. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
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


1. Vuelva a la vista móvil para comprobar que el contenido se muestra correctamente y guarde los cambios.

## Ejemplo de uso

Intentemos convertir este correo electrónico, creado en el editor heredado, en una **[!UICONTROL Email Designer]** plantilla.

### Identifique la sección de su correo electrónico

Podemos identificar 11 secciones en este correo electrónico.

![](assets/html-dce-view-mail.png)

Para identificar qué elemento es qué sección del HTML, puede seleccionarlo.

![](assets/breadcrumbs.png)

Para ver la versión HTML del correo electrónico, haga clic en **[!UICONTROL Show source]**.

### Crear la plantilla de correo electrónico y su estructura

1. Arrastre y suelte **[!UICONTROL Structure components]** según el diseño de nuestro correo electrónico.

1. Repita tantas veces como sea necesario. Necesitamos crear 11 componentes de estructura.

   ![](assets/structure-components-migration.png)

### Inserción de componentes de contenido HTML

1. Inserte un **[!UICONTROL HTML component]** en cada **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Para cada sección, haga clic en **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Inserte la sección HTML.

1. Haga clic en **[!UICONTROL Save]**.

Ahora puede comprobar la representación del correo electrónico.

![](assets/migrated-email-result.png)

### Administración de estilos para adaptarse a la vista móvil

1. Inserte elementos CSS para garantizar que el correo electrónico sea adecuado para la vista móvil.

1. Cambie al código fuente y copie y pegue la sección de estilo en una nueva sección de estilo.

Para obtener más información sobre esto, consulte [Administrar el estilo de su correo electrónico](#manage-the-style-of-your-email).

El correo electrónico heredado ya está disponible en el Diseñador de correo electrónico.
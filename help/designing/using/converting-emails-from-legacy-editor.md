---
title: 'Conversión del correo electrónico del Editor heredado al Diseñador de correo electrónico '
description: Descubra cómo utilizar los correos electrónicos creados en el correo electrónico del Editor heredado al Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 8%

---

# Conversión del contenido de correo electrónico del editor heredado {#converting-an-html-content}

Empiece a trabajar con el Diseñador de correo electrónico y cree plantillas y fragmentos reutilizables a partir del HTML de correo electrónico creado en el Editor heredado.

Este caso de uso permite crear una plantilla de Diseñador de correo electrónico utilizando un correo electrónico de HTML y dividiéndola en componentes de HTML en el Diseñador de correo electrónico.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar la edición in situ.

>[!IMPORTANT]
>
>Esta sección está dirigida a usuarios avanzados familiarizados con el código de HTML.

## Preparación del contenido del correo electrónico

1. Seleccione un correo electrónico del HTML.
1. Identifique secciones para dividir el correo electrónico del HTML.
1. Corte los diferentes bloques de su HTML.

## Cree su estructura de correo electrónico

1. Abra el **[!UICONTROL Email Designer]**  para crear un contenido de correo electrónico vacío.
1. Establezca los atributos de nivel de cuerpo: colores de fondo, anchura, etc. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).
1. Añada tantos componentes de estructura como secciones. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Añadir contenido del HTML

1. Agregue un componente HTML a cada componente de estructura. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie y pegue el HTML en cada componente.

## Administrar el estilo del correo electrónico {#manage-the-style-of-your-email}

1. Cambie a **[!UICONTROL Mobile view]**. Para obtener más información, consulte [esta sección](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

1. Para solucionarlo, cambie al modo de código fuente y copie y pegue la sección de estilos en una nueva sección de estilos. Por ejemplo:

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


1. Vuelva a la vista móvil para comprobar que el contenido se muestra correctamente y guardar los cambios.

## Caso de uso

Intentemos convertir este correo electrónico, creado en el editor heredado, en un **[!UICONTROL Email Designer]** plantilla.

### Identifique la sección del correo electrónico

Podemos identificar 11 secciones en este correo electrónico.

![](assets/html-dce-view-mail.png)

Para identificar qué elemento es qué sección del HTML, puede seleccionarlo.

![](assets/breadcrumbs.png)

Para ver la versión del HTML del correo electrónico, haga clic en **[!UICONTROL Show source]**.

### Creación de la plantilla de correo electrónico y su estructura

1. Arrastrar y soltar **[!UICONTROL Structure components]**  reflejando el diseño de nuestro correo electrónico.

1. Repita tantas veces como sea necesario. Necesitamos crear 11 componentes de estructura.

   ![](assets/structure-components-migration.png)

### Inserción de componentes de contenido del HTML

1. Insertar un **[!UICONTROL HTML component]**  en cada **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Para cada sección, haga clic en **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Inserte la sección del HTML.

1. Haga clic en **[!UICONTROL Save]**.

Ahora puede comprobar la renderización del correo electrónico.

![](assets/migrated-email-result.png)

### Administración de estilos para ajustarse a la vista móvil

1. Inserte elementos CSS para garantizar que el correo electrónico sea adecuado para la vista móvil.

1. Cambie al código fuente y copie y pegue la sección de estilos en una nueva sección de estilos.

Para obtener más información, consulte [Administrar el estilo del correo electrónico](#manage-the-style-of-your-email).

El correo electrónico heredado ya está disponible en el Diseñador de correo electrónico.

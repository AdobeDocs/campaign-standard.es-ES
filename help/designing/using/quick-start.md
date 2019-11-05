---
title: Diseño de contenido de correo electrónico de inicio rápido
description: Empiece a crear contenido de correo electrónico con el Diseñador de correo electrónico.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---

# Diseño de contenido de correo electrónico de inicio rápido{#quick-start}

El Diseñador de correo electrónico proporciona cuatro formas de crear correos electrónicos.

Puede crear un mensaje de correo electrónico que comience de nuevo:

* Puede crear un correo electrónico a partir de un lienzo en blanco agregando fácilmente componentes de estructura y contenido y personalizando su contenido para enviar una entrega rápidamente. También puede administrar completamente los elementos de estilo. Para obtener más información, [comience rápidamente](#from-scratch-email) o consulte la documentación [](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)completa.

* Puede crear un mensaje de correo electrónico a partir de plantillas integradas seleccionando una plantilla y generando su nuevo contenido de correo electrónico desde aquí. [Más información](#building-content-from-an-out-of-the-box-template)

También puede crear un correo electrónico con contenido existente:

* Puede convertir un contenido HTML existente (creado externamente o en el editor heredado). [Más información](#converting-an-html-content)
* Puede importar de inmediato un contenido HTML existente en modo de compatibilidad. [Más información](#compatibility-mode)

## Sin contenido existente {#without-existing-content}

### Creación de un correo electrónico desde cero {#from-scratch-email}

Puede crear un correo electrónico fácilmente, agregar componentes y personalizar su contenido para enviar una entrega rápidamente. Si es necesario, puede adaptar las opciones de estilo al contenido. Para obtener más información sobre la administración de ajustes de estilo y atributos integrados, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

### Adición de una línea de asunto {#add-a-subject-line}

Las líneas de asunto son obligatorias al enviar un correo electrónico. Para obtener más información, consulte [Definición de la línea de asunto de un correo electrónico](../../designing/using/subject-line.md).

1. Cree un correo electrónico.
1. Cierre la página principal.
1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (accesible mediante el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

![](assets/subject-line-quick-start.png)

### Adición de componentes de estructura {#add-structure-components}

Los componentes de estructura definirán el diseño del correo electrónico. Para obtener más información, consulte [Definición de la estructura de un correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

En Componentes de estructura, arrastre y suelte los componentes del diseño que desee utilizar.

>[!NOTE]
>
>Puede seleccionar diferentes diseños de contenido que se añadirán a su correo electrónico.

![](assets/structure-components-quick-start.png)

### Adición de componentes de contenido {#add-content-components}

Puede agregar varios componentes de contenido al correo electrónico, como imágenes, texto y botones. Para obtener más información, consulte Componentes [de contenido](../../designing/using/designing-from-scratch.md#about-content-components).

* Imagen

1. En Componentes **** de contenido, arrastre y suelte la imagen en uno de los componentes de estructura.
1. Haga clic en **Examinar**.
1. Seleccione el archivo de imagen del equipo.

![](assets/browse-image-quick-start.png)

* Texto con personalización

1. En Componentes **** de contenido, arrastre y suelte el texto en uno de los componentes de estructura.
1. Haga clic en el componente e introduzca el texto.
1. Para agregar un campo de personalización, haga clic en **Insertar campo** de personalización en la barra de herramientas.
1. Seleccione el campo que necesita, como Nombre.

![](assets/edit-text-quick-start.png)

* HTML

1. En Componentes **** de contenido, arrastre y suelte HTML en uno de los componentes de estructura.
1. Haga clic en **Mostrar el código** fuente.
1. Escriba el contenido HTML.
1. Haga clic en **Save**.

![](assets/html-component-source-code.png)

Si está familiarizado con HTML, puede copiar y pegar el código HTML del pie de página original mediante el componente de **[!UICONTROL Html]** contenido. Para obtener más información sobre esto, consulte [Acerca de los componentes](../../designing/using/designing-from-scratch.md#about-content-components)de contenido.

![](assets/des_loading_compatible_fragment_9.png)

### Estilo del componente de correo electrónico

Puede ajustar el estilo del correo electrónico, por ejemplo, cambiando el relleno de un componente. Para obtener más información sobre la administración de ajustes de estilo y atributos integrados, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

1. Haga clic en el componente **** Texto.
1. A la derecha, en la paleta, vaya a **Relleno**.
1. Haga clic en el icono de bloqueo para romper la sincronización entre los parámetros superior e inferior o derecho e izquierdo.
1. Ajuste el **relleno** según sea necesario.
1. Haga clic en **Save**.

![](assets/padding-quick-start.png)

Ahora puede guardar y enviar su correo electrónico.

### Creación de contenido a partir de una plantilla lista para usar {#building-content-from-an-out-of-the-box-template}

Puede crear un correo electrónico a partir de plantillas integradas, como mensajes de bienvenida de clientes, newsletters y correos electrónicos de recontratación, y personalizarlos.

1. Cree un correo electrónico y abra su contenido. Para obtener más información sobre esto, consulte [Creación de un correo electrónico](../../channels/using/creating-an-email.md).
1. Haga clic en el icono de inicio para acceder a la página **[!UICONTROL Email Designer]** principal.
1. Haga clic en la **[!UICONTROL Templates]** ficha.
1. Elija una plantilla HTML lista para usar.
Las distintas plantillas presentan varias combinaciones de varios tipos de elementos. Por ejemplo, las plantillas 'Calado' tienen márgenes mientras que las plantillas 'Astro' no tienen uno. Para obtener más información sobre esto, consulte Plantillas [de contenido](../../designing/using/using-reusable-content.md#content-templates).
1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (accesible mediante el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.
1. Puede combinar estos elementos para crear una serie de variantes de correo electrónico. Por ejemplo, puede duplicar una sección de correo electrónico seleccionando un componente de estructura y haciendo clic en **[!UICONTROL Duplicate]** en la barra de herramientas contextual.
1. Puede mover los elementos mediante la flecha azul a la izquierda para arrastrar un componente de estructura por debajo o por encima de otro. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.
1. También puede mover componentes para cambiar la organización de cada elemento de estructura. Para obtener más información sobre esto, consulte [Adición de fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Modifique el contenido de cada elemento según sus necesidades: imágenes, texto, vínculos.
1. Adapte las opciones de estilo al contenido si es necesario. Para obtener más información sobre esto, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

## Con contenido existente {#with-existing-content}

Si desea crear un marco de plantillas modulares y fragmentos que se puedan combinar para reutilizarlos en varios correos electrónicos, debe considerar la posibilidad de convertir el HTML de correo electrónico en una plantilla de Email Designer.

### Conversión de contenido HTML {#converting-an-html-content}

Este caso de uso ofrece una forma rápida de convertir un correo electrónico HTML en componentes de Email Designer.

>[!CAUTION]
>
>Esta sección está dirigida a usuarios familiarizados con el código HTML.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar una edición in-situ.

Fuera del Diseñador de correo electrónico, asegúrese de que el HTML original se divide en secciones reutilizables.

1. Abra el Diseñador de correo electrónico para crear un contenido de correo electrónico vacío.
1. Defina los atributos de nivel de cuerpo: colores de fondo, anchura, etc. Para obtener más información sobre esto, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

Si este no es el caso, elimine los diferentes bloques del HTML. Por ejemplo, aquí se muestra una sección claramente identificada:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Una vez identificados todos los bloques, en el Diseñador de correo electrónico, repita el siguiente procedimiento para cada sección del correo electrónico existente:

1. Agregue un componente de estructura. Para obtener más información sobre esto, consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.
1. Agregue un componente HTML. Para obtener más información sobre esto, consulte [Adición de fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie y pegue el HTML en ese componente.
1. Cambie a la vista móvil. For more on this, see [this section](../../designing/using/styles.md#switching-to-mobile-view).

   La vista interactiva está dañada, ya que falta la CSS.

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


1. Vuelva a la vista de dispositivos móviles para comprobar que el contenido se muestra correctamente y guardar los cambios.

### Importación y edición de un correo electrónico HTML {#compatibility-mode}

Al cargar un contenido, debe contener etiquetas específicas para que sea totalmente compatible y editable con el editor WYSIWYG del Diseñador de correo electrónico.

Si todo o parte del HTML cargado no es compatible con el etiquetado esperado, el contenido se carga en 'modo de compatibilidad', lo que limita las posibilidades de edición a través de la interfaz de usuario.

Cuando se carga un contenido en modo de compatibilidad, aún puede realizar las siguientes modificaciones a través de la interfaz (las acciones no disponibles están ocultas):

* Cambio del texto o cambio de una imagen
* Inserción de vínculos y campos de personalización
* Editar algunas opciones de estilo en el bloque HTML seleccionado
* Definición de contenido condicional

![](assets/email_designer_compatibility.png)

Otras modificaciones, como la adición de nuevas secciones al correo electrónico o el estilo avanzado, deben realizarse directamente en el código fuente del correo electrónico a través del modo HTML.
Aunque el modo de compatibilidad no permite utilizar arrastrar y soltar, garantiza el mismo conjunto de funciones que el editor heredado.

Para obtener más información sobre la conversión de un correo electrónico existente en un correo electrónico compatible con el Diseñador de correo electrónico, consulte [esta sección](../../designing/using/using-existing-content.md).

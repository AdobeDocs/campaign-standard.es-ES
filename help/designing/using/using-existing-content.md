---
solution: Campaign Standard
product: campaign
title: 'Diseño de correos electrónicos con contenido existente '
description: Descubra cómo diseñar correos electrónicos con contenido de correo electrónico existente en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Diseño de correo electrónico
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 6%

---

# Diseño con contenido existente {#designing-using-existing-content}

## Selección de contenido existente{#selecting-an-existing-content}

Adobe Campaign incluye un conjunto de contenidos predefinidos para ayudarle a empezar. Puede utilizar uno de estos elementos o, si el contenido del mensaje que debe enviar se está preparando fuera de Adobe Campaign, puede importarlo desde su equipo o desde una dirección URL.

Al crear un correo electrónico o una página de aterrizaje, puede elegir cargar un contenido existente de otro origen.

>[!NOTE]
>
>Las imágenes siguientes muestran cómo cargar un contenido existente mediante el [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md).

1. Después de crear el correo electrónico o la página de aterrizaje, abra su contenido.
1. Haga clic en el icono de inicio para acceder a la página de inicio **[!UICONTROL Email Designer]**.

   ![](assets/des_loading_1.png)

1. Seleccione el origen del contenido que desea cargar:

   * [Plantillas](../../designing/using/using-reusable-content.md#content-templates) de contenido: haga clic en la  **[!UICONTROL Templates]** pestaña .
   * [Contenido desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), para empezar de nuevo: haga clic en el  **[!UICONTROL Create]** botón .
   * [Contenido del equipo como archivo](#importing-content-from-a-file) ZIP o HTML: haga clic en el  **[!UICONTROL Upload]** botón .
   * [Contenido de una URL existente](#importing-content-from-a-url)  (solo para correos electrónicos): haga clic en el  **[!UICONTROL Import from URL]** botón .

   ![](assets/des_loading_2.png)

1. Cargue el contenido. El contenido seleccionado reemplaza al contenido actual.

   Una vez importado, el contenido se puede editar y personalizar.

   >[!NOTE]
   >
   >El [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) utiliza etiquetado específico. El contenido HTML estándar cargado en Campaign debe coincidir con el etiquetado esperado para que sea totalmente compatible y editable desde el Diseñador de correo electrónico. Si no coincide, el contenido se carga en [modo de compatibilidad](#compatibility-mode). Para hacer compatible el contenido existente, consulte [esta sección](#editing-existing-contents-with-the-email-designer).

**Temas relacionados:**

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Administración de páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)

## Edición de contenido existente con el Diseñador de correo electrónico{#editing-existing-contents-with-the-email-designer}

Para aprovechar al máximo las posibilidades de edición del [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md), el HTML cargado debe contener etiquetas específicas que lo hagan compatible con el editor WYSIWYG.

Si todo o parte del HTML no tiene este etiquetado, el contenido se carga en el [modo de compatibilidad](#compatibility-mode)&#39;.

Para que un contenido externo existente se pueda editar completamente dentro del Diseñador de correo electrónico, consulte la sección [Diseño de un correo electrónico con contenido existente](../../designing/using/using-existing-content.md) .

## Importación de contenido de correo electrónico existente {#importing}

### Importación de contenido desde un archivo {#importing-content-from-a-file}

En la página de inicio del Diseñador de correo electrónico, haga clic en el botón **[!UICONTROL Upload]** para cargar un archivo desde el equipo y, a continuación, confirme la carga.

No hay restricciones en la estructura del archivo zip. Sin embargo, la referencia a los archivos HTML debe ser relativa y respetar la estructura de árbol de la carpeta zip.

Se admiten los siguientes formatos para la importación:

* Un archivo HTML con una hoja de estilo incorporada
* Carpeta .zip que contiene el archivo HTML, la hoja de estilos (.CSS) y las imágenes

>[!NOTE]
>
>Para el contenido del correo electrónico, se recomienda importar archivos HTML únicos con una hoja de estilo incorporada.

#### Importación de contenido desde una dirección URL {#importing-content-from-a-url}

Antes de importar contenido desde una dirección URL, asegúrese de que cumple los requisitos siguientes:

* El contenido debe estar disponible públicamente a través de esta URL.
* Por motivos de seguridad, solo se permiten las direcciones URL que comienzan por **[!UICONTROL https]**.
* Asegúrese de que todos los recursos (imágenes, CSS) estén configurados en vínculos absolutos y en HTTPS. De lo contrario, después de enviar el correo electrónico, la página espejo se mostraría sin sus recursos. A continuación, se muestra un ejemplo de una definición de vínculo absoluto:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>La carga de contenido desde una dirección URL solo está disponible para el canal de correo electrónico.

Para recuperar contenido existente de una URL, siga los pasos a continuación:

1. En la página de inicio del Diseñador de correo electrónico, seleccione el botón **[!UICONTROL Import from URL]**.

   ![](assets/email_designer_importfromurl.png)

1. Defina la dirección URL desde la que se recuperará el contenido.
1. Haga clic en **[!UICONTROL Confirm]**.

Descubra esta función en vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Hay disponibles más vídeos prácticos del Campaign Standard [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).

### Recuperación de contenido de una URL automáticamente en tiempo de preparación {#retrieving-content-from-a-url-automatically-at-preparation-time}

La importación de contenido desde una URL durante la preparación del mensaje le permite recuperar el contenido HTML más reciente cada vez que se prepara el correo electrónico. De este modo, el contenido de los correos electrónicos recurrentes siempre está actualizado en el momento de su envío. Esta función también le permite crear un mensaje programado para una fecha específica, incluso aunque el contenido no esté listo todavía.

Para recuperar contenido en el momento de la preparación, siga los pasos a continuación:

1. Seleccione la opción **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. El contenido de la URL se muestra en el editor como de solo lectura.

   >[!CAUTION]
   >
   >En este paso, no se debe tener en cuenta la visualización HTML en el editor de contenido. Se recuperará en la fase de preparación.

1. Para obtener una vista previa del contenido de la URL que se ha recuperado, abra el mensaje una vez que se haya creado y haga clic en el botón **[!UICONTROL Preview]** .

Es posible personalizar la dirección URL remota desde la que se recupera el contenido. Para realizar esto, siga los pasos a continuación:

1. Haga clic en la etiqueta de correo electrónico en la parte superior de la pantalla para acceder a la pestaña Diseñador de correo electrónico **[!UICONTROL Properties]** .
1. Busque el campo **[!UICONTROL Remote URL]** .

   ![](assets/email_designer_importfromurl4.png)

1. Inserte el campo de personalización, el bloque de contenido o el texto dinámico que desee.

   El bloque de contenido **[!UICONTROL Current date - YYYYMMDD]**, por ejemplo, permite insertar la fecha del día.

   >[!NOTE]
   >
   >Los campos de personalización disponibles están vinculados únicamente a atributos **Delivery** (fecha de creación del correo electrónico, estado, etiqueta de campaña...).

### Modo de compatibilidad {#compatibility-mode}

Al cargar un contenido, debe contener etiquetas específicas para que sea totalmente compatible y editable con el editor WYSIWYG del Diseñador de correo electrónico.

Si todo o parte del HTML cargado no cumple con el etiquetado esperado, el contenido se carga en &#39;modo de compatibilidad&#39;, lo que limita las posibilidades de edición a través de la interfaz de usuario.

Cuando se carga un contenido en modo de compatibilidad, aún puede realizar las siguientes modificaciones a través de la interfaz (las acciones no disponibles están ocultas):

* Cambiar el texto o cambiar una imagen
* Inserción de vínculos y campos personalizados
* Editar algunas opciones de estilo en el bloque HTML seleccionado
* Definición de contenido condicional

![](assets/email_designer_compatibility.png)

Otras modificaciones, como la adición de nuevas secciones al correo electrónico o el estilo avanzado, deben realizarse directamente en el código fuente del correo electrónico a través del modo HTML.

Para obtener más información sobre la conversión de un correo electrónico existente en un correo electrónico compatible con el Diseñador de correo electrónico, consulte [esta sección](../../designing/using/using-existing-content.md).

**Temas relacionados**:

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Vídeo de introducción al Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Diseño del contenido de un correo electrónico desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversión de contenido HTML {#converting-an-html-content}

Si desea crear un marco de plantillas modulares y fragmentos que se puedan combinar para reutilizar en varios correos electrónicos, debe considerar la conversión del HTML de correo electrónico en una plantilla de Diseñador de correo electrónico.

Este caso de uso ofrece una forma rápida de convertir el correo electrónico HTML en componentes del Diseñador de correo electrónico.

>[!CAUTION]
>
>Esta sección está dirigida a usuarios avanzados familiarizados con el código HTML.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar la edición in situ.

Fuera del Diseñador de correo electrónico, asegúrese de que el HTML original se divide en secciones reutilizables.

Si no es así, elimine los diferentes bloques del HTML. Por ejemplo:

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

1. Abra el Diseñador de correo electrónico para crear un contenido de correo electrónico vacío.
1. Establezca los atributos de nivel de cuerpo: colores de fondo, anchura, etc. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).
1. Añada un componente de estructura. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Añada un componente HTML. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie y pegue el HTML en ese componente.
1. Cambie a la vista móvil. Para obtener más información, consulte [esta sección](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   La vista interactiva está dañada porque falta el CSS.

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

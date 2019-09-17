---
title: Interfaz del editor de contenido de la página de aterrizaje
seo-title: Interfaz del editor de contenido de la página de aterrizaje
description: Interfaz del editor de contenido de la página de aterrizaje
seo-description: Aprenda a utilizar las diferentes secciones del editor, como la barra de acciones, para modificar el contenido de la página de aterrizaje.
page-status-flag: nunca activado
uuid: 53729a68-eed2-4c5d-bc14-02c80e897c44
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: diseñar
content-type: referencia
topic-tags: editing-landing-page-content
discoiquuid: 08e2bda-e409-467f-b462-d74256dc6ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# Interfaz del editor de contenido de la página de aterrizaje{#landing-page-content-editor-interface}

El editor de contenido de la página de aterrizaje permite definir, modificar y personalizar fácilmente el contenido en Adobe Campaign. Para acceder a él, haga clic en el **[!UICONTROL Content]** bloque de un tablero de página de aterrizaje.

El editor de contenido está organizado en tres secciones diferentes. Estas secciones le permiten ver y editar el contenido.

![](assets/des_lp_content_8.png)

1. La **paleta** de la parte izquierda de la pantalla permite modificar las opciones generales vinculadas a un bloque seleccionado. Las opciones que se pueden modificar son: color de fondo, borde, alineación de texto, condición de visibilidad, etc. Consulte [Inserción de un campo](../../designing/using/personalization.md#inserting-a-personalization-field)de personalización.
1. La barra de **acciones** contiene las opciones generales de la página. Puede seleccionar una plantilla y cambiar el modo de visualización. Consulte Barra de acciones [del editor de la página de aterrizaje](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. La zona **de** edición principal le permite interactuar directamente con el contenido mediante la barra de herramientas contextual: insertar un vínculo en una imagen, cambiar la fuente, eliminar un campo, etc. Consulte [Barra de herramientas](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar)del editor de la página de aterrizaje.

## Barra de acciones del editor de la página de aterrizaje {#landing-page-editor-action-bar}

La barra de acciones contiene diferentes botones que le permiten interactuar con el contenido que se está creando.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icono<br /> </th> 
   <th> Nombre del botón<br /> </th> 
   <th> Canal<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambiar contenido</span><br /> </td> 
   <td> Página de aterrizaje y correo electrónico<br /> </td> 
   <td> Le permite seleccionar contenido listo para usar o importar su propio contenido HTML. Consulte <a href="../../designing/using/using-existing-content.md">Carga de contenido</a>existente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Deshacer</span><br /> </td> 
   <td> Todos<br /> </td> 
   <td> Cancela la última acción realizada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rehacer</span><br /> </td> 
   <td> Todos<br /> </td> 
   <td> Rehace la última acción que canceló.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar bloques</span><br /> </td> 
   <td> Página de aterrizaje y correo electrónico<br /> </td> 
   <td> Permite mostrar los cuadros alrededor de los bloques de contenido (corresponde a la etiqueta <strong>&lt;div&gt;</strong> HTML).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar origen</span><br /> </td> 
   <td> Página de aterrizaje y correo electrónico<br /> </td> 
   <td> Permite mostrar el código fuente HTML de la página.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Barra de herramientas del editor de la página de aterrizaje {#landing-page-editor-toolbar}

La barra de herramientas es un elemento **** contextual de la interfaz del editor que ofrece diversas funcionalidades en función de la zona seleccionada. Contiene botones de acción y botones que le permiten cambiar el estilo del texto. Las modificaciones realizadas se aplican siempre a la zona seleccionada. Una vez seleccionado un bloque, puede eliminarlo o duplicarlo, por ejemplo. Después de seleccionar el texto dentro de un bloque, puede convertirlo en un vínculo o ponerlo en negrita.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Algunas funciones de la barra de herramientas permiten dar formato al contenido HTML. Sin embargo, si la página contiene una hoja de estilo CSS, las **instrucciones** de la hoja de estilo pueden tener **prioridad** sobre las instrucciones especificadas mediante la barra de herramientas.

<table> 
 <thead> 
  <tr> 
   <th> Icono<br /> </th> 
   <th> Nombre del botón<br /> </th> 
   <th> Contexto<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Vínculo a una dirección URL</span> externa <br /> </td> 
   <td> Cualquier elemento<br /> </td> 
   <td> Permite agregar un vínculo a una dirección URL. Los detalles de cómo configurar un vínculo se presentan en la sección <a href="../../designing/using/links.md#inserting-a-link">Insertar un vínculo</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Vínculo a una página</span> de aterrizaje <br /> </td> 
   <td> Cualquier elemento<br /> </td> 
   <td> Permite acceder a una página de aterrizaje de Adobe Campaign. Los detalles de cómo configurar un vínculo se presentan en la sección <a href="../../designing/using/links.md#inserting-a-link">Insertar un vínculo</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Vínculo</span> de suscripción <br /> </td> 
   <td> Cualquier elemento<br /> </td> 
   <td> Permite insertar un vínculo de suscripción al servicio. Los detalles de cómo configurar un vínculo se presentan en la sección <a href="../../designing/using/links.md#inserting-a-link">Insertar un vínculo</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Vínculo</span> de cancelación de suscripción <br /> </td> 
   <td> Cualquier elemento<br /> </td> 
   <td> Le permite insertar un vínculo de cancelación de suscripción a un servicio. Los detalles de cómo configurar un vínculo se presentan en la sección <a href="../../designing/using/links.md#inserting-a-link">Insertar un vínculo</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Eliminar vínculo</span><br /> </td> 
   <td> Vínculo<br /> </td> 
   <td> Permite eliminar el vínculo, así como todas las configuraciones vinculadas a él, después de confirmarlo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insertar un campo</span> de personalización <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite agregar un campo de la base de datos al contenido. Consulte <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Inserción de un campo</a>de personalización.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insertar un bloque</span> de contenido <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite agregar un bloque de personalización al contenido. Consulte <a href="../../designing/using/personalization.md#adding-a-content-block">Adición de un bloque</a>de contenido.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Habilitar contenido</span> dinámico <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite insertar contenido dinámico en el contenido. Consulte <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">Definición de contenido</a>dinámico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Deshabilitar contenido</span> dinámico <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite eliminar contenido dinámico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ampliar fuente</span><br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Aumenta el tamaño del texto seleccionado (agrega <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Reducir fuente</span><br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Reduce el tamaño del texto seleccionado (agrega <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Negrita</span><br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Agrega el estilo de negrita al texto seleccionado (ajusta el texto con las etiquetas <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cursiva</span><br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Agrega el estilo en cursiva al texto seleccionado (ajusta el texto con las etiquetas <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Subrayado</span><br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Subraya el texto seleccionado (ajusta el texto seleccionado con la <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambiar color</span> de fondo <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite cambiar el color de fondo del bloque seleccionado (agrega style="background-color: rgba(170, 86, 255, 0,87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambiar color</span> de fuente <br /> </td> 
   <td> Elemento Texto<br /> </td> 
   <td> Permite cambiar el color de todo el texto del bloque o solo el texto seleccionado en el bloque (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Imagen</span><br /> </td> 
   <td> Bloque que contiene una imagen<br /> </td> 
   <td> Permite insertar una imagen de un archivo guardado localmente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Eliminar</span><br /> </td> 
   <td> Cualquier bloque<br /> </td> 
   <td> Elimina el bloque y su contenido.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplicar</span><br /> </td> 
   <td> Cualquier bloque<br /> </td> 
   <td> Duplica el bloque, incluidos los estilos vinculados a él.<br /> </td> 
  </tr> 
 </tbody> 
</table>


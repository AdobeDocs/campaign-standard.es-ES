---
solution: Campaign Standard
product: campaign
title: Administración de estilos de correo electrónico
description: Descubra cómo administrar estilos de correo electrónico en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 1%

---


# Administración de estilos de correo electrónico {#managing-styles}


En el Diseñador de correo electrónico, al seleccionar un elemento, se muestran varias opciones específicas del tipo de contenido seleccionado en el panel **[!UICONTROL Settings]**. Puede utilizar estas opciones para cambiar fácilmente el estilo del correo electrónico.

## Selección de un elemento {#selecting-an-element}

Para seleccionar un elemento en la interfaz del Diseñador de correo electrónico, puede:

* haga clic directamente en el correo electrónico,
* o busque el árbol de estructura disponible en las opciones ubicadas en la **Paleta** izquierda.

![](assets/des_tree_structure.png)

Al navegar por el árbol de estructura, puede realizar una selección más precisa. Puede seleccionar:

* todo el componente de estructura,
* una de las columnas que componen el componente de estructura,
* o solo un componente ubicado dentro de una columna.

![](assets/des_tree_structure_selection.png)

Para seleccionar una columna, también puede hacer lo siguiente:

1. Seleccione un componente de estructura (directamente en el correo electrónico o mediante el árbol de estructura disponible en la **Paleta** de la izquierda).
1. En la **barra de herramientas contextual**, haga clic en **[!UICONTROL Select a column]** para elegir la columna deseada.

Consulte un ejemplo en [esta sección](#example--adjusting-vertical-alignment-and-padding).

## Ajuste de la configuración de estilo {#adjusting-style-settings}

1. Seleccione un elemento en el correo electrónico. Para obtener más información, consulte [Selección de un elemento](#selecting-an-element).
1. Ajuste la configuración según sus necesidades. Cada elemento seleccionado ofrece un conjunto diferente de configuraciones.

   Puede insertar fondos, cambiar tamaños, modificar alineación horizontal o vertical, administrar colores, agregar [margen o margen](#selecting-an-element), etc.

   Para ello, utilice las opciones mostradas en el panel **[!UICONTROL Settings]** o [añadir atributos de estilo en línea](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Guarde el contenido.

## Ajuste del margen y margen {#about-padding-and-margin}

La interfaz del Diseñador de correo electrónico le permite ajustar rápidamente el relleno y los márgenes.

**[!UICONTROL Padding]**: esta configuración permite administrar el espacio que se encuentra dentro del borde de un elemento.

![](assets/des_padding.png)

Por ejemplo:

* Utilice el relleno para establecer los márgenes en los lados izquierdo y derecho de una imagen.
* Utilice el relleno superior e inferior para añadir más espaciado a un componente **[!UICONTROL Text]** o **[!UICONTROL Divider]**.
* Para definir los bordes entre columnas dentro de un elemento de estructura, defina el relleno para cada columna.

**[!UICONTROL Margin]**: esta configuración le permite administrar el espacio entre el borde del elemento y el siguiente elemento.

![](assets/des_margin.png)

>[!NOTE]
>
>Según la selección (componente de estructura, columna o componente de contenido), el resultado no será el mismo. Adobe recomienda configurar los parámetros **[!UICONTROL Padding]** y **[!UICONTROL Margin]** en el nivel de columna.

Para **[!UICONTROL Padding]** y **[!UICONTROL Margin]**, haga clic en el icono de candado para romper la sincronización entre los parámetros superior e inferior o derecho e izquierdo. Esto le permite ajustar cada parámetro por separado.

![](assets/des_padding_lock_icon.png)

## Alineación de estilo {#about-alignment}

* **Alineación** de texto: coloque el cursor del ratón sobre algún texto y utilice la barra de herramientas contextual para alinearlo.

   ![](assets/des_text_alignment.png)

* **La** alineación horizontal se puede aplicar a texto, imágenes y botones; actualmente, no a los componentes  **[!UICONTROL Divider]** y  **[!UICONTROL Social]** .

   ![](assets/des_horizontal_alignment.png)

* Para establecer **alineación vertical**, seleccione una columna dentro de un componente de estructura y elija una opción en el panel Configuración.

   ![](assets/des_set_vertical_alignment.png)

## Configuración de fondos {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Configuración de fondo"
>abstract="El Diseñador de correo electrónico le permite personalizar el color de fondo o la imagen de fondo del contenido. Tenga en cuenta que los clientes de correo electrónico no admiten la imagen de fondo."
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="Información adicional"

En cuanto a la configuración de fondos con el Diseñador de correo electrónico, Adobe recomienda lo siguiente:

1. Aplique un color de fondo al cuerpo del correo electrónico si lo requiere el diseño.
1. En la mayoría de los casos, defina los colores de fondo en el nivel de columna.
1. Intente no utilizar colores de fondo en componentes de imagen o texto, ya que son difíciles de administrar.

A continuación se muestran los ajustes de fondo disponibles que puede utilizar.

* Establezca un **[!UICONTROL Background color]** para todo el correo electrónico. Asegúrese de seleccionar la configuración de cuerpo en el árbol de navegación accesible desde la paleta izquierda.

   ![](assets/des_background_body.png)

* Para definir el mismo color de fondo para todos los componentes de estructura, seleccione **[!UICONTROL Viewport background color]**. Esta opción le permite seleccionar una configuración diferente del color de fondo.

   ![](assets/des_background_viewport.png)

* Defina un color de fondo diferente para cada componente de estructura. Seleccione una estructura del árbol de navegación accesible desde la paleta izquierda para aplicar un color de fondo específico solo a esa estructura.

   ![](assets/des_background_structure.png)

   Asegúrese de no establecer un color de fondo de ventanilla móvil, ya que podría ocultar los colores de fondo de la estructura.

* Establezca un **[!UICONTROL Background image]** para el contenido de un componente de estructura.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Algunos programas de correo electrónico no admiten imágenes de fondo. Cuando no se admita, se utilizará el color de fondo de fila. Asegúrese de seleccionar un color de fondo alternativo adecuado en caso de que la imagen no se pueda mostrar.

* Establezca un color de fondo en el nivel de columna.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Este es el caso de uso más común. Adobe recomienda configurar los colores de fondo en el nivel de columna, ya que esto permite una mayor flexibilidad al editar todo el contenido del correo electrónico.

   También puede establecer una imagen de fondo en el nivel de columna, pero esto no se suele utilizar.

### Ejemplo: ajuste de la alineación vertical y el margen {#example--adjusting-vertical-alignment-and-padding}

Desea ajustar el margen y la alineación vertical dentro de un componente de estructura compuesto por tres columnas. Para realizar esto, siga los pasos a continuación:

1. Seleccione el componente de estructura directamente en el correo electrónico o utilice el árbol de estructura disponible en la **Paleta** izquierda.
1. En la **barra de herramientas contextual**, haga clic en **[!UICONTROL Select a column]** y elija la que desea editar. También puede seleccionarlo en el árbol de estructura.

   ![](assets/des_selecting_column.png)

   Los parámetros editables para esa columna se muestran en el panel **[!UICONTROL Settings]** de la derecha.

1. En **[!UICONTROL Vertical alignment]**, seleccione **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   El componente de contenido se muestra encima de la columna .

1. En **[!UICONTROL Padding]**, defina el relleno superior dentro de la columna. Haga clic en el icono de candado para romper la sincronización con el relleno inferior.

   Defina el relleno izquierdo y derecho para esa columna.

   ![](assets/des_adjusting_padding.png)

1. Proceda de forma similar para ajustar la alineación y el relleno de las demás columnas.

   ![](assets/des_adjusting_columns.png)

1. Guarde los cambios.

## Diseño de vínculos {#about-styling-links}

Puede subrayar un vínculo y seleccionar su color y destino en el Diseñador de correo electrónico.

1. En un componente en el que se inserta un vínculo, seleccione el texto de la etiqueta del vínculo.

1. En la configuración del componente, marque **[!UICONTROL Underline link]** para subrayar el texto de la etiqueta del vínculo.

   ![](assets/stylelinks-selecttext.png)

1. Para seleccionar en qué contexto de navegación se abrirá el enlace, seleccione un **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Para cambiar el color del vínculo, haga clic en **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Elija el color que necesite.

   ![](assets/stylelinks-colorchanged.png)

1. Guarde los cambios.

## Adición de atributos de estilo en línea {#adding-inline-styling-attributes}

En la interfaz del Diseñador de correo electrónico, al seleccionar un elemento y mostrar su configuración en el panel lateral, puede personalizar los atributos en línea y su valor para ese elemento específico.

1. Seleccione un elemento en el contenido.
1. En el panel lateral, busque la configuración **[!UICONTROL Styles Inline]**.

   ![](assets/email_designer_inlineattributes.png)

1. Modifique los valores de los atributos existentes o agregue otros nuevos con el botón **+**. Puede añadir cualquier atributo y valor que sea compatible con CSS.

A continuación, el estilo se aplica al elemento seleccionado. Si los elementos secundarios no tienen atributos de estilo específicos definidos, se hereda el estilo del elemento principal.

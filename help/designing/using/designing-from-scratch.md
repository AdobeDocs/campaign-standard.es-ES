---
solution: Campaign Standard
product: campaign
title: 'Diseño de correos electrónicos desde cero '
description: Descubra cómo diseñar correos electrónicos desde cero en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 2d28048590b52b81f27cd1cfe10be029bbc35197
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 2%

---


# Diseño de correos electrónicos desde cero {#designing-an-email-content-from-scratch}

Aprenda a dominar la edición de contenido de correo electrónico. Con Email Designer, puede crear correos electrónicos y plantillas empezando o sin su propio contenido predefinido.

A continuación se indican los pasos principales para crear y diseñar contenido de correo electrónico desde cero con el Diseñador de correo electrónico:

1. Cree un correo electrónico y abra su contenido.
1. Añada componentes de estructura para dar forma al correo electrónico. Consulte [Edición de la estructura de correo electrónico](#defining-the-email-structure).
1. Inserte componentes y fragmentos de contenido en los componentes de estructura. Consulte [Añadir fragmentos y componentes de contenido](#defining-the-email-structure).
1. Añada imágenes y edite el texto del correo electrónico. Consulte [Inserción de imágenes](../../designing/using/images.md#inserting-images).
1. Personalice su correo electrónico agregando campos de personalización, vínculos, etc. Consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field), [Inserción de un vínculo](../../designing/using/links.md#inserting-a-link) y [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Defina la línea de asunto de su correo electrónico. Consulte [Personalización de la línea de asunto de un correo electrónico](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Previsualización del correo electrónico.
1. Guarde el contenido y continúe con el mensaje después de asegurarse de haber definido una audiencia y programado correctamente el envío.

También puede ver este [vídeo de introducción](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=spa).

>[!NOTE]
>
>Para evitar el diseño del contenido del correo electrónico desde cero, puede utilizar plantillas de contenido integradas. Para obtener más información sobre esto, consulte [Plantillas de contenido](../../designing/using/using-reusable-content.md#content-templates).

## Definición de la estructura de correo electrónico {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Acerca de los componentes de estructura"
>abstract="Los componentes de estructura definen el diseño del correo electrónico."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definición de columnas de correo electrónico"
>abstract="El Diseñador de correo electrónico permite definir fácilmente el diseño del correo electrónico definiendo la estructura de columnas."

El Diseñador de correo electrónico permite definir fácilmente la estructura del correo electrónico. Al agregar y mover elementos estructurales con simples acciones de arrastrar y soltar, puede diseñar la forma del correo electrónico en cuestión de segundos.

Para editar la estructura de un correo electrónico:

1. Abra un contenido existente o cree un nuevo contenido de correo electrónico.
1. Acceda a **[!UICONTROL Structure components]** seleccionando el icono **+** de la izquierda.

   ![](assets/email_designer_structure.png)

1. Arrastre y suelte los componentes de estructura que necesita para dar forma al correo electrónico.

   ![](assets/email_designer_structure_components.png)

   Una línea azul materializa la ubicación exacta de los componentes de la estructura antes de soltarla. Puede colocarlo encima, entre o debajo de cualquier otro componente, pero no dentro.

   >[!NOTE]
   >
   >Tenga en cuenta que la pila de columnas no es compatible con todos los programas de correo electrónico. Cuando no se admiten, las columnas no se apilarán.
   >
   >Una vez colocados en el correo electrónico, no podrá mover ni eliminar los componentes a menos que ya haya un componente de contenido o un fragmento dentro del mismo.

1. Hay disponibles varios componentes de estructura compuestos por una o más columnas.

   Seleccione el componente **[!UICONTROL n:n column]** para definir el número de columnas que desee (entre 3 y 10). También puede definir el ancho de cada columna moviendo las flechas en la parte inferior de cada columna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamaño de columna no puede ser inferior al 10 % del ancho total del componente de estructura. No se puede quitar una columna que no esté vacía.

Una vez definida la estructura, podrá añadir fragmentos de contenido y componentes al correo electrónico.

## Uso de un preencabezado {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Uso de un preencabezado"
>abstract="El encabezado previo le permite configurar un texto de resumen corto que ofrece una tasa de apertura más alta para el correo electrónico."

El encabezado previo es un breve texto de resumen que sigue la línea del asunto al ver un correo electrónico desde la bandeja de entrada. El preencabezado ofrece una velocidad de apertura más alta.

Seleccione el cuadro de edición **[!UICONTROL Preheader]** y complete el contenido.

![](assets/email_designer_preheader.png)

Puede agregar un **[!UICONTROL Content block]**, un **[!UICONTROL Dynamic content]** o un **[!UICONTROL Personalization fields]** en el contenido del encabezado previo.

>[!NOTE]
>
>Tenga en cuenta que preheader no es compatible con todos los programas de correo electrónico. Cuando no se admite, no se mostrará el encabezado previo.

## Uso de componentes de contenido {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Acerca de los componentes de contenido"
>abstract="Los componentes de contenido son marcadores de posición de contenido vacíos que se pueden editar para crear un correo electrónico."

Los componentes de contenido son componentes sin procesar y vacíos que se pueden editar una vez colocados en un mensaje de correo electrónico.

Puede agregar tantos componentes de contenido como desee en un componente de estructura. También puede moverlos dentro del componente de estructura o a otro componente de estructura.

Esta es la lista de los componentes disponibles en el Diseñador de correo electrónico:

### **[!UICONTROL Button]**

Si necesita utilizar varios botones, en lugar de editarlos desde cero, puede crear un duplicado del componente **[!UICONTROL Button]** mediante la barra de herramientas contextual.

También puede guardar botones en fragmentos que se puedan reutilizar. Para obtener más información sobre esto, consulte [Creación de un fragmento de contenido](../../designing/using/using-reusable-content.md#creating-a-content-fragment) y [Almacenamiento de contenido como fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Seleccione **[!UICONTROL Fallback view]** para mostrar la imagen de reserva en el Diseñador de correo electrónico.

### **[!UICONTROL Text]**

Utilice este componente para insertar texto en el correo electrónico. Puede ajustar el color, el estilo y el tamaño del texto en **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Utilice este componente para insertar una línea divisoria en el correo electrónico. Puede seleccionar el color, estilo y tamaño de la línea de salto en **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Utilice este componente para copiar y pegar las diferentes partes del HTML existente. Esto le permite crear componentes HTML modulares gratuitos.

>[!NOTE]
>
>Un componente HTML gratuito se puede editar con opciones limitadas. Si no se han alineado todos los estilos, asegúrese de agregar la CSS adecuada en la sección **head** del código HTML; de lo contrario, el correo electrónico no responderá. Utilice el botón **[!UICONTROL Preview]** para probar la capacidad de respuesta del contenido (consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md)).

Para que un contenido externo sea compatible con el Diseñador de correo electrónico, Adobe recomienda crear un mensaje desde cero y copiar el contenido del correo electrónico existente en fragmentos y componentes.

Cuando tenga contenido que no se pueda volver a crear, puede copiar y pegar el código HTML del correo electrónico original mediante el componente de contenido **[!UICONTROL Html]**. Asegúrese de que está familiarizado con HTML antes de continuar.

>[!NOTE]
>
>El nuevo contenido no será la copia exacta de su correo electrónico original, pero los pasos a continuación le guiarán a través de la creación de un mensaje que será lo más cercano posible.

**Antes de copiar el contenido**

1. En el correo electrónico original, identifique las secciones reutilizables de las secciones que serán exclusivas de cada correo electrónico que envíe.
1. Guarde todas las imágenes y recursos que desee utilizar.
1. Si está familiarizado con HTML, divida el contenido HTML original en diferentes partes.

### Video {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Configuración de vídeo"
>abstract="Utilice este componente para insertar un vídeo en el correo electrónico. Tenga en cuenta que los vídeos no funcionan en todos los clientes de correo electrónico. Se recomienda configurar una imagen de reserva."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Información adicional"

Inserte el componente de vídeo en un componente de estructura del correo electrónico e introduzca el vínculo de vídeo en el **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Tenga en cuenta que el vídeo no es compatible con todos los programas de correo electrónico. Cuando no se admite, se mostrará la opción de reserva.

### Imagen

Utilice este componente para insertar una imagen en el correo electrónico.

Inserte el componente de imagen en un componente de estructura y haga clic en Examinar para cargar un archivo de imagen desde el equipo.

### **[!UICONTROL Social]**

Utilice este componente para insertar vínculos a páginas de medios sociales en el correo electrónico. Puede seleccionar los vínculos que desea mostrar y el tamaño de su icono en **[!UICONTROL Component Settings]**.

### Carrusel {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Configuración de carrusel"
>abstract="Obtenga información sobre cómo insertar y configurar un carrusel en el contenido.Tenga en cuenta que el carrusel no funciona en todos los clientes de correo electrónico y que se mostrará la imagen de reserva en caso de que no sea compatible."

1. Arrastre y suelte el componente **[!UICONTROL Carousel]** dentro de un componente de estructura.
1. Busque para seleccionar imágenes del equipo.

   ![](assets/des_carousel_browse.png)

1. En el panel **[!UICONTROL Settings]**, establezca el número de miniaturas que desee en el carrusel.
1. Seleccione una imagen de reserva del equipo.

   ![](assets/des_carousel_fallback.png)

El componente carrusel no es compatible con todos los programas de correo electrónico. Cargue una alternativa para mostrar una imagen en su lugar cuando el carrusel no sea compatible con el correo electrónico.

>[!NOTE]
>
>El componente carrusel es compatible con las siguientes plataformas de correo electrónico: Apple Mail 7, Apple Mail 8, Outlook 2011 para Mac, Outlook 2016 para Mac, Mozilla Thunderbird, iPad y iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox y Safari).

**Temas relacionados**:

- [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
- [Selección de una audiencia en un mensaje](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Programación de mensajes](../../sending/using/about-scheduling-messages.md)
- [Vista previa de mensajes](../../sending/using/previewing-messages.md)
- [Procesamiento de correo electrónico](../../sending/using/email-rendering.md)

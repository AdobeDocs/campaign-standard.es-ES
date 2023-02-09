---
title: Diseño de correos electrónicos desde cero
description: Descubra cómo diseñar correos electrónicos desde cero contenido de correo electrónico en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 7%

---

# Diseño de correos electrónicos desde cero {#designing-an-email-content-from-scratch}

Aprenda a dominar la edición del contenido del correo electrónico. Con el Diseñador de correo electrónico, puede crear correos electrónicos y plantillas que comiencen por o sin su propio contenido predefinido.

Estos son los pasos principales para crear y diseñar un contenido de correo electrónico desde cero mediante el Diseñador de correo electrónico:

1. Cree un correo electrónico y abra su contenido.
1. Añada componentes de estructura para dar forma al correo electrónico. Consulte [Edición de la estructura de correo electrónico](#defining-the-email-structure).
1. Inserte componentes de contenido y fragmentos en los componentes de estructura. Consulte [Adición de fragmentos y componentes de contenido](#defining-the-email-structure).
1. Añada imágenes y edite el texto del correo electrónico. Consulte [Inserción de imágenes](../../designing/using/images.md#inserting-images).
1. Personalice el correo electrónico agregando campos de personalización, vínculos, etc. Consulte [Inserción de un campo personalizado](../../designing/using/personalization.md#inserting-a-personalization-field), [Inserción de un vínculo](../../designing/using/links.md#inserting-a-link) y [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Defina la línea de asunto del correo electrónico. Consulte [Personalización de la línea de asunto de un correo electrónico](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Previsualización del correo electrónico.
1. Guarde el contenido y continúe con el mensaje después de asegurarse de que ha definido una audiencia y ha programado la entrega correctamente.

También puede consultar esta [vídeo introductorio](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>Para evitar diseñar contenido de correo electrónico desde cero, puede usar plantillas de contenido predeterminadas. Para obtener más información, consulte [Plantillas de contenido](../../designing/using/using-reusable-content.md#content-templates).

## Definición de la estructura de correo electrónico {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Acerca de los componentes de estructura"
>abstract="Los componentes de estructura definen el diseño del correo electrónico."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definición de columnas de correo electrónico"
>abstract="El Diseñador de correo electrónico permite definir fácilmente el diseño del correo electrónico definiendo la estructura de columnas."

El Diseñador de correo electrónico le permite definir fácilmente la estructura del correo electrónico. Al agregar y mover elementos estructurales con simples acciones de arrastrar y soltar, puede diseñar la forma de su correo electrónico en cuestión de segundos.

Para editar la estructura de un correo electrónico:

1. Abra un contenido existente o cree un nuevo contenido de correo electrónico.
1. Acceda a la **[!UICONTROL Structure components]** seleccionando **+** a la izquierda.

   ![](assets/email_designer_structure.png)

1. Arrastre y suelte los componentes de estructura que necesita para dar forma al correo electrónico.

   ![](assets/email_designer_structure_components.png)

   Una línea azul materializa la ubicación exacta de los componentes de estructura antes de soltarla. Puede soltarlo encima, entre o debajo de cualquier otro componente, pero no dentro.

   >[!NOTE]
   >
   >Tenga en cuenta que la pila de columnas no es compatible con todos los programas de correo electrónico. Cuando no se admite, las columnas no se apilan.
   >
   >Una vez colocados en el correo electrónico, no puede mover ni eliminar los componentes a menos que ya haya un componente de contenido o un fragmento colocado en él.

1. Hay disponibles varios componentes de estructura compuestos por una o más columnas.

   Seleccione el **[!UICONTROL n:n column]** para definir el número de columnas que elija (entre 3 y 10). También puede definir el ancho de cada columna moviendo las flechas en la parte inferior de cada columna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamaño de columna no puede ser inferior al 10 % de la anchura total del componente de estructura. No se puede quitar una columna que no esté vacía.

Una vez definida la estructura, puede añadir fragmentos de contenido y componentes al correo electrónico.

## Uso de un encabezado previo {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Uso de un encabezado previo"
>abstract="El encabezado previo le permite configurar un breve texto de resumen que ofrece una mayor tasa de apertura para su correo electrónico."

Un encabezado previo es un breve texto de resumen que sigue la línea del asunto cuando se visualiza un correo electrónico desde la bandeja de entrada. El encabezado previo ofrece una tasa de apertura más alta.

Seleccione el **[!UICONTROL Preheader]** cuadro de edición y complete el contenido.

![](assets/email_designer_preheader.png)

Puede añadir un **[!UICONTROL Content block]**, **[!UICONTROL Dynamic content]** o **[!UICONTROL Personalization fields]** en el contenido del encabezado previo.

>[!NOTE]
>
>Tenga en cuenta que el preencabezado no es compatible con todos los programas de correo electrónico. Cuando no se admite, no se muestra.

## Uso de componentes de contenido {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Acerca de los componentes de contenido"
>abstract="Los componentes de contenido son marcadores de posición de contenido vacíos que se pueden editar para crear un correo electrónico."

Los componentes de contenido son componentes sin procesar y vacíos que se pueden editar una vez colocados en un correo electrónico.

Puede añadir tantos componentes de contenido como desee en un componente de estructura. También puede moverlas dentro del componente de estructura o a otro componente de estructura.

Esta es la lista de los componentes disponibles en el Diseñador de correo electrónico:

### **[!UICONTROL Button]**

Si necesita utilizar varios botones, en lugar de editarlos desde cero, puede duplicar el **[!UICONTROL Button]** utilizando la barra de herramientas contextual.

También puede guardar botones en fragmentos que se puedan reutilizar. Para obtener más información, consulte [Creación de un fragmento de contenido](../../designing/using/using-reusable-content.md#creating-a-content-fragment) y [Guardado de contenido como fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Select **[!UICONTROL Fallback view]** para mostrar la imagen de reserva en el Diseñador de correo electrónico.

### **[!UICONTROL Text]**

Utilice este componente para insertar texto en el correo electrónico. Puede ajustar el color, el estilo y el tamaño del texto en **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Utilice este componente para insertar una línea divisoria en el correo electrónico. Puede seleccionar el color, el estilo y el tamaño de la línea de salto en **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Utilice este componente para copiar y pegar las diferentes partes del HTML existente. Esto le permite crear componentes de HTML modulares gratuitos.

>[!NOTE]
>
>Un componente HTML libre es editable con opciones limitadas. Si todos los estilos no están alineados, asegúrese de agregar la CSS adecuada en la **head** del código del HTML; de lo contrario, el correo electrónico no responderá. Utilice la variable **[!UICONTROL Preview]** para probar la capacidad de respuesta del contenido (consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md)).

Para hacer que un contenido externo sea compatible con el Diseñador de correo electrónico, Adobe recomienda crear un mensaje desde cero y copiar el contenido del correo electrónico existente en fragmentos y componentes.

Cuando tenga un contenido que no se pueda recrear, puede copiar y pegar el código del HTML del correo electrónico original con el **[!UICONTROL Html]** componente de contenido. Asegúrese de estar familiarizado con el HTML antes de continuar.

>[!NOTE]
>
>El nuevo contenido no será la copia exacta del correo electrónico original, pero los pasos a continuación le guiarán a través de la creación de un mensaje lo más cercano posible.

**Antes de copiar el contenido**

1. En el correo electrónico original, identifique las secciones reutilizables de las secciones que serán únicas para cada correo electrónico que enviará.
1. Guarde todas las imágenes y recursos que desee utilizar.
1. Si está familiarizado con el HTML, divida el contenido original del HTML en diferentes partes.

### Vídeo {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Configuración de vídeo"
>abstract="Utilice este componente para insertar un vídeo en el correo electrónico. Tenga en cuenta que los vídeos no funcionan en todos los clientes de correo electrónico. Se recomienda configurar una imagen de reserva."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Información adicional"

Inserte el componente de vídeo en un componente de estructura de su correo electrónico e introduzca el vínculo de vídeo en el **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Tenga en cuenta que el vídeo no es compatible con todos los programas de correo electrónico. Cuando no se admite, se muestra la reserva.

### Imagen

Utilice este componente para insertar una imagen en el correo electrónico.

Inserte el componente de imagen en un componente de estructura y haga clic en Examinar para cargar un archivo de imagen desde el equipo.

### **[!UICONTROL Social]**

Utilice este componente para insertar vínculos a páginas de medios sociales en el correo electrónico. Puede seleccionar qué vínculos desea mostrar y el tamaño de su icono en **[!UICONTROL Component Settings]**.

### Carrusel {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Configuración de carrusel"
>abstract="Obtenga información sobre cómo insertar y configurar un carrusel en el contenido. Tenga en cuenta que el carrusel no funciona en todos los clientes de correo electrónico y que la imagen de reserva se mostrará en caso de que no sea compatible."

1. Arrastre y suelte la **[!UICONTROL Carousel]** dentro de un componente de estructura.
1. Busque para seleccionar imágenes del equipo.

   ![](assets/des_carousel_browse.png)

1. En el **[!UICONTROL Settings]** , establezca el número de miniaturas que desee en el carrusel.
1. Seleccione una imagen de reserva del equipo.

   ![](assets/des_carousel_fallback.png)

El componente carrusel no es compatible con todos los programas de correo electrónico. Cargue una alternativa para mostrar una imagen cuando el carrusel no sea compatible con el correo electrónico.

>[!NOTE]
>
>El componente carrusel es compatible con las siguientes plataformas de correo electrónico: Apple Mail 7, Apple Mail 8, Outlook 2011 para Mac, Outlook 2016 para Mac, Mozilla Thunderbird, iPad y iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox y Safari).

**Temas relacionados**:

- [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
- [Selección de una audiencia en un mensaje](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Programación de mensajes](../../sending/using/about-scheduling-messages.md)
- [Vista previa de mensajes](../../sending/using/previewing-messages.md)
- [Procesamiento de correo electrónico](../../sending/using/email-rendering.md)

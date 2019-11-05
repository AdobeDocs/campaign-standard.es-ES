---
title: 'Diseño de correos electrónicos desde cero '
description: Descubra cómo diseñar correos electrónicos desde cero en el Diseñador de correo electrónico.
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


# Diseño de correos electrónicos desde cero {#designing-an-email-content-from-scratch}

Aprenda a dominar la edición de contenido de correo electrónico. Con Email Designer, puede crear correos electrónicos y plantillas empezando o sin su propio contenido predefinido.

## Pasos clave para crear el correo electrónico {#key-steps-to-create-your-email}

A continuación se indican los pasos principales para crear y diseñar contenido de correo electrónico desde cero con el Diseñador de correo electrónico:

1. Cree un correo electrónico y abra su contenido.
1. Agregue componentes de estructura para dar forma al correo electrónico. Consulte [Edición de la estructura](#defining-the-email-structure)de correo electrónico.
1. Inserte componentes y fragmentos de contenido en los componentes de estructura. Consulte [Adición de fragmentos y componentes](#defining-the-email-structure)de contenido.
1. Agregue imágenes y edite el texto del correo electrónico. Consulte [Inserción de imágenes](../../designing/using/images.md#inserting-images).
1. Personalice su correo electrónico agregando campos de personalización, vínculos, etc. Consulte [Inserción de un campo](../../designing/using/personalization.md#inserting-a-personalization-field)de personalización, [Inserción de un vínculo](../../designing/using/links.md#inserting-a-link) y [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Defina la línea de asunto de su correo electrónico. See [Personalizing the subject line of an email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Previsualice el correo electrónico.
1. Guarde el contenido y continúe con el mensaje después de asegurarse de haber definido una audiencia y de haber programado correctamente el envío.

También puede ver este vídeo [de introducción](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=spa).

>[!NOTE]
>
>Para evitar el diseño del contenido del correo electrónico desde cero, puede utilizar plantillas de contenido integradas. Para obtener más información sobre esto, consulte Plantillas [de contenido](../../designing/using/using-reusable-content.md#content-templates).

### Definición de la estructura de correo electrónico {#defining-the-email-structure}

El Diseñador de correo electrónico permite definir fácilmente la estructura del correo electrónico. Al agregar y mover elementos estructurales con simples acciones de arrastrar y soltar, puede diseñar la forma del correo electrónico en cuestión de segundos.

Para editar la estructura de un correo electrónico:

1. Abra un contenido existente o cree un nuevo contenido de correo electrónico.
1. Para acceder al **[!UICONTROL Structure components]** , seleccione el icono **+** de la izquierda.

   ![](assets/email_designer_structure.png)

1. Arrastre y suelte los componentes de estructura que necesita para dar forma al correo electrónico.

   ![](assets/email_designer_structure_components.png)

   Una línea azul materializa la ubicación exacta de los componentes de la estructura antes de soltarla. Puede colocarlo encima, entre o debajo de cualquier otro componente, pero no dentro.

   >[!NOTE]
   >
   >Una vez colocados en el correo electrónico, no podrá mover ni eliminar los componentes a menos que ya haya un componente de contenido o un fragmento dentro del mismo.

1. Hay disponibles varios componentes de estructura compuestos por una o más columnas.

   Seleccione el **[!UICONTROL n:n column]** componente para definir el número de columnas que desee (entre 3 y 10). También puede definir el ancho de cada columna moviendo las flechas en la parte inferior de cada columna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamaño de columna no puede ser inferior al 10 % del ancho total del componente de estructura. No puede eliminar una columna que no esté vacía.

Una vez definida la estructura, podrá añadir fragmentos de contenido y componentes al correo electrónico.

### Uso de componentes de contenido {#about-content-components}

 Los componentes de contenido son componentes sin procesar y vacíos que se pueden editar una vez colocados en un mensaje de correo electrónico.

Puede agregar tantos componentes de contenido como desee en un componente de estructura. También puede moverlos dentro del componente de estructura o a otro componente de estructura.

Esta es la lista de los componentes disponibles en el Diseñador de correo electrónico:

- **[!UICONTROL Button]**

   Si necesita utilizar varios botones, en lugar de editarlos desde cero, puede duplicar el **[!UICONTROL Button]** componente mediante la barra de herramientas contextual.

   También puede guardar botones en fragmentos que se puedan reutilizar. Para obtener más información sobre esto, consulte [Creación de un fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment) de contenido y [Guardado de contenido como un fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

1. Seleccione **[!UICONTROL Fallback view]** para mostrar la imagen de reserva en el Diseñador de correo electrónico.

- **[!UICONTROL Text]**

   Utilice este componente para insertar texto en el correo electrónico. Puede ajustar el color, el estilo y el tamaño del texto en **[!UICONTROL Component Settings]**.

- **[!UICONTROL Divider]**

   Utilice este componente para insertar una línea divisoria en el correo electrónico. Puede seleccionar el color, el estilo y el tamaño de la línea de salto en **[!UICONTROL Component Settings]**.

- **[!UICONTROL Html]**

   Utilice este componente para copiar y pegar las diferentes partes del HTML existente. Esto le permite crear componentes HTML modulares gratuitos.

   >[!NOTE]
   >
   >Un componente HTML gratuito se puede editar con opciones limitadas. Si no se han alineado todos los estilos, asegúrese de agregar la CSS adecuada en la sección **head** del código HTML; de lo contrario, el correo electrónico no responderá. Utilice el **[!UICONTROL Preview]** botón para probar la capacidad de respuesta del contenido (consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md)).

   Para que un contenido externo sea compatible con el Diseñador de correo electrónico, Adobe recomienda crear un mensaje desde cero y copiar el contenido del correo electrónico existente en fragmentos y componentes.

   Si tiene contenido que no se puede volver a crear, puede copiar y pegar el código HTML del correo electrónico original mediante el componente de contenido **[!UICONTROL Html]** . Asegúrese de que está familiarizado con HTML antes de continuar.

   <!-- A full example is presented below. -->

   >[!NOTE]
   >
   >El nuevo contenido no será la copia exacta de su correo electrónico original, pero los pasos a continuación le guiarán a través de la creación de un mensaje que será lo más cercano posible.

   **Antes de copiar el contenido**

   1. En el correo electrónico original, identifique las secciones reutilizables de las secciones que serán únicas para cada correo electrónico que envíe.
   1. Guarde todas las imágenes y recursos que desee utilizar.
   1. Si está familiarizado con HTML, divida el contenido HTML original en diferentes partes.

- **[!UICONTROL Video]**

   Utilice este componente para insertar un vídeo en el correo electrónico.

   Inserte el componente de vídeo en un componente de estructura del correo electrónico e introduzca el vínculo de vídeo en el **[!UICONTROL Component Settings]**.

- **[!UICONTROL Image]**

   Utilice este componente para insertar una imagen en el correo electrónico.

   Inserte el componente de imagen en un componente de estructura y haga clic en Examinar para cargar un archivo de imagen desde el equipo.

- **[!UICONTROL Social]**

   Utilice este componente para insertar vínculos a páginas de medios sociales en el correo electrónico. Puede seleccionar los vínculos que desea mostrar y el tamaño del icono en **[!UICONTROL Component Settings]**.

- **[!UICONTROL Carousel]**

   1. Arrastre y suelte el **[!UICONTROL Carousel]** componente dentro de un componente de estructura.
   1. Busque para seleccionar imágenes del equipo.
   ![](assets/des_carousel_browse.png)

   1. En el **[!UICONTROL Settings]** panel, establezca el número de miniaturas que desee en el carrusel.
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

---
solution: Campaign Standard
product: campaign
title: Introducción al Diseñador de correo electrónico
description: Empiece a crear contenido de correo electrónico con el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Diseño de correo electrónico
role: User
level: Beginner
exl-id: 47f53290-2190-4181-bcd5-e60287189c41
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 6%

---

# Introducción al Diseñador de correo electrónico {#quick-start}

El Diseñador de correo electrónico proporciona cuatro formas de crear correos electrónicos.

Puede crear un correo electrónico [que comience de nuevo en el Diseñador de correo electrónico](#without-existing-content):

1. Puede **crear un correo electrónico a partir de un lienzo en blanco** añadiendo fácilmente componentes de estructura y contenido y personalizando su contenido para realizar un envío rápidamente. También puede administrar completamente los elementos de estilo. Para obtener más información, [comience rápidamente](#from-scratch-email) o consulte la [documentación completa](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Puede **crear un correo electrónico a partir de una plantilla predeterminada** seleccionando una plantilla y creando su nuevo contenido de correo electrónico desde aquí. [Más información](#building-content-from-an-out-of-the-box-template)

También puede crear un correo electrónico [con contenido existente](#with-existing-content):

1. Puede **convertir un contenido HTML existente** (creado externamente o en el editor heredado). [Más información](#converting-an-html-content)
1. Puede **importar de inmediato un contenido HTML existente** en modo de compatibilidad. [Más información](#compatibility-mode)

| Sin contenido | Con contenido |
|---|---|
| [Creación de un correo electrónico desde cero](#from-scratch-email) | [Conversión de contenido HTML existente](#converting-an-html-content) |
| [Creación de contenido a partir de una plantilla predeterminada](#building-content-from-an-out-of-the-box-template) | [Importación de un HTML existente](#compatibility-mode) |

## Diseño de correos electrónicos con el editor {#without-existing-content}

>[!NOTE]
>
>En ambas estrategias de creación, es fundamental rellenar la línea de asunto antes de enviar el correo electrónico. Obtenga información sobre cómo [Agregar una línea de asunto](#add-a-subject-line).

### Creación de un correo electrónico desde cero {#from-scratch-email}

Puede crear un correo electrónico fácilmente, añadir componentes y personalizar su contenido para realizar una entrega rápidamente. Si es necesario, puede adaptar las opciones de estilo al contenido. Para obtener más información sobre la administración de la configuración de estilo y los atributos en línea, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).

1. Creación de un correo electrónico.
1. Cierre la página principal.

### Adición de una línea de asunto {#add-a-subject-line}

Las líneas de asunto son obligatorias al enviar un correo electrónico. Para obtener más información, consulte [Definición de la línea de asunto de un correo electrónico](../../designing/using/subject-line.md).

1. Vaya a la pestaña **[!UICONTROL Properties]** de la página de inicio del Diseñador de correo electrónico (accesible a través del icono de inicio) y rellene la sección **[!UICONTROL Subject]** .

![](assets/subject-line-quick-start.png)

### Adición de componentes de estructura {#add-structure-components}

Los componentes de estructura definirán el diseño del correo electrónico. Para obtener más información, consulte [Definición de la estructura de un correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

En Componentes de estructura, arrastre y suelte los componentes del diseño que desee utilizar.

>[!NOTE]
>
>Puede seleccionar diferentes diseños de contenido que se añadirán en el correo electrónico.

![](assets/structure-components-quick-start.png)

### Adición de componentes de contenido {#add-content-components}

Puede añadir varios componentes de contenido al correo electrónico, como imágenes, texto y botones. Para obtener más información, consulte [Componentes de contenido](../../designing/using/designing-from-scratch.md#about-content-components).

* **Imagen**

   1. En **Componentes de contenido**, arrastre y suelte la imagen en uno de los componentes de estructura.
   1. Haga clic en **Examinar**.
   1. Seleccione el archivo de imagen del equipo.

   ![](assets/browse-image-quick-start.png)

* **Texto con personalización**

   1. En **Componentes de contenido**, arrastre y suelte el texto en uno de los componentes de estructura.
   1. Haga clic en el componente e introduzca el texto.
   1. Para añadir un campo de personalización, haga clic en **Insert personalization field** en la barra de herramientas.
   1. Seleccione el campo que necesita, como Nombre.

   ![](assets/edit-text-quick-start.png)

* **HTML**

   1. En **Componentes de contenido**, arrastre y suelte HTML en uno de los componentes de estructura.
   1. Haga clic en **Show the source code**.
   1. Introduzca el contenido HTML.
   1. Haga clic en **Save**.

   ![](assets/html-component-source-code.png)

   Si está familiarizado con HTML, puede copiar y pegar el código HTML del pie de página original mediante el componente de contenido **[!UICONTROL Html]** . Para obtener más información, consulte [Acerca de los componentes de contenido](../../designing/using/designing-from-scratch.md#about-content-components).

   ![](assets/des_loading_compatible_fragment_9.png)

### Diseño del componente de correo electrónico

Puede ajustar el estilo del correo electrónico, por ejemplo, cambiando el relleno de un componente. Para obtener más información sobre la administración de la configuración de estilo y los atributos en línea, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).

1. Haga clic en su **Componente de texto**.
1. A la derecha, en la paleta, vaya a **Relleno**.
1. Haga clic en el icono de candado para romper la sincronización entre los parámetros superior e inferior o derecho e izquierdo.
1. Ajuste **Relleno** según sea necesario.
1. Haga clic en **Save**.

![](assets/padding-quick-start.png)

Ahora puede guardar y enviar su correo electrónico.

### Creación de contenido a partir de una plantilla predeterminada {#building-content-from-an-out-of-the-box-template}

Puede crear un correo electrónico a partir de plantillas predeterminadas, como mensajes de bienvenida del cliente, boletines informativos y correos electrónicos de renovación de la participación, y personalizarlos.

1. Cree un correo electrónico y abra su contenido. Para obtener más información, consulte [Creación de un correo electrónico](../../channels/using/creating-an-email.md).
1. Haga clic en el icono de inicio para acceder a la página de inicio **[!UICONTROL Email Designer]**.
1. Seleccione la pestaña **[!UICONTROL Templates]**.
1. Elija una plantilla HTML predeterminada.
Las distintas plantillas presentan varias combinaciones de varios tipos de elementos. Por ejemplo, las plantillas &quot;pluma&quot; tienen márgenes, mientras que las plantillas &quot;astro&quot; no tienen uno. Para obtener más información, consulte [Plantillas de contenido](../../designing/using/using-reusable-content.md#content-templates).
1. Vaya a la pestaña **[!UICONTROL Properties]** de la página de inicio del Diseñador de correo electrónico (accesible a través del icono de inicio) y rellene la sección **[!UICONTROL Subject]** .
1. Puede combinar estos elementos para crear una serie de variantes de correo electrónico. Por ejemplo, puede duplicar una sección de correo electrónico seleccionando un componente de estructura y haciendo clic en **[!UICONTROL Duplicate]** en la barra de herramientas contextual.
1. Puede mover los elementos mediante la flecha azul de la izquierda para arrastrar un componente de estructura por debajo o por encima de otro. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. También puede mover componentes para cambiar la organización de cada elemento de estructura. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Modifique el contenido de cada elemento según sus necesidades: imágenes, texto, vínculos.
1. Adapte las opciones de estilo al contenido si es necesario. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).

## Uso de contenido de correo electrónico existente {#with-existing-content}

Si desea crear un marco de plantillas modulares y fragmentos que se puedan combinar para reutilizar en varios correos electrónicos, debe considerar la conversión del HTML de correo electrónico en una plantilla de Diseñador de correo electrónico.

### Conversión de contenido HTML {#converting-an-html-content}

Este caso de uso ofrece una forma rápida de convertir el correo electrónico HTML en componentes del Diseñador de correo electrónico. Para obtener más información sobre este tema, consulte [Conversión de contenido HTML](../../designing/using/using-existing-content.md#converting-an-html-content).

>[!CAUTION]
>
>Esta sección es para usuarios familiarizados con el código HTML.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar la edición in situ.


### Importación y edición de un correo electrónico HTML {#compatibility-mode}

Al cargar un contenido, debe contener etiquetas específicas para que sea totalmente compatible y editable con el editor WYSIWYG del Diseñador de correo electrónico.

Para obtener más información sobre la conversión de un correo electrónico existente en un correo electrónico compatible con el Diseñador de correo electrónico, consulte [esta sección](../../designing/using/using-existing-content.md#compatibility-mode).

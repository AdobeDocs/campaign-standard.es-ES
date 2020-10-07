---
title: Introducción al Diseñador de correo electrónico
description: Inicio de creación de contenido de correo electrónico con el Diseñador de correo electrónico.
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
source-wordcount: '924'
ht-degree: 6%

---

# Introducción al Diseñador de correo electrónico {#quick-start}

El Diseñador de correo electrónico proporciona cuatro formas de crear correos electrónicos.

Puede crear un mensaje de correo electrónico [empezando por nuevo en Email Designer](#without-existing-content):

1. Puede **crear un correo electrónico desde un lienzo** en blanco agregando fácilmente componentes de estructura y contenido y personalizando su contenido para enviar un envío rápidamente. También puede administrar completamente los elementos de estilo. Para obtener más información, [comience rápidamente](#from-scratch-email) o consulte la documentación [](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)completa.

1. Puede **crear un correo electrónico a partir de una plantilla** lista para usar seleccionando una plantilla y generando el nuevo contenido de correo electrónico desde aquí. [Más información](#building-content-from-an-out-of-the-box-template)

También puede crear un correo electrónico [con contenido](#with-existing-content)existente:

1. Puede **convertir un contenido** HTML existente (creado externamente o en el editor heredado). [Más información](#converting-an-html-content)
1. Puede **importar inmediatamente un contenido** HTML existente en modo de compatibilidad. [Más información](#compatibility-mode)

| Sin contenido | Con contenido |
|---|---|
| [Creación de un correo electrónico desde cero](#from-scratch-email) | [Conversión de un contenido HTML existente](#converting-an-html-content) |
| [Creación de contenido a partir de una plantilla lista para usar](#building-content-from-an-out-of-the-box-template) | [Importación de un HTML existente](#compatibility-mode) |

## Diseño de correos electrónicos con el editor {#without-existing-content}

>[!NOTE]
>
>En ambas estrategias de creación, es fundamental completar la línea de asunto antes de enviar el correo electrónico. Aprenda a [Añadir una línea](#add-a-subject-line)de asunto.

### Creación de un correo electrónico desde cero {#from-scratch-email}

Puede crear un correo electrónico fácilmente, añadir componentes y personalizar su contenido para enviar un envío rápidamente. Si es necesario, puede adaptar las opciones de estilo al contenido. Para obtener más información sobre la administración de ajustes de estilo y atributos integrados, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

1. Creación de un correo electrónico.
1. Cierre la página principal.

### Añadir una línea de asunto {#add-a-subject-line}

Las líneas de asunto son obligatorias al enviar un correo electrónico. Para obtener más información, consulte [Definición de la línea de asunto de un correo electrónico](../../designing/using/subject-line.md).

1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (a la que se puede acceder mediante el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

![](assets/subject-line-quick-start.png)

### Añadir componentes de estructura {#add-structure-components}

Los componentes de estructura definirán el diseño del correo electrónico. Para obtener más información, consulte [Definición de la estructura de un correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

En Componentes de estructura, arrastre y suelte los componentes del diseño que desee utilizar.

>[!NOTE]
>
>Puede seleccionar diferentes diseños de contenido que se añadirán a su correo electrónico.

![](assets/structure-components-quick-start.png)

### Añadir componentes de contenido {#add-content-components}

Puede agregar varios componentes de contenido al correo electrónico, como imágenes, texto y botones. Para obtener más información, consulte Componentes [de contenido](../../designing/using/designing-from-scratch.md#about-content-components).

* **Imagen**

   1. En Componentes **** de contenido, arrastre y suelte la imagen en uno de los componentes de estructura.
   1. Haga clic en **Examinar**.
   1. Seleccione el archivo de imagen del equipo.

   ![](assets/browse-image-quick-start.png)

* **Texto con personalización**

   1. En Componentes **** de contenido, arrastre y suelte el texto en uno de los componentes de estructura.
   1. Haga clic en el componente e introduzca el texto.
   1. Para agregar un campo de personalización, haga clic en **Insertar campo** de personalización en la barra de herramientas.
   1. Seleccione el campo que necesita, como Nombre.

   ![](assets/edit-text-quick-start.png)

* **HTML**

   1. En Componentes **** de contenido, arrastre y suelte HTML en uno de los componentes de estructura.
   1. Haga clic en **Mostrar el código** fuente.
   1. Escriba el contenido HTML.
   1. Haga clic en **Save**.

   ![](assets/html-component-source-code.png)

   Si está familiarizado con HTML, puede copiar y pegar el código HTML del pie de página original mediante el componente de **[!UICONTROL Html]** contenido. For more on this, see [About content components](../../designing/using/designing-from-scratch.md#about-content-components).

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

1. Cree un correo electrónico y abra su contenido. For more on this, see [Creating an email](../../channels/using/creating-an-email.md).
1. Haga clic en el icono de inicio para acceder a la **[!UICONTROL Email Designer]** página de inicio.
1. Seleccione la pestaña **[!UICONTROL Templates]**.
1. Elija una plantilla HTML lista para usar.
Las distintas plantillas presentan varias combinaciones de varios tipos de elementos. Por ejemplo, las plantillas &#39;Calado&#39; tienen márgenes, mientras que las plantillas &#39;Astro&#39; no tienen uno. Para obtener más información sobre esto, consulte Plantillas [de contenido](../../designing/using/using-reusable-content.md#content-templates).
1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (a la que se puede acceder mediante el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.
1. Puede combinar estos elementos para crear una serie de variantes de correo electrónico. Por ejemplo, puede realizar el duplicado de una sección de correo electrónico seleccionando un componente de estructura y haciendo clic en **[!UICONTROL Duplicate]** desde la barra de herramientas contextual.
1. Puede mover los elementos mediante la flecha azul a la izquierda para arrastrar un componente de estructura por debajo o por encima de otro. Para obtener más información, consulte [Edición de la estructura de correo electrónico](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. También puede mover componentes para cambiar la organización de cada elemento de estructura. Para obtener más información, consulte [Añadir fragmentos y componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Modifique el contenido de cada elemento según sus necesidades: imágenes, texto, vínculos.
1. Adapte las opciones de estilo al contenido si es necesario. Para obtener más información, consulte [Edición de estilos de correo electrónico](../../designing/using/styles.md).

## Uso de contenido de correo electrónico existente {#with-existing-content}

Si desea crear un marco de plantillas modulares y fragmentos que se puedan combinar para reutilizarlos en varios correos electrónicos, debe considerar la posibilidad de convertir el HTML de correo electrónico en una plantilla de diseñador de correo electrónico.

### Conversión de contenido HTML {#converting-an-html-content}

Este caso de uso oferta una forma rápida de convertir el correo electrónico HTML en componentes de Email Designer. Para obtener más información sobre este tema, consulte [Conversión de contenido](../../designing/using/using-existing-content.md#converting-an-html-content)HTML.

>[!CAUTION]
>
>Esta sección está dirigida a usuarios familiarizados con el código HTML.

>[!NOTE]
>
>Al igual que el modo de compatibilidad, un componente HTML es editable con opciones limitadas: solo puede realizar una edición in-situ.


### Importación y edición de un correo electrónico HTML {#compatibility-mode}

Al cargar un contenido, debe contener etiquetas específicas para que sea totalmente compatible y editable con el editor WYSIWYG del Diseñador de correo electrónico.

Para obtener más información sobre la conversión de un correo electrónico existente en un correo electrónico compatible con el Diseñador de correo electrónico, consulte [esta sección](../../designing/using/using-existing-content.md#compatibility-mode).

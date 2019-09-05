---
title: Acerca de las plantillas
seo-title: Acerca de las plantillas
description: Acerca de las plantillas
seo-description: '" Las plantillas de Adobe Campaign le permiten preconfigurar parámetros según sus necesidades: las plantillas pueden contener una configuración completa o parcial de la actividad de mercadotecnia para simplificar el uso de Adobe Campaign para usuarios finales no técnicos. "'
page-status-flag: no activado nunca
uuid: 018534 b 6-61 a 3-433 e-bb 60-49883 c 8 b 9386
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: administración de plantillas
discoiquuid: 95218 ebe -5430-42 a 2-b 900-1 dadbbc 92 d 99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e2766bb9fef619142d3ee59cb8aa8ed20424a3f

---


# Acerca de las plantillas{#about-templates}

## Plantillas de actividad de marketing {#marketing-activity-templates}

Cuando cree una nueva actividad de marketing, la primera pantalla del asistente le pedirá que seleccione un tipo o una plantilla. Las plantillas permiten preconfigurar determinados parámetros según sus necesidades. La plantilla puede contener una configuración completa o parcial de la actividad de mercadotecnia. La administración de plantillas la realiza el administrador funcional.

El usuario final tiene una interfaz simplificada. Al crear una actividad de marketing nueva, solo tiene que seleccionar la plantilla que desee utilizar. No es necesario preocuparse por ninguna configuración técnica. Ya ha sido preconfigurado por el administrador funcional de la plantilla.

Por ejemplo, en el caso de una plantilla de correo electrónico, puede rellenar previamente el contenido HTML, la audiencia y cualquier otro parámetro de la entrega: programar, perfiles de prueba, propiedades generales de la entrega, parámetros avanzados, etc. Esto le permite ahorrar tiempo al crear una nueva actividad.

![](assets/template_1.png)

Para cada tipo de actividad de marketing, hay una o varias plantillas integradas disponibles con una configuración mínima. Estas plantillas integradas no se pueden modificar ni eliminar.

Las plantillas están disponibles para las siguientes actividades de mercadotecnia:

* Programas
* Campañas
* Entregas por correo electrónico
* Envíos SMS
* Notificaciones push
* Páginas de aterrizaje
* Flujos de trabajo
* Servicios
* Importar
* Mensajes transaccionales

Estas plantillas se gestionan desde **[!UICONTROL Resources]** la **[!UICONTROL Templates]** pantalla &gt;.

>[!NOTE]
>
>La configuración de marca se puede preconfigurar en una plantilla de correo electrónico o de página de aterrizaje. Para obtener más información, consulte la sección [de marca](../../administration/using/branding.md) .

## Plantillas de contenido {#content-templates}

Se puede acceder a las plantillas de contenido HTML desde **[!UICONTROL Resources]** la **[!UICONTROL Content templates & fragments]** pantalla &gt; del menú [Avanzado](../../start/using/interface-description.md#advanced-menu). Desde allí puede administrar plantillas de contenido de página de aterrizaje, plantillas de contenido de correo electrónico y fragmentos.

![](assets/content_templates_list.png)

Las plantillas de contenido integradas son de solo lectura. Para editar uno de ellos, primero debe duplicarlo.

Puede crear nuevas plantillas o fragmentos y definir su propio contenido. Para obtener más información sobre esto, consulte [Creación de una plantilla](../../start/using/about-templates.md#creating-a-content-template) de contenido y [Creación de un fragmento de contenido](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Al editar contenido con el correo electrónico de Designer, también puede crear plantillas de contenido guardando el contenido como fragmento o plantilla. Para obtener más información sobre esto, consulte [Guardar contenido como plantilla](../../start/using/about-templates.md#saving-content-as-template) y [Guardar contenido como fragmento](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

### Plantillas de contenido de correo electrónico predeterminadas {#email-content-templates}

Puede administrar el contenido HTML que se ofrece en **[!UICONTROL Templates]** la ficha de la página [principal de](../../designing/using/about-email-content-design.md#about-the-email-designer) Designer Designer.

Las plantillas de contenido de correo electrónico integradas incluyen dieciocho diseños optimizados para móviles y cuatro plantillas interactivas de mejor calidad diseñadas por artistas de Behance. Se corresponden con los usos más actuales como mensajes de bienvenida de clientes, boletines informativos y correos electrónicos de reparticipación, entre otros. Pueden personalizarse fácilmente con el contenido de sus marcas para facilitar el proceso de diseño de correos electrónicos desde cero.

![](assets/content_templates.png)

**Temas relacionados:**

* Descubra cómo personalizar plantillas de contenido [en este vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Para obtener más información sobre la edición de contenido, consulte [Acerca del diseño de contenido de correo electrónico](../../designing/using/about-email-content-design.md).

### Creación de una plantilla de contenido {#creating-a-content-template}

Puede crear sus propias plantillas de contenido para usarlas tantas veces como sea necesario.

El siguiente ejemplo muestra cómo crear una plantilla de contenido de correo electrónico.

1. Vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** y haga clic **[!UICONTROL Create]** en.
1. Haga clic en la etiqueta de correo electrónico para acceder **[!UICONTROL Properties]** a la ficha de Email Designer.
1. Especifique una etiqueta reconocible y seleccione los siguientes parámetros para poder utilizar esta plantilla en correos electrónicos:

   * Seleccione **[!UICONTROL Shared]** o **[!UICONTROL Delivery]** en la **[!UICONTROL Content type]** lista desplegable.
   * Seleccione **[!UICONTROL Template]** en la **[!UICONTROL HTML type]** lista desplegable.
   ![](assets/email_designer_create-template.png)

1. Si es necesario, puede definir una imagen que se utilizará como miniatura para la plantilla. Selecciónelo en la **[!UICONTROL Thumbnail]** ficha de las propiedades de la plantilla.

   ![](assets/email_designer_create-template_thumbnail.png)

   Esta miniatura se mostrará en **[!UICONTROL Templates]** la ficha de la página [principal de](../../designing/using/about-email-content-design.md#about-the-email-designer) Designer Designer.

1. Cierre **[!UICONTROL Properties]** la ficha para volver al área de trabajo principal.
1. Agregue componentes de estructura y componentes de contenido que puede personalizar según sea necesario.
   >[!NOTE]
   >
   > No puede insertar campos de personalización ni contenido condicional dentro de una plantilla de contenido.
1. Una vez editada, guarde la plantilla.

Esta plantilla ahora se puede utilizar en cualquier correo electrónico creado con el correo electrónico de Designer. Selecciónelo en la **[!UICONTROL Templates]** ficha de la página [principal de](../../designing/using/about-email-content-design.md#about-the-email-designer) Designer Designer.

![](assets/content_template_new.png)

### Guardar contenido como plantilla {#saving-content-as-template}

Al editar un correo electrónico con el correo electrónico de Designer, puede guardar directamente el contenido de ese correo electrónico como plantilla.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Seleccione **[!UICONTROL Save as template]** en la barra de herramientas principal de Designer Designer.

   ![](assets/email_designer_save-as-template.png)

1. Agregue una etiqueta y una descripción, si es necesario, y haga clic **[!UICONTROL Save]** en.

   ![](assets/email_designer_save-as-template_creation.png)

1. Para encontrar la plantilla que acaba de crear, vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

1. Para utilizar la nueva plantilla, selecciónela en la **[!UICONTROL Templates]** ficha de la página [principal de](../../designing/using/about-email-content-design.md#about-the-email-designer) Designer Designer.

   ![](assets/content_template_new.png)


---
title: Acerca de las plantillas
seo-title: Acerca de las plantillas
description: Acerca de las plantillas
seo-description: '"Las plantillas de Adobe Campaign le permiten preconfigurar parámetros según sus necesidades: las plantillas pueden contener una configuración completa o parcial de la actividad de marketing para simplificar el uso de Adobe Campaign para usuarios finales no técnicos."'
page-status-flag: nunca activado
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: referencia
topic-tags: administrar plantillas
discoiquuid: 95218ebe-5430-42a2-b900-1dadbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Acerca de las plantillas{#about-templates}

## Plantillas de actividades de marketing {#marketing-activity-templates}

Cuando crea una nueva actividad de marketing, la primera pantalla del asistente le pide que seleccione un tipo o una plantilla. Las plantillas le permiten preconfigurar ciertos parámetros según sus necesidades. La plantilla puede contener una configuración completa o parcial de la actividad de marketing. La administración de plantillas la realiza el administrador funcional.

El usuario final tiene una interfaz simplificada. Al crear una nueva actividad de marketing, solo tiene que seleccionar la plantilla que desee utilizar. No hay necesidad de preocuparse por ninguna configuración técnica. El administrador funcional de la plantilla ya lo ha preconfigurado.

Por ejemplo, en el caso de una plantilla de correo electrónico, puede rellenar previamente el contenido HTML, la audiencia y cualquier otro parámetro de la entrega: programación, perfiles de prueba, propiedades generales de la entrega, parámetros avanzados, etc. Esto le permite ahorrar tiempo al crear una nueva actividad.

![](assets/template_1.png)

Para cada tipo de actividad de marketing, hay una o varias plantillas listas para usar disponibles con una configuración mínima. Estas plantillas listas para usar no se pueden modificar ni eliminar.

Las plantillas están disponibles para las siguientes actividades de marketing:

* Programas
* Campañas
* Entregas por correo electrónico
* Entregas de SMS
* Notificaciones push
* Páginas de aterrizaje
* Flujos de trabajo
* Servicios
* Importar
* Mensajes transaccionales

Estas plantillas se administran desde la pantalla **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** .

>[!NOTE]
>
>La configuración de marca puede preconfigurarse en una plantilla de página de aterrizaje o correo electrónico. Para obtener más información, consulte la sección [Marcas](../../administration/using/branding.md) .

## Plantillas de contenido {#content-templates}

Se puede acceder a las plantillas de contenido HTML desde la pantalla **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** del menú [](../../start/using/interface-description.md#advanced-menu)Avanzado. Desde allí, puede administrar plantillas de contenido de página de aterrizaje, plantillas de contenido de correo electrónico y también fragmentos.

![](assets/content_templates_list.png)

Las plantillas de contenido integradas son de solo lectura. Para editar uno de ellos, primero debe duplicar la plantilla deseada.

Puede crear nuevas plantillas o fragmentos y definir su propio contenido. Para obtener más información sobre esto, consulte [Creación de una plantilla](../../start/using/about-templates.md#creating-a-content-template) de contenido y [Creación de un fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de contenido.

Al editar contenido con el Diseñador de correo electrónico, también puede crear plantillas de contenido guardando el contenido como fragmento o plantilla. Para obtener más información sobre esto, consulte [Guardar contenido como plantilla](../../start/using/about-templates.md#saving-content-as-template) y [Guardar contenido como fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

### Plantillas de contenido de correo electrónico integradas {#email-content-templates}

Puede administrar el contenido HTML que se ofrece en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md) .

Las plantillas de contenido de correo electrónico integradas incluyen dieciocho diseños optimizados para dispositivos móviles y cuatro plantillas adaptables de primera categoría diseñadas por artistas de Behance. Corresponden a los usos más actuales, como mensajes de bienvenida al cliente, boletines informativos y correos electrónicos de recontratación, entre otros. Pueden personalizarse fácilmente con el contenido de sus marcas para facilitar el proceso de diseño de correos electrónicos desde cero.

![](assets/content_templates.png)

**Temas relacionados:**

* Aprenda a personalizar plantillas de contenido [en este vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Para obtener más información sobre la edición de contenido, consulte [Acerca del diseño](../../designing/using/overview.md)de contenido de correo electrónico.

### Creación de una plantilla de contenido {#creating-a-content-template}

Puede crear sus propias plantillas de contenido para utilizarlas tantas veces como sea necesario.

El siguiente ejemplo muestra cómo crear una plantilla de contenido de correo electrónico.

1. Vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** y haga clic en **[!UICONTROL Create]**.
1. Haga clic en la etiqueta de correo electrónico para acceder a la **[!UICONTROL Properties]** ficha del Diseñador de correo electrónico.
1. Especifique una etiqueta reconocible y seleccione los siguientes parámetros para poder utilizar esta plantilla en los correos electrónicos:

   * Seleccione **[!UICONTROL Shared]** o **[!UICONTROL Delivery]** en la lista **[!UICONTROL Content type]** desplegable.
   * Seleccione **[!UICONTROL Template]** en la lista **[!UICONTROL HTML type]** desplegable.
   ![](assets/email_designer_create-template.png)

1. Si es necesario, puede establecer una imagen que se utilizará como miniatura para la plantilla. Selecciónelo en la **[!UICONTROL Thumbnail]** ficha de las propiedades de la plantilla.

   ![](assets/email_designer_create-template_thumbnail.png)

   Esta miniatura se mostrará en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md) .

1. Cierre la **[!UICONTROL Properties]** ficha para volver al espacio de trabajo principal.
1. Agregue componentes de estructura y componentes de contenido que puede personalizar según sea necesario.
   >[!NOTE]
   >
   > No puede insertar campos de personalización ni contenido condicional dentro de una plantilla de contenido.
1. Una vez editada, guarde la plantilla.

Esta plantilla ahora se puede utilizar en cualquier correo electrónico generado con el Diseñador de correo electrónico. Selecciónelo en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md) .

![](assets/content_template_new.png)

### Guardar contenido como plantilla {#saving-content-as-template}

Al editar un correo electrónico con el Diseñador de correo electrónico, puede guardar directamente el contenido de ese correo electrónico como plantilla.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Seleccione **[!UICONTROL Save as template]** en la barra de herramientas principal de Email Designer.

   ![](assets/email_designer_save-as-template.png)

1. Agregue una etiqueta y una descripción si es necesario y haga clic en **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Para buscar la plantilla que acaba de crear, vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

1. Para utilizar la nueva plantilla, selecciónela en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md) .

   ![](assets/content_template_new.png)


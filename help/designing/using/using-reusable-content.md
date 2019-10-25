---
title: 'Creación y uso de contenido reutilizable '
seo-title: Creación y uso de contenido reutilizable
description: Creación y uso de contenido reutilizable
seo-description: Empiece a crear contenido de correo electrónico reutilizable con el Diseñador de correo electrónico.
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
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---

# Creación y uso de contenido reutilizable {#using-reusable-content}

Aprenda a dominar la edición de contenido de correo electrónico. Con Email Designer, puede crear plantillas y fragmentos con su propio contenido predefinido y reutilizarlos para los siguientes envíos.

## Diseño mediante plantillas {#designing-templates}

>[!NOTE]
>
> En Adobe Campaign Standard, puede crear distintos tipos de plantillas a las que se puede acceder desde el menú **Recursos** &gt; **Plantillas** . Las plantillas utilizadas en el Diseñador de correo electrónico son plantillas de contenido. Para obtener más información, consulte [Acerca de las plantillas](../../start/using/about-templates.md).

### Plantillas de contenido {#content-templates}

Puede administrar el contenido HTML que se ofrecerá en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md) . Las distintas plantillas presentan varias combinaciones de varios tipos de elementos. Por ejemplo, las plantillas 'Calado' tienen márgenes mientras que las plantillas 'Astro' no tienen uno. Para obtener más información sobre esto, consulte Plantillas [de contenido](#content-templates).

![](assets/template_content.png)

Para obtener información sobre cómo generar un correo electrónico a partir de una plantilla lista para usar, consulte Diseñador de [correo electrónico](../../designing/using/quick-start.md#building-content-from-an-out-of-the-box-template).

### Creating a content template {#creating-a-content-template}

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

   Esta miniatura se mostrará en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

1. Cierre la **[!UICONTROL Properties]** ficha para volver al espacio de trabajo principal.
1. Agregue componentes de estructura y componentes de contenido que puede personalizar según sea necesario.
   >[!NOTE]
   >
   > No puede insertar campos de personalización ni contenido condicional dentro de una plantilla de contenido.
1. Una vez editada, guarde la plantilla.

Esta plantilla ahora se puede utilizar en cualquier correo electrónico generado con el Diseñador de correo electrónico. Selecciónelo en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

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

1. Para utilizar la nueva plantilla, selecciónela en la **[!UICONTROL Templates]** ficha de la página de inicio de [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

   ![](assets/content_template_new.png)

### Creación de una plantilla con fragmentos y componentes {#template-fragments-components}

Ahora puede crear una plantilla de correo electrónico con el Diseñador de correo electrónico. Utilice los componentes de contenido para reflejar las diferentes secciones del correo electrónico y ajustar la configuración para que estén lo más cerca posible de la newsletter original. Por último, inserte los fragmentos que acaba de crear.

1. Con el Diseñador de correo electrónico, cree una plantilla. Para obtener más información sobre esto, consulte Plantillas [de contenido](#content-templates).
1. Inserte varios componentes de estructura en la plantilla, correspondientes al encabezado, pie de página y cuerpo del correo electrónico. Para obtener más información sobre cómo agregar componentes de estructura, consulte [Edición de la estructura de correo electrónico con el Diseñador](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.
1. Inserte tantos componentes de contenido como sea necesario para crear el cuerpo de la newsletter. Este será el contenido editable de su correo electrónico que actualizará cada mes.

   ![](assets/des_loading_compatible_fragment_5.png)

   Si está familiarizado con el código HTML, Adobe recomienda utilizar **[!UICONTROL Html]** componentes en los que puede copiar y pegar los elementos más complejos del correo electrónico original. Utilice otros componentes como **[!UICONTROL Button]**, **[!UICONTROL Image]** o **[!UICONTROL Text]** para el resto del contenido. Para obtener más información sobre esto, consulte [Acerca de los componentes](../../designing/using/designing-from-scratch.md#about-content-components)de contenido.

   >[!NOTE]
   >
   >El uso del **[!UICONTROL Html]** componente permite crear componentes que se pueden editar con opciones limitadas. Antes de seleccionar este componente, asegúrese de que sabe cómo gestionar el código HTML.

1. Ajuste los componentes de contenido para que coincidan con el correo electrónico original tanto como pueda.

   ![](assets/des_loading_compatible_fragment_6.png)

   Para obtener más información sobre la administración de ajustes de estilo y atributos integrados, consulte [Edición de estilos](../../designing/using/styles.md)de correo electrónico.

1. Inserte los dos fragmentos (encabezado y pie de página) que creó anteriormente en los componentes de estructura deseados.

   ![](assets/des_loading_compatible_fragment_10.png)

1. Guarde la plantilla.

Ahora puede administrar completamente esta plantilla en el Diseñador de correo electrónico para crear y actualizar la newsletter que enviará todos los meses a los destinatarios.

Para utilizarlo, cree un correo electrónico y seleccione la plantilla de contenido que acaba de crear.

**Tema** relacionado:

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Vídeo de introducción al Diseñador de correo electrónico](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=spa)
* [Diseño de contenido de correo electrónico desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Acerca de los fragmentos {#about-fragments}

 Un fragmento es un componente reutilizable al que se puede hacer referencia en uno o varios correos electrónicos.
Se pueden encontrar en la interfaz en **Recursos** &gt; Fragmentos y plantillas **de contenido**.

Para optimizar el uso de fragmentos en el Diseñador de correo electrónico:

* Cree sus propios fragmentos. Consulte [Creación de un fragmento](#creating-a-content-fragment) de contenido y [Guardado de contenido como fragmento](#saving-content-as-a-fragment).
* Utilícelos tantas veces como sea necesario en sus correos electrónicos. Consulte [Inserción de elementos en un correo electrónico](#inserting-elements-into-an-email).
* Al editar un fragmento, los cambios se sincronizan: se propagan automáticamente a todos los correos electrónicos (siempre que no se hayan preparado ni enviado aún) que contengan ese fragmento.

Cuando se agregan a un correo electrónico, los fragmentos se bloquean de forma predeterminada. Si desea modificar un fragmento para un correo electrónico específico, puede romper la sincronización con el fragmento original desbloquearlo en el correo electrónico donde se utiliza. Los cambios ya no se sincronizarán.

Para desbloquear un fragmento dentro de un correo electrónico, selecciónelo y haga clic en el icono de bloqueo de la barra de herramientas contextual.

![](assets/des_unlocking_fragment.png)

Ese fragmento se convierte en un componente independiente que ya no está vinculado al fragmento original. Luego se puede editar como cualquier otro componente de contenido. Consulte [Acerca de los componentes](../../designing/using/designing-from-scratch.md#about-content-components)de contenido.

### Inserción de fragmentos en un correo electrónico {#inserting-elements-into-an-email}

Para definir el contenido del correo electrónico, puede añadir elementos de contenido en los componentes de estructura que haya colocado de antemano. Consulte [Edición de la estructura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de correo electrónico.

1. Acceda a los elementos de contenido seleccionando el icono **+** de la izquierda. Seleccione [Fragmentos](#about-fragments) o componentes [de contenido](../../designing/using/designing-from-scratch.md#about-content-components).
1. Si ya conoce la etiqueta o parte de la etiqueta del fragmento que desea agregar, puede buscarla.

   ![](assets/email_designer_fragmentsearch.png)

1. Arrastre y suelte un fragmento o componente de contenido de la paleta en un componente de estructura del correo electrónico.

   ![](assets/email_designer_addfragment.png)

   Una vez agregado un elemento al correo electrónico, se puede mover dentro del componente de estructura o a otro componente de estructura del correo electrónico.

   ![](assets/email_designer_movefragment.png)

1. Edite el elemento para que coincida con las necesidades exactas de este correo electrónico. Puede agregar texto, vínculos, imágenes, etc.

   >[!NOTE]
   >
   >Los fragmentos se bloquean de forma predeterminada cuando se agregan a un correo electrónico. Puede romper la sincronización con el fragmento original si desea modificar el fragmento para un correo electrónico específico o realizar el cambio directamente en el fragmento. Consulte [Acerca de los fragmentos](#about-fragments).

1. Repita este procedimiento para todos los elementos que necesite agregar al correo electrónico.
1. Guarde su correo electrónico.

Ahora que la estructura de correo electrónico está llena, puede editar el estilo de cada elemento de contenido. Consulte [Edición de un elemento](../../designing/using/styles.md#editing-an-element).

>[!NOTE]
>
>Si se modifica un fragmento, los cambios se propagan automáticamente en los mensajes de correo electrónico donde se utiliza. Para obtener más información sobre esto, consulte [Acerca de los fragmentos](#about-fragments).

### Creación de un fragmento de contenido {#creating-a-content-fragment}

Puede crear sus propios fragmentos de contenido para utilizarlos según sea necesario en uno o varios correos electrónicos.

1. Vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** y haga clic en **[!UICONTROL Create]**.
1. Haga clic en la etiqueta de correo electrónico para acceder a la **[!UICONTROL Properties]** ficha del Diseñador de correo electrónico.
1. Especifique una etiqueta reconocible y seleccione los parámetros siguientes para buscar el fragmento al editar el contenido del correo electrónico:

   * Debido a que los fragmentos solo son compatibles con los correos electrónicos, seleccione **[!UICONTROL Delivery]** en la lista **[!UICONTROL Content type]** desplegable.
   * Seleccione **[!UICONTROL Fragment]** en la lista **[!UICONTROL HTML type]** desplegable para poder utilizar este contenido como fragmento.
   ![](assets/email_designer_createfragment.png)

1. Si es necesario, puede establecer una imagen que se utilizará como miniatura para el fragmento. Selecciónelo en la **[!UICONTROL Thumbnail]** ficha de las propiedades de la plantilla.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Esta miniatura se mostrará junto a la etiqueta del fragmento al editar un correo electrónico.

1. Cierre la **[!UICONTROL Properties]** ficha para volver al espacio de trabajo principal.
1. Agregue componentes de estructura y componentes de contenido que puede personalizar según sea necesario.

   >[!CAUTION]
   >
   >Los fragmentos no pueden incluir campos de personalización, contenido dinámico u otro fragmento.
   >
   >Evite guardar como contenido de fragmento con componentes de estructura vacíos. Una vez insertado el fragmento &gt;, no se podrán editar.
   >
   >La vista [](../../designing/using/styles.md#switching-to-mobile-view) móvil no está disponible en fragmentos.

1. Una vez editado, guarde el fragmento.

Este fragmento ahora se puede utilizar en cualquier correo electrónico generado con el Diseñador de correo electrónico. Aparece en la sección de la **[!UICONTROL Fragments]** paleta.

>[!NOTE]
>
>No se pueden insertar campos de personalización dentro de un fragmento a menos que se utilicen en un correo electrónico y se desbloqueen. Consulte [Acerca de los fragmentos](#about-fragments).

### Guardar contenido como fragmento {#saving-content-as-a-fragment}

Al editar un correo electrónico con el Diseñador de correo electrónico, puede guardar directamente parte de ese correo electrónico como un fragmento.

* No puede guardar como fragmento una estructura que contenga campos de personalización, contenido dinámico u otro fragmento.
* Solo puede seleccionar estructuras adyacentes entre sí.
<!-- - You cannot select an empty structure.-->

1. Al editar un correo electrónico en el Diseñador de correo electrónico, seleccione **[!UICONTROL Save as fragment]** en la barra de herramientas principal.

   ![](assets/email_designer_save-as-fragment.png)

1. En el espacio de trabajo, seleccione las estructuras que compondrán el fragmento.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Asegúrese de seleccionar estructuras adyacentes entre sí y que no incluyan campos de personalización, contenido dinámico u otro fragmento.
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. Agregue una etiqueta y una descripción si es necesario y haga clic en **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. Para buscar el fragmento que acaba de crear, vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Para utilizar el nuevo fragmento, abra cualquier contenido de correo electrónico y selecciónelo en la lista de fragmentos.

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>La vista [](../../designing/using/styles.md#switching-to-mobile-view) móvil no está disponible en fragmentos. Si desea editar una vista móvil de correo electrónico, hágalo antes de guardar el contenido como un fragmento.

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

## Creación de encabezados y pies de página reutilizables mediante fragmentos {#header-footer-fragments}

Mediante el Diseñador de correo electrónico, cree un fragmento para cada sección reutilizable. En este ejemplo, creará dos fragmentos: una para el encabezado y otra para el pie de página. A continuación, puede copiar las partes relevantes del contenido existente en estos fragmentos.

Para realizar esto, siga los pasos a continuación:

1. En Adobe Campaign, vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** y cree un fragmento para el encabezado. Para obtener más información sobre esto, consulte [Creación de un fragmento](#creating-a-content-fragment)de contenido.
1. Agregue al fragmento tantos componentes de estructura como necesite.

![](assets/des_loading_compatible_fragment_1.png)

1. Inserte componentes de imagen y texto en la estructura.

![](assets/des_loading_compatible_fragment_2.png)

1. Cargue la imagen correspondiente, introduzca el texto y ajuste la configuración.

![](assets/des_loading_compatible_fragment_3.png)

1. Guarde el fragmento.
1. Proceda de forma similar para crear el pie de página y guardarlo.

![](assets/des_loading_compatible_fragment_4.png)

Los fragmentos ya están listos para utilizarse en una plantilla.

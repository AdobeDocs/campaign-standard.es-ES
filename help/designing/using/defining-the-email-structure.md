---
title: Definición de la estructura de correo electrónico
seo-title: Definición de la estructura de correo electrónico
description: Definición de la estructura de correo electrónico
seo-description: Descubra cómo utilizar el correo electrónico de Designer en Campaign para formar los correos electrónicos y rellenarlos con componentes de contenido.
page-status-flag: no activado nunca
uuid: 6 ec 63 f 65-1425-4 c 28-84 e 8-b 09574458 db 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: editing-email-content
discoiquuid: 207 fdf 6 d -165 a -41 af-ad 53-ba 97 d 3403 b 62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ac7fa8be4c408d75d77d3035af4cec25ac001c2

---


# Definición de la estructura de correo electrónico{#defining-the-email-structure}

## Edición de la estructura de correo electrónico {#editing-the-email-structure}

El correo electrónico de Designer permite definir fácilmente la estructura del correo electrónico. Al agregar y mover elementos estructurales con acciones sencillas de arrastrar y soltar, puede diseñar la forma del mensaje de correo electrónico en segundos.

Para editar la estructura de un mensaje de correo electrónico:

1. Abra un contenido existente o cree un nuevo contenido de correo electrónico.
1. Para acceder al **[!UICONTROL Structure components]** icono **, seleccione** el icono +.

   ![](assets/email_designer_structure.png)

1. Arrastre y suelte los componentes de estructura que necesita para dar forma a su correo electrónico.

   ![](assets/email_designer_structure_components.png)

   Una línea azul materializa la ubicación exacta de los componentes de estructura antes de colocarla. Puede colocarlo arriba, entre o debajo de cualquier otro componente, pero no dentro de.

   >[!NOTE]
   >
   >Una vez colocado en el correo electrónico, no podrá mover ni eliminar los componentes a menos que ya haya un componente de contenido o un fragmento colocado dentro.

1. Hay disponibles varios componentes de estructura compuestos de una o más columnas.

   Seleccione **[!UICONTROL n:n column]** el componente para definir el número de columnas que elija (entre 3 y 10). También puede definir el ancho de cada columna moviendo las flechas al final de cada columna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamaño de columna no puede estar por debajo del 10% del ancho total del componente de estructura. No se puede eliminar una columna que no esté vacía.

Una vez definido la estructura, puede agregar fragmentos de contenido y componentes a su correo electrónico.

## Adición de fragmentos y componentes de contenido {#adding-fragments-and-content-components}

Con el correo electrónico de Designer, después de agregar componentes de estructura a su correo electrónico, puede definir su contenido. Para ello, debe agregar elementos dentro de cada componente de estructura.

Puede utilizar dos categorías de elementos de contenido: **fragmentos** y **componentes de contenido**.

### Acerca de los fragmentos {#about-fragments}

Un fragmento es un componente reutilizable al que se puede hacer referencia en uno o varios correos electrónicos.

Para realizar el mejor uso de fragmentos en el correo electrónico de Designer:

* Cree sus propios fragmentos. Consulte [Creación de un fragmento de contenido](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) y [Almacenamiento de contenido como fragmento](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* Utilícelo tantas veces como sea necesario en sus correos electrónicos. Consulte [Inserción de elementos en un correo electrónico](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email).
* Cuando edita un fragmento, los cambios se sincronizan: se propagan automáticamente a todos los correos electrónicos (siempre que no se hayan preparado ni enviado aún) que contengan dicho fragmento.

Cuando se agrega a un correo electrónico, los fragmentos están bloqueados de forma predeterminada. Si desea modificar un fragmento para un correo electrónico específico, puede desglosar la sincronización con el fragmento original desbloqueado en el correo electrónico donde se utiliza. Los cambios ya no se sincronizarán.

Para desbloquear un fragmento dentro de un mensaje de correo electrónico, selecciónelo y haga clic en el icono de candado de la barra contextual.

![](assets/des_unlocking_fragment.png)

Ese fragmento se convierte en un componente independiente que ya no está vinculado al fragmento original. Se puede editar como cualquier otro componente de contenido. Consulte [Acerca de los componentes del contenido](../../designing/using/defining-the-email-structure.md#about-content-components).

### Acerca de los componentes de contenido {#about-content-components}

Los componentes de contenido son componentes sin procesar y vacíos que puede editar una vez en un mensaje de correo electrónico.

Puede agregar tantos componentes de contenido como desee en un componente de estructura. También puede moverlos dentro del componente de estructura o de otro componente de estructura.

Esta es la lista de los componentes disponibles en el correo electrónico de Designer:

* **[!UICONTROL Button]**

   Si necesita utilizar varios botones, en lugar de editar cada botón desde cero, puede duplicar **[!UICONTROL Button]** el componente utilizando la barra contextual.

   También puede guardar botones en fragmentos que pueden reutilizarse. Para obtener más información, consulte [Creación de un fragmento de contenido](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) y [Almacenamiento de contenido como fragmento](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

* **[!UICONTROL Carousel]**

   Para obtener más información sobre esto, consulte [Uso del componente carrusel](../../designing/using/defining-the-email-structure.md#using-the-carousel-component).

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   Utilice este componente para copiar y pegar las distintas partes del HTML existente. Esto le permite crear componentes HTML modulares gratuitos.

   >[!NOTE]
   >
   >Un componente HTML gratuito se puede editar con opciones limitadas. Si todos los estilos no están alineados, asegúrese de agregar la CSS adecuada en la sección **head** del código HTML; de lo contrario, el correo electrónico no será interactivo. Use **[!UICONTROL Preview]** el botón para comprobar la respuesta del contenido (consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md)).

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### Uso del componente carrusel {#using-the-carousel-component}

1. Arrastre y suelte **[!UICONTROL Carousel]** el componente dentro de un componente de estructura.
1. Navegue para seleccionar imágenes desde su equipo.

   ![](assets/des_carousel_browse.png)

1. Desde el **[!UICONTROL Settings]** panel, establezca el número de miniaturas que desee en el carrusel.
1. Seleccione una imagen de reserva del equipo.

   ![](assets/des_carousel_fallback.png)

   El componente carrusel no es compatible con todos los programas de correo electrónico. Cargue una alternativa para mostrar una imagen cuando el carrusel no sea compatible con el correo electrónico.

   >[!NOTE]
   >
   >El componente carrusel es compatible con las siguientes plataformas de correo electrónico: Apple Mail 7, Apple Mail 8, Outlook 2011 para Mac, Outlook 2016 para Mac, Mozilla Thunderbird, ipad y ipad mini iOS, iphone iOS, Android, AOL (Chrome, Firefox y Safari).

1. Seleccione **[!UICONTROL Fallback view]** para mostrar la imagen de reserva en el correo electrónico de Designer.

### Inserción de elementos en un mensaje de correo electrónico {#inserting-elements-into-an-email}

Para definir el contenido de su correo electrónico, puede agregar elementos de contenido en los componentes de estructura que haya colocado previamente. Consulte [Edición de la estructura de correo electrónico](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Para acceder a los elementos de contenido, seleccione el icono **+** a la izquierda. Seleccione [Fragmentos](../../designing/using/defining-the-email-structure.md#about-fragments) o [componentes de contenido](../../designing/using/defining-the-email-structure.md#about-content-components).
1. Si ya conoce la etiqueta o parte de la etiqueta del fragmento que desea agregar, puede buscarlo.

   ![](assets/email_designer_fragmentsearch.png)

1. Arrastre y suelte un fragmento o componente de contenido de la paleta a un componente de estructura del correo electrónico.

   ![](assets/email_designer_addfragment.png)

   Una vez agregado el elemento al correo electrónico, se puede mover dentro del componente de estructura o a otro componente de estructura del correo electrónico.

   ![](assets/email_designer_movefragment.png)

1. Edite el elemento para que coincida con las necesidades exactas de este correo electrónico. Puede agregar texto, vínculos, imágenes, etc.

   >[!NOTE]
   >
   >Los fragmentos están bloqueados de forma predeterminada cuando se añaden a un mensaje de correo electrónico. Puede dividir la sincronización con el fragmento original si desea modificar el fragmento para un correo electrónico específico o realizar el cambio directamente en el fragmento. Consulte [Acerca de los fragmentos](../../designing/using/defining-the-email-structure.md#about-fragments).

1. Repita este procedimiento para todos los elementos que necesite agregar al correo electrónico.
1. Guarde el correo electrónico.

Ahora que la estructura de correo electrónico está llena, puede editar el estilo de cada elemento de contenido. Consulte [Edición de un elemento](../../designing/using/editing-email-styles.md#editing-an-element).

>[!NOTE]
>
>Si se modifica un fragmento, los cambios se propagan automáticamente en los mensajes de correo electrónico donde se utiliza. Para obtener más información sobre esto, consulte [Acerca de los fragmentos](../../designing/using/defining-the-email-structure.md#about-fragments).

### Creación de un fragmento de contenido {#creating-a-content-fragment}

Puede crear sus propios fragmentos de contenido para utilizarlos según sea necesario en uno o varios correos electrónicos.

1. Vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** y haga clic **[!UICONTROL Create]** en.
1. Haga clic en la etiqueta de correo electrónico para acceder **[!UICONTROL Properties]** a la ficha de Email Designer.
1. Especifique una etiqueta reconocible y seleccione los siguientes parámetros para encontrar el fragmento al editar contenido de correo electrónico:

   * Debido a que los fragmentos solo son compatibles con los correos electrónicos, seleccione **[!UICONTROL Delivery]** en la lista **[!UICONTROL Content type]** desplegable.
   * Seleccione **[!UICONTROL Fragment]** entre la lista **[!UICONTROL HTML type]** desplegable para poder utilizar este contenido como fragmento.
   ![](assets/email_designer_createfragment.png)

1. Si es necesario, puede definir una imagen que se utilizará como miniatura para el fragmento. Selecciónelo en la **[!UICONTROL Thumbnail]** ficha de las propiedades de la plantilla.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Esta miniatura se mostrará junto a la etiqueta del fragmento al editar un mensaje de correo electrónico.

1. Cierre **[!UICONTROL Properties]** la ficha para volver al área de trabajo principal.
1. Agregue componentes de estructura y componentes de contenido que puede personalizar según sea necesario.

   >[!NOTE]
   >
   >Los fragmentos no pueden incluir campos de personalización, contenido dinámico u otro fragmento.
   >La vista [móvil no](../../designing/using/about-email-content-design.md#switching-to-mobile-view) está disponible en fragmentos.

1. Una vez editado, guarde el fragmento.

Este fragmento ahora se puede utilizar en cualquier correo electrónico creado con el correo electrónico de Designer. Aparece debajo de **[!UICONTROL Fragments]** la sección de la paleta.

>[!NOTE]
>
>No se pueden insertar campos de personalización dentro de un fragmento a menos que se usen en un correo electrónico y se desbloquee. Consulte [Acerca de los fragmentos](../../designing/using/defining-the-email-structure.md#about-fragments).

### Guardar contenido como fragmento {#saving-content-as-a-fragment}

Al editar un correo electrónico con el correo electrónico de Designer, puede guardar directamente parte de ese mensaje de correo electrónico como fragmento.

* No puede guardar como fragmento una estructura que contenga campos de personalización, contenido dinámico u otro fragmento.
* Solo puede seleccionar estructuras adyacentes entre sí.
<!--* You cannot select an empty structure.-->

1. Cuando edite un correo electrónico en el correo electrónico de Designer, seleccione **[!UICONTROL Save as fragment]** en la barra de herramientas principal.

   ![](assets/email_designer_save-as-fragment.png)

1. Desde el espacio de trabajo, seleccione las estructuras que compondrán el fragmento.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Asegúrese de seleccionar estructuras adyacentes entre sí y que no incluyan campos de personalización, contenido dinámico u otro fragmento.
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. Agregue una etiqueta y una descripción, si es necesario, y haga clic **[!UICONTROL Save]** en.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. Para encontrar el fragmento que acaba de crear, vaya a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Para utilizar el nuevo fragmento, abra cualquier contenido de correo electrónico y selecciónelo en la lista de fragmentos.

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>La vista [móvil no](../../designing/using/about-email-content-design.md#switching-to-mobile-view) está disponible en fragmentos. Si desea editar una vista móvil de correo electrónico, hágalo antes de guardar el contenido como fragmento.

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


---
title: Personalización del contenido del correo electrónico
description: Descubra cómo personalizar un correo electrónico en el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '2536'
ht-degree: 4%

---


# Personalización del contenido del correo electrónico {#personalization}

El contenido y la visualización de los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. Estas formas se pueden combinar según criterios en función de los perfiles. En general, Adobe Campaign le permite:

* Insertar campos personalizados dinámicos. See [Inserting a personalization field](#inserting-a-personalization-field).
* Insertar bloques de personalización predefinidos. Consulte [Añadir un bloque](#adding-a-content-block)de contenido.
* Personalice el remitente de un correo electrónico. Consulte [Personalización del remitente](#personalizing-the-sender).
* Personalice el asunto de un correo electrónico. See [Personalizing the subject line of an email](../../designing/using/subject-line.md#subject-line).
* Cree contenido condicional. Consulte [Definición de contenido dinámico en un mensaje de correo electrónico](#defining-dynamic-content-in-an-email).

## Personalización del remitente {#personalizing-the-sender}

Para definir el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio del Diseñador de correo electrónico (accesible mediante el icono de inicio). Para obtener más información sobre esto, consulte [Definición del remitente de un mensaje de correo electrónico](../../designing/using/subject-line.md#email-sender).

Puede cambiar el nombre del remitente haciendo clic en el bloque de nombre **del** remitente. A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

Este campo se puede personalizar. Para ello, puede añadir campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente.

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

## Personalización de direcciones URL{#personalizing-urls}

Adobe Campaign le permite personalizar una o varias direcciones URL en el mensaje agregándoles campos de personalización, bloques de contenido o contenido dinámico. Para ello:

1. Inserte una URL externa y especifique sus parámetros. See [Inserting a link](../../designing/using/links.md#inserting-a-link).
1. Si no se muestra, haga clic en el lápiz situado junto a la URL seleccionada en el panel Configuración para acceder a las opciones de personalización.
1. Añada los campos de personalización, los bloques de contenido y el contenido dinámico que desee utilizar.

   ![](assets/des_personalize_links.png)

1. Guarde los cambios.

>[!NOTE]
>
>Las direcciones URL de personalización no se pueden aplicar al nombre de dominio ni a la extensión URL. Se mostrará un mensaje de error durante la análisis de mensajes si la personalización es incorrecta. Al seleccionar un bloque de contenido, no se le permite seleccionar elementos como **Vínculo a página espejo**. Este tipo de bloques está prohibido dentro de un vínculo.

## Inserción de un campo personalizado{#inserting-a-personalization-field}

Adobe Campaign permite insertar un campo de la base de datos en la página, como el nombre del perfil.

>[!NOTE]
>
>Las siguientes imágenes muestran cómo insertar un campo de personalización mediante el Diseñador de [correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) para un correo electrónico.

Para agregar un campo de personalización al contenido:

1. Haga clic dentro de un bloque de texto, haga clic en el **[!UICONTROL Personalize]** icono de la barra de herramientas contextual y seleccione **[!UICONTROL Insert personalization field]**. Para obtener más información sobre la interfaz de Email Designer, consulte [esta sección](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_perso_field_1.png)

1. Seleccione el campo que desee insertar en el contenido de la página.

   ![](assets/email_perso_field_2.png)

1. Haga clic **[!UICONTROL Confirm]**.

El nombre del campo aparece en el editor y se resalta.

![](assets/email_perso_field_3.png)

Una vez generada la personalización (por ejemplo, al obtener una vista previa y preparar el correo electrónico), este campo se reemplazará por el valor correspondiente al perfil de destino.

>[!NOTE]
>
>Si el correo electrónico se crea a partir de un flujo de trabajo, los datos adicionales calculados en el flujo de trabajo también estarán disponibles en los campos de personalización. Para obtener más información sobre cómo agregar datos adicionales desde un flujo de trabajo, consulte la sección [Enriquecimiento de datos](../../automating/using/about-targeting-activities.md#enriching-data) .

## Añadir un bloque de contenido{#adding-a-content-block}

Adobe Campaign oferta una lista de bloques de contenido preconfigurados. Estos bloques de contenido son dinámicos, personalizados y tienen una representación específica. Por ejemplo, puede agregar un saludo o un vínculo a la página espejo.

>[!NOTE]
>
>Las siguientes imágenes muestran cómo insertar un bloque de contenido mediante el Diseñador de [correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) para un correo electrónico.

Para agregar un bloque de contenido:

1. Haga clic dentro de un bloque de texto, haga clic en el **[!UICONTROL Personalize]** icono de la barra de herramientas contextual y seleccione **[!UICONTROL Insert content block]**. Para obtener más información sobre la interfaz de Email Designer, consulte [esta sección](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Seleccione el bloque de contenido que desee insertar. Los bloques disponibles varían según el contexto (correo electrónico o página de aterrizaje).

   ![](assets/email_content_block_2.png)

1. Haga clic **[!UICONTROL Save]**.

El nombre del bloque de contenido aparece en el editor y se resalta en amarillo. Se adaptará automáticamente al perfil cuando se genere la personalización.

![](assets/email_content_block_3.png)

Los bloques de contenido predeterminados son:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:: Este bloque de contenido solo se puede usar en una **página de aterrizaje**.
* **[!UICONTROL Default sender name (DefaultSenderName)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:: Este bloque de contenido solo se puede usar en un **envío**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### Creación de bloques de contenido personalizados {#creating-custom-content-blocks}

Puede definir nuevos bloques de contenido que se insertarán en un mensaje o página de aterrizaje.

Para crear un bloque de contenido, siga estos pasos:

1. Haga clic **[!UICONTROL Resources > Content blocks]** en el menú avanzado para acceder a la lista de los bloques de contenido.
1. Haga clic en el **[!UICONTROL Create]** botón o duplicado de un bloque de contenido preexistente.

   ![](assets/content_bloc_01.png)

1. Introduzca una etiqueta.
1. Seleccione el bloque **[!UICONTROL Content type]**. Hay tres opciones disponibles:

   * **[!UICONTROL Shared]**:: El bloque de contenido se puede utilizar en un envío o una página de aterrizaje.
   * **[!UICONTROL Delivery]**:: El bloque de contenido solo se puede usar en un envío.
   * **[!UICONTROL Landing page]**:: El bloque de contenido solo se puede usar en una página de aterrizaje.
   ![](assets/content_bloc_02.png)

1. Puede seleccionar un **[!UICONTROL Targeting dimension]**. Para obtener más información sobre esto, consulte [Acerca de la dimensión de segmentación](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. Puede seleccionar la **[!UICONTROL Depends on format]** opción para definir dos bloques diferentes: uno para correos electrónicos HTML y otro para correos electrónicos en formato de texto. Se mostrarán dos fichas en el editor (HTML y Texto) para definir el contenido correspondiente.

   ![](assets/content_bloc_03.png)

1. Introduzca el contenido de los bloques de contenido y haga clic en el **[!UICONTROL Create]** botón.

El bloque de contenido ahora se puede usar en el editor de contenido de un mensaje o una página de aterrizaje.

>[!CAUTION]
>
>Al editar el contenido de un bloque, asegúrese de que no haya espacios en blanco adicionales entre el principio y el final de las instrucciones *if* . En HTML, los espacios en blanco se muestran en la pantalla y, por lo tanto, impactarán en el diseño del contenido.

### Acerca de la dimensión de segmentación {#about-targeting-dimension}

La dimensión de segmentación le permite definir en qué tipo de mensaje puede utilizar el bloque de contenido. Esto sirve para evitar el uso de bloques inadecuados en un mensaje, lo que puede provocar errores.

De hecho, al editar un mensaje, solo puede seleccionar bloques de contenido con una dimensión de segmentación compatible con la dimensión de segmentación de dicho mensaje.

Por ejemplo, la dimensión de segmentación del **[!UICONTROL Unsubscription link]** bloque es **[!UICONTROL Profiles]** porque contiene campos de personalización específicos del **[!UICONTROL Profiles]** recurso. Por lo tanto, no puede utilizar un **[!UICONTROL Unsubscription link]** bloque en un mensaje transaccional [de](../../channels/using/event-transactional-messages.md)evento, ya que la dimensión de segmentación de ese tipo de mensaje es **[!UICONTROL Real-time events]**. Sin embargo, puede utilizar el bloque de vínculo **** Baja en un mensaje transaccional [de](../../channels/using/profile-transactional-messages.md)perfil, ya que la dimensión de segmentación de ese tipo de mensaje son **Perfiles**. Finalmente, el **[!UICONTROL Link to mirror page]** bloque no tiene una dimensión de segmentación, por lo que puede utilizarla en cualquier mensaje.

Si deja este campo vacío, el bloque de contenido será compatible con todos los mensajes, sin importar la dimensión de segmentación. Si establece una dimensión de segmentación, ese bloque solo será compatible con los mensajes que tengan la misma dimensión de segmentación.

Para obtener más información sobre esto, consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).

**Temas relacionados:**

* [Inserción de un campo personalizado](#inserting-a-personalization-field)
* [Añadir un bloque de contenido](#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](#defining-dynamic-content-in-an-email)

## Personalización de un origen de imagen{#personalizing-an-image-source}

Adobe Campaign le permite personalizar una o varias imágenes del mensaje según un criterio concreto o utilizar el seguimiento. Esto se realiza insertando campos de personalización, bloques de contenido o contenido dinámico en el origen de la imagen. Para ello:

1. Inserte una imagen en el contenido del mensaje o seleccione una imagen que ya esté presente.
1. En la paleta de propiedades de imagen, marque la **[!UICONTROL Enable personalization]** opción.

   ![](assets/des_personalize_images_1.png)

   Se muestra el **[!UICONTROL Source]** campo y la imagen seleccionada se muestra como **personalizada** en el editor.

1. Haga clic en el lápiz situado junto al botón de **[!UICONTROL Source]** campo para acceder a las opciones de personalización.
1. Después de agregar el origen de la imagen, agregue los campos de personalización, los bloques de contenido y el contenido dinámico que desee.

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >El nombre de dominio (http://mydomain.com) no se puede personalizar, debe introducirse manualmente. El resto de la dirección URL se puede personalizar. Por ejemplo: http://mydomain.com/`[Gender]`.jpg

1. Confirme los cambios.

## Contenido condicional {#conditional-content}

### Definición de una condición de visibilidad{#defining-a-visibility-condition}

Puede especificar una condición de visibilidad en cualquier elemento. Solo será visible si se respeta la condición.

Para agregar una condición de visibilidad, seleccione un bloque e introduzca la condición que debe respetarse en el **[!UICONTROL Visibility condition]** campo de su configuración.

![](assets/delivery_content_5.png)

Esta opción solo está disponible para los siguientes elementos: DIRECCIÓN, BLOQUEO, CENTRO, DIR, DIV, DL, FIELDSET, FORMULARIO, H1, H2, H3, H4, H5, H6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

El editor de expresiones se presenta en la sección de edición [de expresiones](../../automating/using/editing-queries.md#about-query-editor) avanzadas.

Estas condiciones adoptan la sintaxis de expresión XTK (por ejemplo, **context.perfil.email !=&#39;&#39;** o **context.perfil.status=&#39;0&#39;**). De forma predeterminada, todos los campos son visibles.

>[!NOTE]
>
>No se puede definir una condición para un bloque que ya contiene un subelemento con contenido dinámico o un bloque que ya constituye un contenido dinámico. Los bloques dinámicos no visibles, como las listas desplegables, no se pueden editar.

### Definición de contenido dinámico en un correo electrónico{#defining-dynamic-content-in-an-email}

En un mensaje de correo electrónico, puede definir diferentes contenidos que se mostrarán dinámicamente a los destinatarios según las condiciones definidas mediante el editor de expresiones. Por ejemplo, desde el mismo mensaje de correo electrónico, puede asegurarse de que cada perfil recibe un mensaje diferente según el intervalo de edad.

Definir contenido dinámico es diferente de [definir condiciones](#defining-a-visibility-condition)de visibilidad.

1. Seleccione un fragmento, un componente o un elemento. En este ejemplo, seleccione una imagen.
1. Haga clic en el **[!UICONTROL Dynamic content]** icono de la barra de herramientas contextual.

   ![](assets/dynamic_content_2.png)

   La **[!UICONTROL Dynamic content]** sección aparece en la paleta de la izquierda.

   ![](assets/dynamic_content_3.png)

   De forma predeterminada, esta sección contiene dos elementos: la variante predeterminada y una nueva variante.

   >[!NOTE]
   >
   >El contenido siempre debe tener una variante predeterminada. No puede eliminarlo.

1. Haga clic en el **[!UICONTROL Edit]** botón para definir las condiciones de visualización de la primera variante alternativa.

   ![](assets/dynamic_content_4.png)

1. Especifique una etiqueta y seleccione los campos que desea definir como condiciones. Por ejemplo, en el **[!UICONTROL General]** nodo, seleccione el **[!UICONTROL Age]** campo

   ![](assets/dynamic_content_5.png)

1. Establezca las condiciones de filtrado. Por ejemplo, desea que se muestre un contenido diferente a personas de entre 18 y 25 años de edad.

   ![](assets/dynamic_content_6.png)

1. Una vez definidas todas las condiciones, defina el orden de prioridad en el que se aplicará la condición y guarde los cambios.

   ![](assets/dynamic_content_7.png)

   El contenido se mostrará en la paleta en orden de prioridad, de arriba a abajo. For more on priorities, refer to [this section](#defining-dynamic-content-in-an-email).

1. Cargue una nueva imagen para la variante que acaba de definir.

   ![](assets/dynamic_content_8.png)

   Los destinatarios de entre 18 y 25 años verán la nueva imagen.

   ![](assets/dynamic_content_10.png)

1. Haga clic en **[!UICONTROL Add a condition]** para agregar un nuevo contenido y su regla vinculada.

   ![](assets/dynamic_content_9.png)

   Por ejemplo, puede agregar una imagen diferente para mostrarla a personas de entre 26 y 35 años de edad.

1. Proceda de forma similar con cualquier otro elemento del correo electrónico que desee mostrar dinámicamente. Puede ser texto, botón, fragmento, etc. Guarde los cambios.

>[!CAUTION]
>
>Una vez que haya preparado el mensaje y antes de enviarlo, pruébelo con una prueba. Si no lo hace, es posible que no se detecten algunos errores y que no se envíe el correo electrónico.

**Temas relacionados:**

* [Envío de pruebas](../../sending/using/sending-proofs.md)
* [Edición avanzada de expresiones](../../automating/using/editing-queries.md#about-query-editor)

### Orden de prioridad {#order-of-priority}

En el editor de expresiones, cuando se define un contenido dinámico, el orden de prioridad es el siguiente.

1. Puede definir dos contenidos dinámicos diferentes con **dos condiciones** diferentes, por ejemplo:

   **Condición 1:** el sexo del perfil es masculino,

   **Condición 2:** el perfil tiene entre 20 y 30 años.

   ![](assets/delivery_content_61.png)

   Algunos perfiles de la base de datos corresponden a las dos condiciones, pero sólo se puede enviar un correo electrónico con un contenido dinámico.

1. Por lo tanto, debe definir la prioridad del contenido dinámico. Una condición con un orden de prioridad de **1** (y, por lo tanto, el contenido dinámico correspondiente) se enviará a un perfil aunque este perfil también cumpla otra condición cuyo orden de prioridad sea **2** o **3** .

   ![](assets/delivery_content_62.png)

Solo puede definir un orden de prioridad por contenido dinámico.

## Ejemplo: Personalización de correo electrónico{#example-email-personalization}

En este ejemplo, un miembro del equipo de servicios de marketing ha creado un correo electrónico para informar a algunos de sus clientes de que existe una oferta especial solo para ellos. El miembro del equipo decidió personalizar el correo electrónico según las edades respectivas de los clientes. Los clientes de entre 18 y 27 años recibirán un correo electrónico con una imagen y un lema diferentes a los que recibirán los clientes mayores de 27 años.

El correo electrónico se crea de la siguiente manera:

* El contenido dinámico se aplica a la imagen y el contenido dinámico se configura según el rango de edad.

   ![](assets/delivery_content_43.png)

   Añadir y configurar contenido dinámico se detalla en la sección [Definición de contenido dinámico en un mensaje de correo electrónico](#defining-dynamic-content-in-an-email) .

* Se aplican Campos de personalización y contenido dinámico al texto. Según el rango de edad del perfil, el correo electrónico inicio con el nombre del perfil o el título y los apellidos del perfil.

   ![](assets/delivery_content_44.png)

   Añadir y configurar los campos de personalización se detalla en la sección [Inserción de un campo](#inserting-a-personalization-field) de personalización.

### Configuración de imágenes {#configuring-images}

En este ejemplo, el contenido dinámico aplicado a las imágenes se configura de la siguiente manera:

**A destinatario de entre 18 y 27 años:**

1. Seleccione el contenido dinámico en la **[!UICONTROL Properties]** paleta y haga clic en el **[!UICONTROL Edit]** botón.

   ![](assets/delivery_content_48.png)

1. Edite la etiqueta y seleccione el **[!UICONTROL Age]** campo del **[!UICONTROL Profile]** nodo.

   ![](assets/delivery_content_49.png)

1. Seleccione el operador **Bueno o igual** y, a continuación, escriba **18** para crear la expresión **anterior a 18** .

   ![](assets/delivery_content_50.png)

1. Añada una nueva **[!UICONTROL Age]** condición.

   Seleccione el operador **Menor o igual que** seguido de 27 en el campo de valor para crear la expresión **menor de 27** .

   ![](assets/delivery_content_51.png)

1. Confirme los cambios.

**A los perfiles de destinatario de 27 años o más:**

1. Seleccione el contenido dinámico de la paleta y edítelo.
1. Edite la etiqueta y seleccione el **[!UICONTROL Age]** campo del **[!UICONTROL Profile]** nodo.
1. Añada el operador **Bueno que** seguido de 27 en el campo de valor para crear la expresión **anterior a 27** .

   ![](assets/delivery_content_52.png)

1. Confirme los cambios.

El contenido dinámico está configurado correctamente.

### Configuración del texto {#configuring-text}

En este ejemplo, el contenido dinámico aplicado a los textos se configura de la siguiente manera:

**Para destinatario de perfiles de entre 18 y 27 años:**

1. Seleccione el componente de estructura que desee y agregue un contenido dinámico.
1. Edite el contenido dinámico y configure las expresiones de objetivo. Consulte [Configuración de imágenes](#configuring-images).
1. En el componente de estructura, en la posición deseada, haga clic en el icono de la barra de herramientas contextual y seleccione **[!UICONTROL Personalize]** **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. En la lista que aparece, seleccione el **[!UICONTROL First name]** campo y confirme.

   ![](assets/delivery_content_54.png)

1. El campo de personalización se inserta perfectamente en el contenido dinámico seleccionado.

**A los perfiles de destinatario de 27 años o más:**

1. Seleccione el componente de estructura que desee y agregue un contenido dinámico.
1. Edite el contenido dinámico y configure las expresiones de objetivo. Consulte [Configuración de imágenes](#configuring-images).
1. En el componente de estructura, en la posición deseada, haga clic en el icono de la barra de herramientas contextual y seleccione **[!UICONTROL Personalize]** **[!UICONTROL Insert personalization field]**.
1. Seleccione **[!UICONTROL Title]** en la lista desplegable.
1. Proceda de forma similar para agregar el **[!UICONTROL Last name]** campo.

   ![](assets/delivery_content_56.png)

Sus campos de personalización deberían insertarse perfectamente en el contenido dinámico seleccionado.

### Vista previa de correos electrónicos {#previewing-emails}

La vista previa le permite comprobar que los campos de personalización y el contenido dinámico están correctamente configurados antes de enviar el **[!UICONTROL Proofs]**. Durante la previsualización, puede seleccionar diferentes perfiles de prueba correspondientes a los destinatarios de correo electrónico.

Sin perfiles de prueba, el correo electrónico que aparece de forma predeterminada es:

![](assets/delivery_content_45.png)

El mensaje de correo electrónico no tiene campos de personalización y se utiliza la imagen predeterminada.

El primer perfil de prueba corresponde a un cliente de entre 18 y 27 años. Al seleccionar este perfil, aparece el siguiente mensaje de correo electrónico:

![](assets/delivery_content_46.png)

El campo de personalización que corresponde a la expresión de entre 18 y 27 años, en concreto el nombre del perfil, está configurado correctamente y la imagen también ha cambiado según el perfil.

El segundo perfil corresponde a un cliente mayor de 27 años y genera el siguiente correo electrónico:

![](assets/delivery_content_47.png)

La imagen ha cambiado gracias al contenido dinámico, y el lema que aparece es el lema más formal definido para este público objetivo.

**Temas relacionados:**

* [Creación de audiencias](../../audiences/using/creating-audiences.md)
* [Preparación del envío](../../sending/using/preparing-the-send.md)


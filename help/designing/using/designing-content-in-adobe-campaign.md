---
title: Diseño de contenido en Adobe Campaign
description: Cree contenido de correo electrónico empezando desde cero, importando HTML o aprovechando las plantillas existentes.
audience: designing
content-type: reference
topic-tags: about-content-design
feature: Email Design
role: User
level: Beginner
exl-id: 85d6361b-6c27-42c0-bac4-774b71625bf8
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 88%

---

# Diseñador de correos electrónicos de Campaign{#designing-content-in-adobe-campaign}

Una vez creado un correo electrónico en Adobe Campaign, debe definir su contenido.

El Diseñador de correo electrónico le permite crear correos electrónicos personalizados y cautivadores con una interfaz de arrastrar y soltar. Ya sea desde una pizarra en blanco o aprovechando los fragmentos de contenido o las plantillas existentes, diseñe y perfeccione el contenido de cada correo electrónico, ya sea promocional o transaccional.

Compilado para ofrecer HTML optimizado para un diseño interactivo, el Diseñador de correo electrónico le permite definir y aplicar fácilmente las condiciones de visibilidad y de contenido dinámico a un correo electrónico, una plantilla o un fragmento directamente a través de la interfaz de usuario. Puede alternar sin problemas entre la interfaz de arrastre y suelte y el código del HTML haciendo clic en un botón.

El Diseñador de correo electrónico le permite crear plantillas contenido de correo electrónico y las respectivas plantillas. Es compatible con correos electrónicos simples, transaccionales, de prueba A/B, multilingües y recurrentes.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

![](assets/do-not-localize/how-to-video.png) [Descubra el Diseñador de correo electrónico con este vídeo](#video)

* Para descubrir cómo crear contenido de correo electrónico, consulte [Introducción al Diseñador de correo electrónico](../../designing/using/quick-start.md).
* Para obtener una descripción general del Diseñador de correo electrónico, consulte [Uso del Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md).
* Para obtener más información sobre la creación de contenido:
   * Desde cero, consulte el [Diseño de correos electrónicos desde cero](../../designing/using/designing-from-scratch.md).
   * Para contenido existente, consulte [Diseño con contenido existente](../../designing/using/using-existing-content.md).
   * Con integraciones de Creative Cloud, consulte [Diseño de correo electrónico con varias soluciones](../../designing/using/using-integrations.md).
* Para obtener más información sobre Personalización, consulte [Personalización](../../designing/using/personalization.md).

Al crear un correo electrónico, puede elegir utilizar una plantilla predefinida o cargar un contenido existente de otro origen. Consulte [Selección de contenido existente](../../designing/using/using-existing-content.md#selecting-an-existing-content).

Para aumentar la eficacia de sus campañas de marketing, personalice su contenido. Consulte [Inserción de campos de personalización](../../designing/using/personalization.md#inserting-a-personalization-field) y [Añadir un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block).

También puede definir contenido dinámico que varíe según cada perfil. Consulte [Definición del contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) y [Definición del contenido dinámico en una página de aterrizaje](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Mejore sus mensajes y páginas de aterrizaje con vínculos e imágenes. Consulte [Inserción de vínculos](../../designing/using/links.md#inserting-a-link) e [Inserción de imágenes](../../designing/using/images.md#inserting-images).

## Interfaz de Diseñador de correo electrónico {#email-designer-interface}

El Diseñador de correo electrónico proporciona muchas opciones que le permiten crear, editar y personalizar todos los aspectos del contenido.

La interfaz se compone de varias áreas que ofrecen diferentes funcionalidades:

![](assets/email_designer_overview.png)

Desde los elementos disponibles en la **paleta** (1), arrastre y suelte los componentes de estructura y los fragmentos de contenido en el **Espacio de trabajo** principal (2). Seleccione un componente o elemento en el **Espacio de trabajo** (2) y personalice su estilo principal y sus características de visualización en el panel **Configuración** (3).

Acceda a las opciones y configuraciones más generales desde la **barra de herramientas** principal (4).

>[!NOTE]
>
>El panel **Configuración** puede moverse a la izquierda según la resolución de pantalla y la visualización.

![](assets/email_designer_toolbar.png)

La **barra de herramientas contextual** de la interfaz del editor ofrece varias funcionalidades en función de la zona seleccionada. Contiene botones de acción y botones que permiten cambiar el estilo del texto. Las modificaciones realizadas se aplican siempre a la zona seleccionada.

### Página de inicio del Diseñador de correo electrónico {#email-designer-home-page}

Al [crear un correo electrónico](../../channels/using/creating-an-email.md), se muestra la **[!UICONTROL Email Designer]** página de inicio automáticamente al seleccionar el contenido del correo electrónico.

![](assets/email_designer_home_page.png)

La pestaña **[!UICONTROL Properties]** permite editar los detalles del correo electrónico, como la etiqueta, la dirección y el nombre del remitente o el asunto del correo electrónico. También puede acceder a esta pestaña haciendo clic en la etiqueta de correo electrónico en la parte superior de la pantalla.

![](assets/email_designer_home_properties.png)

La pestaña **[!UICONTROL Templates]** le permite elegir entre el contenido HTML incorporado o las plantillas ya creadas para diseñar rápidamente su correo electrónico. Consulte [Plantillas de contenido](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

La pestaña **[!UICONTROL Learn & support]** le permite acceder fácilmente a la documentación y los tutoriales relacionados.

![](assets/email_designer_home_support.png)

Si no selecciona una plantilla, la página de inicio de Diseñador de correo electrónico también le permite elegir cómo quiere diseñar el contenido en inicio:

* Haga clic en el botón **[!UICONTROL Create]** para comenzar un nuevo contenido desde cero. Consulte [Diseño del contenido de un correo electrónico desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Haga clic en el botón **[!UICONTROL Upload]** para cargar un archivo desde el equipo. Consulte [Importación de contenido desde un archivo](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Haga clic en el botón **[!UICONTROL Import from URL]** para recuperar el contenido existente de una URL. Consulte [Importación de contenido desde una URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminología {#terminology}

**Plantillas**: son estructuras de correo electrónico que se pueden crear y reutilizar para varios envíos.

**Fragmentos**: un fragmento es un componente reutilizable al que se puede hacer referencia en uno o varios correos electrónicos.

**Componentes de estructura**: elementos estructurales que definen el diseño del correo electrónico.

**Componentes de contenido**: son componentes sin procesar y vacíos que se pueden editar una vez colocados en un correo electrónico.

## Prácticas recomendadas para el diseño de contenido {#content-design-best-practices}

Para utilizar correctamente el Diseñador de correo electrónico y crear los mejores correos electrónicos de la manera más sencilla posible, se recomienda aplicar los siguientes principios:

* Utilice estilos en línea en lugar de CSS y CSS independientes en la sección &lt;head> del HTML. Al utilizar el estilo en línea, puede optimizar el almacenamiento y la reutilización de fragmentos de contenido.

   Consulte [Añadir atributos de estilo en línea](../../designing/using/styles.md#adding-inline-styling-attributes).

* Si importa archivos .zip con contenido HTML, utilice CSS normal. No se admiten las hojas de estilo SCSS.

* Configure la marca fácilmente mediante la creación y reutilización de fragmentos de contenido para mantener la coherencia en las campañas de marketing.

   Consulte [Creación de un fragmento de contenido](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Al editar el contenido **del correo electrónico**:

   Previsualice los mensajes antes de enviarlos. Adobe Campaign ofrece una forma de probar el procesamiento de correo electrónico con Litmus. Para obtener más información, consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).

* La metaetiqueta de Remitente del reenvío no es compatible con el Diseñador de correo electrónico.

En la siguiente guía paso a paso de Adobe Campaign se ofrecen más prácticas generales y de diseño sobre los mensajes: [Prácticas recomendadas de envío con Adobe Campaign](../../sending/using/delivery-best-practices.md).

### Actualización de fragmentos {#email-designer-updates}

El Diseñador de correo electrónico está en constante mejora. Si creó contenido de correo electrónico desde cero a partir de una plantilla predeterminada o si creó fragmentos, puede recibir el siguiente mensaje de actualización la próxima vez que abra el contenido:

![](assets/email_designer_fragment_patch_message.png)

Adobe recomienda actualizar el contenido a la versión más reciente para evitar problemas como problemas de colisión con CSS. Haga clic en **[!UICONTROL Update now]**.

Si se produce un error durante la actualización de contenido, compruebe el HTML y corríjalo antes de volver a ejecutar esta actualización.

Cuando se trata de fragmentos, tenga en cuenta lo siguiente:

* Si desea agregar un fragmento a un nuevo correo electrónico o plantilla y recibe este mensaje, primero debe actualizar este fragmento.

* Si tiene varios fragmentos, debe actualizar el fragmento que desee utilizar como contenido de correo electrónico.

* Para evitar el impacto en los mensajes de correo electrónico actuales que aún no están preparados, puede optar por no actualizar algunos de los fragmentos.

* Aún puede enviar correos electrónicos cuando ya esté utilizando un fragmento que no se haya actualizado, pero ese fragmento no se puede editar.

* La actualización de fragmentos utilizados en correos electrónicos que ya están preparados no afecta a esos mensajes.

## Limitaciones del Diseñador de correo electrónico {#email-designer-limitations}

* No se pueden usar los campos de personalización en un fragmento. Para obtener más información sobre fragmentos, consulte [esta sección](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Al editar estilos, solo están disponibles las fuentes web oficialmente admitidas por la mayoría de los clientes de correo electrónico.
* Los estilos no se pueden guardar como un tema para su reutilización futura. Sin embargo, el estilo CSS se puede guardar en una plantilla de contenido o en un correo electrónico. Para obtener más información de los estilos, consulte [esta sección](../../designing/using/styles.md).
* La metaetiqueta de Remitente del reenvío no es compatible con el Diseñador de correo electrónico.
* Los pares sustitutos, caracteres no incluidos en el plano multilingüe básico del conjunto de caracteres Unicode, no se pueden almacenar en 2 bytes (16 bits) y deben codificarse en 2 caracteres UTF-16. Estos caracteres incluyen algunos ideogramas CJK, la mayoría de emojis y algunos idiomas.<br>Estos caracteres pueden provocar algunos problemas de incompatibilidad en el texto dinámico. Debe realizar pruebas sólidas antes de enviar los mensajes.

**Temas relacionados**

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Diseño de una página de aterrizaje](../../channels/using/designing-a-landing-page.md)
* [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md)
* [Creación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)

## Tutorial en vídeo {#video}

Este vídeo ofrece información general sobre el Diseñador de correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/22771?quality=12)

Para la introducción del Diseñador de correo electrónico, consulte este [conjunto de vídeos](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) que explican la funcionalidad general del Diseñador de correo electrónico y cómo diseñar un correo electrónico desde cero o con plantillas

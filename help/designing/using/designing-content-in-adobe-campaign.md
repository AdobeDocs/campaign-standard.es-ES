---
title: Diseño de contenido en Adobe Campaign
description: Utilice el Diseñador de correo electrónico de Campaña para crear correos electrónicos cautivadores personalizados mediante una interfaz de arrastrar y soltar. A partir de una pizarra en blanco, o aprovechando los fragmentos de contenido o las plantillas existentes, diseñe y perfeccione todo el contenido de cada correo electrónico
page-status-flag: never-activated
uuid: 8f73407f-ab90-46bc-aeb6-bd87fcb0404c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: 20800cde-50ad-4d2b-a2f9-812258bec665
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3859c91e4aa083d897c02769495113f62e071f3c
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 4%

---


# Diseñador de correos electrónicos de Campaign{#designing-content-in-adobe-campaign}

Una vez creado un correo electrónico en Adobe Campaign, debe definir su contenido.

El Diseñador de correo electrónico le permite crear cautivadores correos electrónicos personalizados mediante una interfaz de arrastrar y soltar. Ya sea desde una pizarra en blanco o aprovechando los fragmentos de contenido o las plantillas existentes, diseñe y perfeccione todo el contenido de cada correo electrónico, ya sea promocional o transaccional.

Diseñado para ofrecer HTML optimizado para un diseño interactivo, el Diseñador de correo electrónico le permite definir y aplicar fácilmente condiciones de visibilidad y contenido dinámico a un correo electrónico, plantilla o fragmento directamente a través de la interfaz de usuario. Puede alternar sin problemas entre la interfaz de arrastrar y soltar y el código HTML haciendo clic en un botón.

El Diseñador de correo electrónico permite crear plantillas de contenido de correo electrónico y contenido de correo electrónico. Es compatible con correos electrónicos simples, correos electrónicos transaccionales, correos electrónicos de prueba A/B, correos electrónicos multilingües y correos electrónicos recurrentes.

Para empezar a usar el Diseñador de correo electrónico, vea este [conjunto de vídeos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) que explican la funcionalidad general del Diseñador de correo electrónico y cómo diseñar un correo electrónico desde cero o mediante plantillas.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* Para descubrir cómo crear contenido de correo electrónico, consulte [Introducción a Email Designer](../../designing/using/quick-start.md).
* Para obtener una descripción general del Diseñador de correo electrónico, consulte [Uso del Diseñador](../../designing/using/designing-content-in-adobe-campaign.md)de correo electrónico.
* Para obtener más información sobre la creación de contenido:
   * Desde cero, consulte [Diseño de correos electrónicos desde cero](../../designing/using/designing-from-scratch.md).
   * Con el contenido existente, consulte [Diseño con contenido](../../designing/using/using-existing-content.md)existente.
   * Con integraciones de Creative Cloud, consulte Diseño [](../../designing/using/using-integrations.md)de correo electrónico con varias soluciones.
* Para obtener más información sobre Personalización, consulte [Personalización](../../designing/using/personalization.md).

Al crear un correo electrónico, puede elegir utilizar una plantilla predefinida o cargar un contenido existente de otra fuente. Consulte [Selección de un contenido](../../designing/using/using-existing-content.md#selecting-an-existing-content)existente.

Para aumentar la eficacia de sus campañas de marketing, personalice su contenido. Consulte [Inserción de un campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalización y [Añadir un bloque](../../designing/using/personalization.md#adding-a-content-block)de contenido.

También puede definir contenido dinámico que varía según cada perfil. Consulte [Definición de contenido dinámico en un mensaje de correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) y [Definición de contenido dinámico en una página de aterrizaje](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Mejore sus mensajes y páginas de aterrizaje con vínculos e imágenes. Consulte [Inserción de un vínculo](../../designing/using/links.md#inserting-a-link) e [Inserción de imágenes](../../designing/using/images.md#inserting-images).

## Interfaz de Email Designer {#email-designer-interface}

El Diseñador de correo electrónico proporciona muchas opciones que le permiten crear, editar y personalizar todos los aspectos del contenido.

La interfaz se compone de varias áreas que ofrecen diferentes funcionalidades:

![](assets/email_designer_overview.png)

Desde los elementos disponibles en la **paleta** (1), arrastre y suelte los componentes de estructura y los fragmentos de contenido en el **espacio de trabajo** principal (2). Seleccione un componente o elemento en el **espacio de trabajo** (2) y personalice su estilo principal y sus características de visualización en el panel **Configuración** (3).

Acceda a opciones y configuraciones más generales desde la **barra de herramientas** principal (4).

>[!NOTE]
>
>El panel **Configuración** puede moverse a la izquierda según la resolución de pantalla y la visualización.

![](assets/email_designer_toolbar.png)

La barra de herramientas **** contextual de la interfaz del editor oferta varias funcionalidades en función de la zona seleccionada. Contiene botones de acción y botones que permiten cambiar el estilo del texto. Las modificaciones realizadas se aplican siempre a la zona seleccionada.

### Página de inicio de Email Designer {#email-designer-home-page}

Al [crear un correo electrónico](../../channels/using/creating-an-email.md), la **[!UICONTROL Email Designer]** página de inicio se muestra automáticamente al seleccionar el contenido del correo electrónico.

![](assets/email_designer_home_page.png)

La **[!UICONTROL Properties]** ficha permite editar los detalles del correo electrónico, como la etiqueta, la dirección y el nombre del remitente o el asunto del correo electrónico. También puede acceder a esta ficha haciendo clic en la etiqueta de correo electrónico en la parte superior de la pantalla.

![](assets/email_designer_home_properties.png)

La **[!UICONTROL Templates]** ficha le permite elegir entre el contenido HTML incorporado o las plantillas que ya ha creado para diseñar su correo electrónico con rapidez y inicio. Consulte Plantillas [de contenido](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

La ficha **[!UICONTROL Learn & support]** le permite acceder fácilmente a la documentación y los tutoriales relacionados.

![](assets/email_designer_home_support.png)

Si no selecciona una plantilla, la página de inicio de Diseñador de correo electrónico también le permite elegir cómo desea diseñar el contenido en inicio:

* Haga clic en el **[!UICONTROL Create]** botón para inicio de un nuevo contenido desde cero. Consulte [Diseño de contenido de correo electrónico desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Haga clic en el **[!UICONTROL Upload]** botón para cargar un archivo desde el equipo. Consulte [Importación de contenido desde un archivo](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Haga clic en el **[!UICONTROL Import from URL]** botón para recuperar el contenido existente de una URL. Consulte [Importación de contenido desde una dirección URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminología {#terminology}

**Plantillas**: Las plantillas son estructuras de correo electrónico que se pueden crear y reutilizar para varios envíos.

**Fragmentos**: Un fragmento es un componente reutilizable al que se puede hacer referencia en uno o varios correos electrónicos.

**Componentes** de estructura: Elementos estructurales que definen el diseño del correo electrónico.

**Componentes** de contenido: Los componentes de contenido son componentes sin procesar y vacíos que se pueden editar una vez colocados en un mensaje de correo electrónico.

## Content design best practices {#content-design-best-practices}

Para utilizar correctamente el Diseñador de correo electrónico y crear los mejores correos electrónicos de la manera más sencilla posible, se recomienda aplicar los siguientes principios:

* Utilice estilos en línea en lugar de CSS y CSS independientes en la sección &lt;head> del HTML. Al utilizar el estilo en línea, puede optimizar el almacenamiento y la reutilización de fragmentos de contenido.

   Consulte [Añadir atributos](../../designing/using/styles.md#adding-inline-styling-attributes)de estilo en línea.

* Si importa archivos ZIP con contenido HTML, utilice CSS normal. No se admiten las hojas de estilo SCSS.

* Configure la marca fácilmente mediante la creación y reutilización de fragmentos de contenido para mantener la coherencia en las campañas de marketing.

   Consulte [Creación de un fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de contenido.

* Al editar el contenido **del** correo electrónico:

   Previsualización tus mensajes antes de enviarlos. Adobe Campaign oferta una forma de probar el procesamiento por correo electrónico con Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

En la siguiente sección se describen más las prácticas recomendadas generales y de diseño en relación con los mensajes: [Prácticas recomendadas](../../sending/using/delivery-best-practices.md)de envío.

### Actualización de fragmentos {#email-designer-updates}

El Diseñador de correo electrónico está en constante mejora. Si ha creado un contenido de correo electrónico desde cero, a partir de una plantilla lista para usar o si ha creado fragmentos, puede recibir el siguiente mensaje de actualización la próxima vez que abra el contenido:

![](assets/email_designer_fragment_patch_message.png)

Adobe recomienda actualizar el contenido a la versión más reciente para evitar problemas como problemas de colisión con CSS. Haga clic **[!UICONTROL Update now]**.

Si se produce un error durante la actualización de contenido, compruebe el HTML y corríjalo antes de volver a ejecutar esta actualización.

Cuando se trata de fragmentos, tenga en cuenta lo siguiente:

* Si desea agregar un fragmento a un nuevo correo electrónico o plantilla y recibe este mensaje, primero debe actualizar este fragmento.

* Si tiene varios fragmentos, debe actualizar cada fragmento que desee utilizar en un contenido de correo electrónico.

* Para evitar el impacto en los mensajes de correo electrónico actuales que aún no están preparados, puede optar por no actualizar algunos fragmentos.

* Aún puede enviar correos electrónicos cuando ya se esté utilizando un fragmento que no se haya actualizado, pero ese fragmento no se pueda editar.

* La actualización de fragmentos utilizados en correos electrónicos que ya están preparados no afecta a esos mensajes.

## Limitaciones de Email Designer {#email-designer-limitations}

* No se pueden usar campos de personalización en un fragmento. For more on fragments, see [this section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Al editar estilos, solo están disponibles las fuentes web oficialmente admitidas por la mayoría de los clientes de correo electrónico.
* Los estilos no se pueden guardar como un tema para su reutilización futura. Sin embargo, el estilo CSS se puede guardar en una plantilla de contenido o en un correo electrónico. For more on styles, see [this section](../../designing/using/styles.md).

**Temas relacionados**

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Diseño de una página de aterrizaje](../../channels/using/designing-a-landing-page.md)
* [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md)
* [Creación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)

---
title: Acerca del diseño del contenido de la página de aterrizaje
seo-title: Acerca del diseño del contenido de la página de aterrizaje
description: Acerca del diseño del contenido de la página de aterrizaje
seo-description: Obtenga información sobre las características específicas del editor de contenido de la página de aterrizaje.
page-status-flag: nunca activado
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: diseñar
content-type: referencia
topic-tags: editing-landing-page-content
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# Acerca del diseño del contenido de la página de aterrizaje{#about-landing-page-content-design}

Utilice el editor de contenido estándar para crear y modificar el contenido de las páginas de aterrizaje en Adobe Campaign.

Esta sección describe las características específicas del editor de contenido de la página de aterrizaje:

* [Interfaz del editor de contenido de la página de aterrizaje](../../channels/using/landing-page-content-editor-interface.md)
* [Administración de la estructura y el estilo de la página de aterrizaje](../../channels/using/managing-landing-page-structure-and-style.md)
* [Cambio de las propiedades de datos de un formulario de página de aterrizaje](../../channels/using/changing-a-landing-page-form-data-properties.md)

Para obtener más información sobre las acciones comunes a una o varias actividades de marketing, consulte las siguientes secciones:

* Para obtener más información sobre la personalización del contenido de una página de aterrizaje, consulte [Inserción de un campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalización y [Adición de un bloque](../../designing/using/personalization.md#adding-a-content-block)de contenido.
* Para obtener más información sobre la definición de contenido dinámico en una página de aterrizaje, consulte [Definición de contenido dinámico en una página](../../channels/using/defining-dynamic-content-in-a-landing-page.md)de aterrizaje.
* Para obtener más información sobre cómo insertar vínculos en una página de aterrizaje, consulte [Inserción de un vínculo](../../designing/using/links.md#inserting-a-link).
* Para obtener más información sobre cómo insertar imágenes en una página de aterrizaje, consulte [Inserción de imágenes](../../designing/using/images.md).

Compruebe también las prácticas recomendadas [generales para el diseño](../../designing/using/overview.md#content-design-best-practices)de contenido.

>[!NOTE]
>
>Si la instancia se instaló antes de la versión 19.0 de Adobe Campaign Standard, aún tendrá acceso al editor de contenido de correo electrónico heredado. La interfaz, los principios de uso y la configuración son mayormente los mismos que se describen a continuación para las páginas de aterrizaje. Sin embargo, es posible que todas las funciones no estén disponibles ni se mantengan en el editor de contenido de correo electrónico heredado, que ya no se utiliza en la versión 19.0. Para editar rápidamente el contenido del correo electrónico mediante una interfaz de arrastrar y soltar con funciones extendidas, utilice el Diseñador de [correo electrónico](../../designing/using/overview.md).

## Prácticas recomendadas para el diseño de la página de aterrizaje {#landing-pages-best-practices-design}

* Al editar el contenido **de la página** de aterrizaje:

   * Antes de importar una plantilla de página HTML en Adobe Campaign, asegúrese de que la plantilla se abre y se muestra correctamente en los distintos exploradores.
   * Si la página HTML contiene secuencias de comandos JavaScript, deben ejecutarse sin errores fuera del editor. En general, evite utilizar secuencias de comandos en el contenido del mensaje para asegurarse de que los clientes de correo electrónico lo procesan correctamente.
   * Al crear una plantilla, se recomienda agregar un atributo **'type'** a las etiquetas. El editor procesará esta información y ayudará al usuario a vincular un campo de base de datos al campo de formulario al configurar la aplicación Web.
   Ejemplo de código HTML en la plantilla:

   ```
   <input id="email" type="email" name="email"/>
   ```

   La lista oficial de atributos 'type' está disponible en la siguiente dirección: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)
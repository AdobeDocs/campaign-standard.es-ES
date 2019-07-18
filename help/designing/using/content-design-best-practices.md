---
title: Prácticas recomendadas de diseño de contenido
seo-title: Prácticas recomendadas de diseño de contenido
description: Prácticas recomendadas de diseño de contenido
seo-description: Lea estas instrucciones para garantizar la óptima operación del editor.
page-status-flag: no activado nunca
uuid: ad 74 f 49 d -999 f -4140-89 b 0-d 1 ead 8642 d 89
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: about-content-design
discoiquuid: d 33 f 5 f 14-a 4 e 3-4327-bd 16-eb 3135 a 32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

Para garantizar la óptima operación del editor, recomendamos observar las siguientes pautas:

* No se admiten hojas de estilo SCSS. Utilice CSS normal si importa archivos ZIP que contengan su contenido HTML.
* When editing **email content**:

   Previsualice los mensajes antes de enviarlos. Adobe Campaign ofrece una forma de probar el procesamiento por correo electrónico con el Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* When editing **landing page content**:

   * Antes de importar una plantilla de página HTML en Adobe Campaign, asegúrese de que la plantilla se abre y se muestra correctamente en los distintos exploradores.
   * Si la página HTML contiene secuencias de comandos JavaScript, debe ejecutarse sin errores fuera del editor. En general, evite utilizar secuencias de comandos en el contenido del mensaje para asegurarse de que los clientes de correo electrónico las procesen correctamente.
   * When building a template, we recommend adding a **'type'** attribute to  tags. El editor procesará esta información y ayudará al usuario a vincular un campo de base de datos al campo de formulario al configurar la aplicación Web.

      Ejemplo de código HTML en la plantilla:

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

---
title: Adición de contenido dinámico de Target
seo-title: Adición de contenido dinámico de Target
description: Adición de contenido dinámico de Target
seo-description: Descubra cómo agregar contenido dinámico de Adobe Target en una de sus entregas de Adobe Campaign.
page-status-flag: no activado nunca
uuid: b 3 cc 045 f -7924-480 e -8 c 61-8246510 f 3 adb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y objetivo
discoiquuid: 45 ddf 7 b 7-98 f 7-4 fdd-bb 4 a -49 ec 8490 e 877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Adding Target dynamic content{#adding-target-dynamic-content}

Con la integración de Adobe Target, las imágenes dinámicas se pueden agregar a una entrega para personalizar el contenido según las experiencias.

Mientras edita un correo electrónico, puede insertar una imagen dinámica de Adobe Target que cambie según los destinatarios.

Antes de acceder a la imagen en Adobe Campaign, primero debe realizar las siguientes tareas en Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Create one or several [audiences](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), to define the target of your activity.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiencia, debe seleccionar una de las ofertas de redireccionamiento creadas.
* Cree segmentos utilizando información de Adobe Campaign para especificar experiencias. Para utilizar datos de Adobe Campaign en las reglas de selección de la oferta, debe especificar los datos en el rawbox de Adobe Target.

1. Cree una entrega por correo electrónico.
1. When editing the content of an email or a landing page, go to an image block, then select **[!UICONTROL Dynamic image from Adobe Target]** via the contextual menu.

   ![](assets/tar_insert_dynamic_image.png)

1. Seleccione la imagen que aparecerá de forma predeterminada en el correo electrónico. You can directly specify the image URL or select an image shared via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   La integración solo admite imágenes estáticas. El resto del contenido no se puede personalizar.

1. Introduzca el nombre del rawbox especificado en Adobe Target.
1. Si utiliza permisos de Enterprise en la configuración de Adobe Target, agregue la propiedad correspondiente en este campo. Learn more about Target Enterprise permissions in [this page](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Este campo es opcional y no es necesario si no utiliza permisos de Enterprise en Target.
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   Los campos de Adobe Campaign utilizados deben haberse especificado en el rawbox. Aquí, definiremos distintas experiencias según el sexo del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Obtenga una vista previa del mensaje de correo electrónico para ver si, al seleccionar distintos perfiles, la imagen inserta cambios según los parámetros especificados en la actividad de Adobe Target y en Adobe Campaign.

Ahora se puede enviar la entrega que contiene la imagen dinámica. Los resultados se pueden encontrar en Adobe Target.

**Temas relacionados:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Acerca del diseño de contenido de correo electrónico](../../designing/using/about-email-content-design.md)
* [Personalizar imágenes de correo electrónico en](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) vídeo en tiempo real


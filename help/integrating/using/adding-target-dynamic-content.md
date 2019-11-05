---
title: Adición de contenido dinámico de Target
description: Obtenga información sobre cómo añadir contenido dinámico de Adobe Target en una de las entregas de Adobe Campaign.
page-status-flag: nunca activado
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y objetivo
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Adición de contenido dinámico de Target{#adding-target-dynamic-content}

Con la integración de Adobe Target, se pueden añadir imágenes dinámicas a una entrega para personalizar el contenido en función de las experiencias.

Al editar un correo electrónico, puede insertar una imagen dinámica de Adobe Target que cambiará en función de los destinatarios.

Antes de acceder a la imagen en Adobe Campaign, primero se deben realizar las siguientes tareas en Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Cree una o varias [audiencias](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html) para definir el público objetivo de la actividad.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiencia, debe seleccionar una de las ofertas de redireccionamiento creadas.
* Cree segmentos con información de Adobe Campaign para especificar experiencias. Para utilizar datos de Adobe Campaign en las reglas de selección de la oferta, debe especificar los datos en el “rawbox” en Adobe Target.

1. Creación de un envío de correo electrónico.
1. Al editar el contenido de un correo electrónico o una página de aterrizaje, vaya a un bloque de imagen y, a continuación, seleccione **[!UICONTROL Dynamic image from Adobe Target]** mediante el menú contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Seleccione la imagen que aparecerá de forma predeterminada en el correo electrónico. Puede especificar directamente la dirección URL de la imagen o seleccionar una imagen compartida mediante [Recursos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   La integración solo admite imágenes estáticas. El resto del contenido no se puede personalizar.

1. Introduzca el nombre del “rawbox” especificado en Adobe Target.
1. Si utiliza permisos de empresa en la configuración de Adobe Target, añada la propiedad correspondiente en este campo. Obtenga más información sobre los permisos de empresa de Target en [esta página](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Este campo es opcional y no es necesario si no se utilizan permisos de empresa en Target.
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   Los campos de Adobe Campaign utilizados deben haberse especificado en el “rawbox”. Aquí, definiremos diferentes experiencias en función del género del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Obtenga una vista previa del correo electrónico para ver si, al seleccionar distintos perfiles, la imagen insertada cambia según los parámetros especificados en la actividad de Adobe Target y en Adobe Campaign.

Ahora se puede enviar la entrega que contenga la imagen dinámica. Los resultados se pueden encontrar en Adobe Target.

**Temas relacionados:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Acerca del diseño de contenido de correo electrónico](../../designing/using/overview.md)
* [Personalización de imágenes de correo electrónico en vídeo en tiempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real


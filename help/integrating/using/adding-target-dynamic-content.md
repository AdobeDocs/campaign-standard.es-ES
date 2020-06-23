---
title: Adición de contenido dinámico de Target
description: Aprenda a añadir contenido dinámico de Adobe Target en uno de sus envíos de Adobe Campaign.
page-status-flag: never-activated
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 27%

---


# Adición de contenido dinámico de Target{#adding-target-dynamic-content}

Con la integración de Adobe Target, las imágenes dinámicas se pueden añadir a un envío para personalizar el contenido en función de las experiencias.

Durante la edición de un correo electrónico, puede insertar una imagen dinámica desde el Adobe Target que cambiará en función de los destinatarios.

Antes de acceder a la imagen en Adobe Campaign, primero se deben realizar las siguientes tareas en Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Cree una o varias [audiencias](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html) para definir el público objetivo de la actividad.
* Create a [Form-based experience composer](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiencia, debe seleccionar una de las ofertas de redireccionamiento creadas.
* Cree segmentos con información de Adobe Campaign para especificar experiencias. Para utilizar datos de Adobe Campaign en las reglas de selección de la oferta, debe especificar los datos en el “rawbox” en Adobe Target.

1. Creación de una entrega de correo electrónico.
1. Al editar el contenido de un correo electrónico o una página de aterrizaje, vaya a un bloque de imagen y, a continuación, seleccione **[!UICONTROL Dynamic image from Adobe Target]** mediante el menú contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Seleccione la imagen que aparecerá de forma predeterminada en el correo electrónico. Puede especificar directamente la dirección URL de la imagen o seleccionar una imagen compartida mediante [Recursos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   La integración solo admite imágenes estáticas. El resto del contenido no se puede personalizar.

1. Introduzca el nombre del “rawbox” especificado en Adobe Target.
1. Si utiliza permisos de empresa en la configuración de Adobe Target, añada la propiedad correspondiente en este campo. Obtenga más información sobre los permisos de empresa de Target en [esta página](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html). Este campo es opcional y no es necesario si no se utilizan permisos de empresa en Target.
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   Los campos de Adobe Campaign utilizados deben haberse especificado en el “rawbox”. Aquí definiremos diferentes experiencias según el sexo del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Previsualización el correo electrónico para ver si, al seleccionar diferentes perfiles, la imagen insertada cambia según los parámetros especificados en la actividad de Adobe Target y en el Adobe Campaign.

Ahora se puede enviar el envío que contiene la imagen dinámica. Sus resultados se pueden encontrar en Adobe Target.

**Temas relacionados:**

* [Adobe Target Portal](https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html)
* [Acerca del diseño de contenido de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalización de imágenes de correo electrónico en vídeo en tiempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real


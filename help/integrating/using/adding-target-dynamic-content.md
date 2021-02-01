---
solution: Campaign Standard
product: campaign
title: Adición de contenido dinámico de Target
description: Aprenda a añadir contenido dinámico de Adobe Target en uno de sus envíos de Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 3672f0bc4ebc551c4eb34660a3a55d44fa726f1a
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 31%

---


# Adición de contenido dinámico de Target{#adding-target-dynamic-content}

Con la integración con Adobe Target, las imágenes dinámicas se pueden añadir a un envío para personalizar el contenido en función de las experiencias.

Al editar un correo electrónico, puede insertar una imagen dinámica de Adobe Target que cambiará según los destinatarios.

Antes de acceder a la imagen en Adobe Campaign, las siguientes tareas deben realizarse primero en Adobe Target:

* Cree una o varias [ofertas de redireccionamiento](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), en las que debe especificar la dirección URL de la imagen que utilizará.
* Cree una o varias [audiencias](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html) para definir el público objetivo de la actividad.
* Cree una actividad [Compositor de experiencias basadas en formularios](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html), en la que deberá seleccionar un rawbox y especificar varias experiencias, según el número de ofertas de redireccionamiento creadas. Para cada experiencia, debe seleccionar una de las ofertas de redireccionamiento creadas.
* Cree segmentos con información de Adobe Campaign para especificar experiencias. Para utilizar datos de Adobe Campaign en las reglas de selección de la oferta, debe especificar los datos en el “rawbox” en Adobe Target.

1. Creación de una entrega de correo electrónico.
1. Al editar el contenido de un correo electrónico o una página de aterrizaje, vaya a un bloque de imagen y, a continuación, seleccione **[!UICONTROL Dynamic image from Adobe Target]** mediante el menú contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Seleccione la imagen que aparecerá de forma predeterminada en el correo electrónico. Puede especificar directamente la dirección URL de la imagen o seleccionar una imagen compartida mediante [Recursos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   La integración solo admite imágenes estáticas. El resto del contenido no se puede personalizar.

1. Introduzca el nombre del “rawbox” especificado en Adobe Target.
1. Si utiliza permisos de empresa en la configuración de Adobe Target, añada la propiedad correspondiente en este campo. Obtenga más información sobre los permisos de empresa de Target en [esta página](https://docs.adobe.com/content/help/es-ES/target/using/administer/manage-users/enterprise/properties-overview.html). Este campo es opcional y no es necesario si no se utilizan permisos de empresa en Target.
1. En **[!UICONTROL Additional decision parameters]**, especifique la asignación entre los campos definidos en los segmentos de Adobe Target y los campos de Adobe Campaign.

   Los campos de Adobe Campaign utilizados deben haberse especificado en el “rawbox”. Aquí definiremos diferentes experiencias según el sexo del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Previsualización el correo electrónico para ver si, al seleccionar diferentes perfiles, la imagen insertada cambia según los parámetros especificados en la actividad de Adobe Target y en Adobe Campaign.

Ahora se puede enviar el envío que contiene la imagen dinámica. Sus resultados se pueden encontrar en Adobe Target.

**Temas relacionados:**

* [Adobe Target Portal](https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html)
* [Acerca del diseño de contenido de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalización de imágenes de correo electrónico en ](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) tiempo real


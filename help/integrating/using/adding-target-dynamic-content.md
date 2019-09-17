---
title: Adición de contenido dinámico de Target
seo-title: Adición de contenido dinámico de Target
description: Adición de contenido dinámico de Target
seo-description: Obtenga información sobre cómo añadir contenido dinámico de Adobe Target en una de las entregas de Adobe Campaign.
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
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Adición de contenido dinámico de Target{#adding-target-dynamic-content}

Con la integración de Adobe Target, se pueden añadir imágenes dinámicas a una entrega para personalizar el contenido en función de las experiencias.

Al editar un correo electrónico, puede insertar una imagen dinámica de Adobe Target que cambiará en función de los destinatarios.

Antes de acceder a la imagen en Adobe Campaign, primero se deben realizar las siguientes tareas en Adobe Target:

* Cree una o varias ofertas [de](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)redireccionamiento, en las que deberá especificar la dirección URL de la imagen que utilizará.
* Cree una o varias [audiencias](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)para definir el objetivo de la actividad.
* Cree una actividad de compositor [de experiencias basadas en](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) formularios, en la que deberá seleccionar un rawbox y especificar varias experiencias, según el número de ofertas de redireccionamiento creadas. Para cada experiencia, debe seleccionar una de las ofertas de redireccionamiento creadas.
* Cree segmentos con información de Adobe Campaign para especificar experiencias. Para utilizar datos de Adobe Campaign en las reglas de selección de la oferta, debe especificar los datos en el rawbox de Adobe Target.

1. Cree un envío de correo electrónico.
1. Al editar el contenido de un correo electrónico o una página de aterrizaje, vaya a un bloque de imagen y, a continuación, seleccione **[!UICONTROL Dynamic image from Adobe Target]** mediante el menú contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Seleccione la imagen que aparecerá de forma predeterminada en el correo electrónico. Puede especificar directamente la dirección URL de la imagen o seleccionar una imagen compartida mediante [Recursos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   La integración solo admite imágenes estáticas. El resto del contenido no se puede personalizar.

1. Escriba el nombre del rawbox especificado en Adobe Target.
1. Si utiliza permisos de Enterprise en la configuración de Adobe Target, agregue la propiedad correspondiente en este campo. Obtenga más información sobre los permisos de Target Enterprise en [esta página](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Este campo es opcional y no es obligatorio si no utiliza permisos de Enterprise en Target.
1. En **[!UICONTROL Additional decision parameters]**, especifique la asignación entre los campos definidos en los segmentos de Adobe Target y los campos de Adobe Campaign.

   Los campos de Adobe Campaign utilizados deben haberse especificado en el rawbox. Aquí, definiremos diferentes experiencias en función del género del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Obtenga una vista previa del correo electrónico para ver si, al seleccionar distintos perfiles, la imagen insertada cambia según los parámetros especificados en la actividad de Adobe Target y en Adobe Campaign.

Ahora se puede enviar la entrega que contenga la imagen dinámica. Los resultados se pueden encontrar en Adobe Target.

**Temas relacionados:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Acerca del diseño de contenido de correo electrónico](../../designing/using/overview.md)
* [Personalización de imágenes de correo electrónico en vídeo en tiempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real


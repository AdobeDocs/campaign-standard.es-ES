---
solution: Campaign Standard
product: campaign
title: Acerca del servicio Audience Destinations
description: Obtenga más información sobre el servicio Audience Destinations.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# Acerca del servicio Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Es necesario que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Mejore las experiencias de sus consumidores aprovechando [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) para crear audiencias con un público objetivo muy preciso basadas en conjuntos de datos grandes y complejos. Adobe Experience Platform consolida los datos de perfil, comportamiento y multientidad en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, lo que le permite administrar de forma eficaz sus experiencias con los clientes.

A continuación, Adobe Campaign Standard utilizará el servicio **Audience Destinations** para recuperar una colección de perfiles, conocidos como **Audiences**, de Adobe Experience Platform para programas de campaña multicanal o de varios canales.

**** Las audiencias se crean creando por primera vez  **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, perfiles, eventos, datos de varias entidades) dentro de un perfil de cliente de Adobe Experience Platform para crear un objetivo multidimensional. En estos documentos dedicados se hace referencia a los conceptos globales sobre Perfil del cliente en tiempo real y Servicios de segmentación:

* [Resumen del perfil del cliente en tiempo real](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Información general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Una vez creado un segmento, puede activarlo como audiencia para un envío en [Flujos de trabajo de Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Además, puede utilizar datos contextuales de Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) y añadir contenido dinámico a sus campañas.

![](assets/do-not-localize/how-to-video.png) Los vídeos explicativos también están disponibles en  [esta sección](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html).

Términos empleados en estas secciones:

* **Perfil**: Perfil es un modelo de datos estándar de Experience Platform que se utiliza para definir atributos de los consumidores. Un perfil también puede ser un agregado de datos de evento y atributos relacionados con una persona o dispositivo.

   Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: Conjunto de reglas que define un subconjunto de perfiles de la base de datos mediante atributos y datos de evento.

   Ejemplo: &quot;Hombres > 50 años&quot;.

* **Audiencia**: Colección de perfiles que cumplen las reglas de segmentos.

   Ejemplo: Lista de perfiles correspondientes a todos los hombres > 50 años de edad en la base de datos.

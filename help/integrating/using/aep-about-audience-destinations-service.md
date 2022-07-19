---
title: Acerca del servicio Audience Destinations
description: Obtenga más información sobre el servicio Audience Destinations.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Acerca del servicio Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Es necesario que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.

Aproveche las experiencias de sus consumidores aprovechando el [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) para crear audiencias con objetivos muy precisos basadas en conjuntos de datos grandes y complejos. Adobe Experience Platform consolida los datos de perfil, comportamiento y de varias entidades en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, lo que le permite administrar de forma eficaz las experiencias de sus clientes.

Adobe Campaign Standard utilizará la variable **Destinos de audiencia** para recuperar una colección de perfiles, conocidos como **Audiencias**, de Adobe Experience Platform para programas de campaña multicanal o de varios pasos.

**Audiencias** se crean por primera vez **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, perfil, evento, datos de varias entidades) dentro de un perfil de cliente de Adobe Experience Platform para crear un objetivo multidimensional. En estos documentos dedicados se hace referencia a los conceptos globales sobre Perfil del cliente en tiempo real y Servicios de segmentación:

* [Resumen del perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Información general del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Una vez creado un segmento, puede activarlo como audiencia para un envío en [flujos de trabajo de Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Además, puede utilizar datos contextuales de Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) y añada contenido dinámico a sus campañas.

![](assets/do-not-localize/how-to-video.png) Los vídeos explicativos también están disponibles en [esta sección](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Términos empleados en estas secciones:

* **Perfil**: El perfil es un modelo de datos estándar del Experience Platform que se utiliza para definir los atributos de los consumidores. Un perfil también puede ser un agregado de datos de evento y atributos relacionados con una persona o dispositivo.

   Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: Conjunto de reglas que define un subconjunto de perfiles de la base de datos mediante atributos y datos de evento.

   Ejemplo: &quot;Hombres > 50 años&quot;.

* **Audiencia**: Colección de perfiles que cumplen las reglas de segmentos.

   Ejemplo: Lista de perfiles correspondientes a todos los hombres > 50 años de edad en la base de datos.

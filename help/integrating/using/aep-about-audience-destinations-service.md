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
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 4%

---

# Acerca del servicio Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations ya no se utiliza. Las funciones obsoletas siguen estando disponibles, pero no se pueden mejorar ni admitir. Obtenga más información [en esta página](../../rn/using/deprecated-features.md)

Potencie las experiencias de sus consumidores aprovechando el [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) para crear audiencias con objetivos muy precisos basadas en conjuntos de datos grandes y complejos. Adobe Experience Platform consolida los datos de perfil, comportamiento y de varias entidades en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, lo que le permite administrar de forma eficaz sus experiencias con los clientes.

A continuación, Adobe Campaign Standard utilizará **Destinos de audiencia** para recuperar una colección de perfiles, conocida como **Audiencias**, de Adobe Experience Platform para programas de campañas de varios pasos o canales cruzados.

**Audiencias** se crean mediante la primera compilación **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, datos de perfil, evento, de varias entidades) dentro de un perfil de cliente desde Adobe Experience Platform para crear un objetivo multidimensional. Se hace referencia a los conceptos globales en Real-time Customer Profile y Segmentation Services en estos documentos dedicados:

* [Resumen del perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Resumen del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Una vez creado un segmento, puede activarlo como audiencia para un envío en [Flujos de trabajo de Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Además, puede utilizar datos contextuales desde Adobe Experience Platform para lo siguiente [personalizar](../../integrating/using/aep-personalizing-campaigns.md) y agregue contenido dinámico a sus campañas.

![](assets/do-not-localize/how-to-video.png) Los vídeos de procedimientos también están disponibles en [esta sección](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Términos utilizados en estas secciones:

* **Perfil**: el perfil es un modelo de datos estándar Experience Platform que se utiliza para definir los atributos de los consumidores. Un perfil también puede ser una suma de datos de evento y atributos relacionados con una persona o dispositivo.

  Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: conjunto de reglas que define un subconjunto de perfiles de la base de datos, utilizando atributos y datos de evento.

  Ejemplo: &quot;Varones > 50 años&quot;.

* **Audiencia**: Una colección de perfiles que cumplen las reglas de los segmentos.

  Ejemplo: Lista de perfiles correspondientes a todos los hombres > 50 años en la base de datos.

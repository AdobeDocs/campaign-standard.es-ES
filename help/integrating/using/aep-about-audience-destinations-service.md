---
title: Acerca del servicio Audience Destinations
description: Obtenga más información sobre el servicio Audience Destinations.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%
---
# Acerca del servicio Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations ya no se utiliza. Las funciones obsoletas siguen estando disponibles, pero no se pueden mejorar ni admitir. Más información [en esta página](../../rn/using/deprecated-features.md)

Habilite sus experiencias como consumidor aprovechando [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=es) para crear audiencias con un alto nivel de segmentación basadas en conjuntos de datos grandes y complejos. Adobe Experience Platform consolida los datos de perfil, comportamiento y de varias entidades en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, lo que le permite administrar de forma eficaz sus experiencias con los clientes.

Adobe Campaign Standard usará el servicio **Destinos de audiencia** para recuperar una colección de perfiles, conocidos como **Audiencias**, de Adobe Experience Platform para programas de campañas en canales múltiples o de varios pasos.

Las **audiencias** se crean al generar primero **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, perfil, evento, datos de varias entidades) dentro de un perfil de cliente desde Adobe Experience Platform para crear un destino multidimensional. Se hace referencia a los conceptos globales en Real-time Customer Profile y Segmentation Services en estos documentos dedicados:

* [Resumen del perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es)
* [Resumen del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es)

Una vez creado un segmento, puede activarlo como audiencia para una entrega en [flujos de trabajo de Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Además, puedes usar datos contextuales de Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) y agregar contenido dinámico a tus campañas.

![](assets/do-not-localize/how-to-video.png) Los vídeos de procedimientos también están disponibles en [esta sección](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=es).

Términos utilizados en estas secciones:

* **Perfil**: el perfil es un modelo de datos estándar de Experience Platform que se usa para definir atributos de consumidores. Un perfil también puede ser una suma de datos de evento y atributos relacionados con una persona o dispositivo.

  Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: conjunto de reglas que define un subconjunto de perfiles de la base de datos, utilizando atributos y datos de evento.

  Ejemplo: &quot;Varones > 50 años&quot;.

* **Audiencia**: Una colección de perfiles que cumplen las reglas del segmento.

  Ejemplo: Lista de perfiles correspondientes a todos los hombres > 50 años en la base de datos.

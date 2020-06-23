---
title: Acerca del servicio Audience Destinations
description: Obtenga más información sobre el servicio Audiencia Destinations.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: be7ab90583e9c6472fd2c86082e832432d0a32b9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Acerca del servicio Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>El servicio Destinos de Audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Potencie las experiencias de los consumidores aprovechando el [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) para crear audiencias con objetivos muy precisos basadas en conjuntos de datos grandes y complejos. El Adobe Experience Platform consolida los datos de perfil, comportamiento y multientidad en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, permitiéndole administrar eficazmente sus experiencias con el cliente.

Adobe Campaign Standard utilizará entonces el servicio de **Audiencia Destinos** para recuperar una colección de perfiles, conocidos como **Audiencias**, de Adobes Experience Platform para programas de campaña de varios pasos y/o canales cruzados.

**Las Audiencias** se crean mediante la primera generación de **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, perfil, evento, datos de varias entidades) dentro de un perfil del cliente desde el Adobe Experience Platform para crear un destinatario multidimensional. En estos documentos específicos se hace referencia a los conceptos globales sobre los servicios de Perfil y segmentación de clientes en tiempo real:

* [Información general sobre el Perfil del cliente en tiempo real](https://docs.adobe.com/content/help/es-ES/experience-platform/profile/home.html)
* [Descripción general del servicio de segmentación](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Una vez creado un segmento, puede activarlo como audiencia para un envío en flujos de trabajo [de](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Además, puede utilizar datos contextuales del Adobe Experience Platform para [personalizar](../../automating/using/aep-personalizing-campaigns.md) y agregar contenido dinámico a sus campañas.

Los vídeos de procedimientos también están disponibles en [esta sección](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Términos utilizados en estas secciones:

* **Perfil**: Perfil es un modelo de datos estándar de Experience Platform que se utiliza para definir los atributos de los consumidores. Un perfil también puede ser un acumulado de datos de evento y atributos relacionados con una persona o un dispositivo.

   Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: Conjunto de reglas que define un subconjunto de perfiles de la base de datos, utilizando atributos y datos de evento.

   Ejemplo: &quot;Hombres mayores de 50 años&quot;.

* **Audiencia**: Colección de perfiles que cumplen las reglas de segmentos.

   Ejemplo: Lista de perfiles correspondientes a todos los varones mayores de 50 años en su base de datos.

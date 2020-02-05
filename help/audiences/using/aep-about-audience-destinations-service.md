---
title: Acerca del servicio Destinos de audiencia
description: Obtenga más información sobre el servicio Audience Destinations.
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
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# Acerca del servicio Destinos de audiencia {#about-audiences}

>[!IMPORTANT]
>
>El servicio Destinos de audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Potencie las experiencias de sus clientes aprovechando la plataforma [de experiencias de](https://www.adobe.io/apis/experienceplatform/home.html) Adobe (AEP) para crear audiencias con un público objetivo muy preciso basadas en conjuntos de datos grandes y complejos. Adobe Experience Platform consolida los datos de perfil, comportamiento y multientidad en fuentes en línea y sin conexión, incluido Adobe Analytics, para ayudarle a crear una vista de 360 grados de su cliente, permitiéndole administrar de forma eficaz sus experiencias con el cliente.

A continuación, Adobe Campaign Standard utilizará el servicio **Destinos** de audiencia para recuperar una colección de perfiles, conocidos como **Audiencias**, de AEP para programas de campaña de varios pasos o canales.

**Las audiencias** se crean creando primero **segmentos**, que son esencialmente un conjunto de reglas basadas en prácticamente cualquier variable (por ejemplo, perfil, evento, datos de varias entidades) dentro de un perfil de cliente de AEP para crear un objetivo multidimensional. En [estos documentos](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)dedicados se hace referencia a los conceptos globales de los servicios de perfil y segmentación unificados.

Una vez creado un segmento, puede activarlo como audiencia para una entrega en flujos de trabajo [de](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Además, puede utilizar datos contextuales de la plataforma Adobe Experience para [personalizar](../../automating/using/aep-personalizing-campaigns.md) y agregar contenido dinámico a sus campañas.

Los vídeos de procedimientos también están disponibles en [esta sección](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Términos utilizados en estas secciones:

* **Perfil**: Profile es un modelo de datos estándar de la plataforma de experiencia que se utiliza para definir atributos de los consumidores. Un perfil también puede ser un agregado de datos de eventos y atributos relacionados con una persona o dispositivo.

   Ejemplo: &quot;John Doe es un hombre de 55 años&quot;.

* **Segmento**: Conjunto de reglas que define un subconjunto de perfiles de la base de datos, utilizando atributos y datos de eventos.

   Ejemplo: &quot;Hombres mayores de 50 años&quot;.

* **Audiencia**: Colección de perfiles que cumplen las reglas de segmentos.

   Ejemplo: Lista de perfiles correspondientes a todos los hombres mayores de 50 años en la base de datos.

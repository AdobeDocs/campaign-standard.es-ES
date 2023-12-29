---
title: Acerca del conector de datos de Adobe Experience Platform
description: Administre esquemas XDM para que los datos del Campaign Standard estén disponibles en Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# Acerca del conector de datos de Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform ya no se utiliza. Las funciones obsoletas siguen estando disponibles, pero no se pueden mejorar ni admitir. Más información [en esta página](../../rn/using/deprecated-features.md)

El conector de datos de Adobe Experience Platform ayuda a los clientes existentes a ofrecer sus datos en Adobe Experience Platform asignando datos XTK (datos incorporados en Campaign) a datos del modelo de datos de experiencia (XDM) en Adobe Experience Platform.

Tenga en cuenta que el conector es **unidireccional** y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían desde Adobe Experience Platform a Adobe Campaign Standard.

El Conector de datos de Adobe Experience Platform está diseñado para **ingenieros de datos** que comprendan los recursos personalizados de Adobe Campaign Standard y comprendan cómo debe estar el esquema de datos general del cliente dentro de Adobe Experience Platform.

En las siguientes secciones se describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform. Esto comienza con la creación de un esquema XDM y un conjunto de datos.

![](assets/do-not-localize/how-to-video.png) [Descubra esta funcionalidad en vídeo](#video)

>[!NOTE]
>Una vez configurado el conector de datos de Adobe Experience Platform y que los datos se han introducido correctamente en Adobe Experience Platform, debe habilitar el conjunto de datos para que los datos se incluyan en el perfil del cliente en tiempo real.
>
>Esto se puede realizar a través de las API o de la interfaz de Adobe Experience Platform. Para obtener más información, consulte la documentación específica:
>
>* [Habilitar un conjunto de datos para el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [Configuración de un conjunto de datos para el perfil del cliente en tiempo real y el servicio de identidad mediante API](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## Conceptos clave {#key-concepts}

* La asignación predeterminada solo está disponible para campos que se proporcionan en Campaign Standard de forma predeterminada. Para ingerir todos los campos y recursos personalizados, cada cliente debe definir su propia asignación.

* Adobe Experience Platform Data Connector insertará datos de perfil a través de la plataforma a intervalos regulares&#x200B; La duración del intervalo es de 15 minutos. Este valor se puede modificar utilizando [API de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* El ingeniero de datos puede publicar, modificar y pausar la asignación de Campaign a Adobe Experience Platform.

* Se puede asignar cualquier dimensión de segmentación. La recomendación es tener una sola asignación para todos los campos en una sola dimensión de segmentación.

* Todas las actualizaciones de perfil, incluidas las opciones de inclusión/exclusión de canales, forman parte de la actualización por lotes.

* Cualquier cambio de esquema de Adobe Campaign Standard o XDM debe reasignarse manualmente&#x200B;

* Los datos de registro de seguimiento y registro de banda ancha se incorporan automáticamente a Adobe Experience Platform como eventos de experiencia. Esta ingesta se transmite en tiempo real a Adobe Experience Platform.

* El servicio de ID de Experience Cloud (ECID) es un identificador de dispositivo que se envía de forma predeterminada con los eventos de experiencia.

  Se trata de un ID único y persistente asignado a un visitante que el servicio de ID de Platform puede utilizar para identificar el mismo visitante y sus datos en diferentes soluciones de Experience Cloud. Para obtener más información, consulte [Ayuda del servicio de identidad de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

  >[!NOTE]
  >
  >Tenga en cuenta que, si dos o más perfiles comparten un mismo dispositivo, el ECID sería el mismo para estos dos perfiles en el servicio de identidad unificado.

## Limitaciones {#limitations}

* No se admite la transferencia de eventos de suscripción de forma predeterminada. Para transferir eventos de suscripción, puede crear el XDM y el conjunto de datos correspondientes en Adobe Experience Platform y, a continuación, configurar una asignación de datos personalizada para estos datos.

* En cuanto a las solicitudes de privacidad (tanto acciones de acceso como de eliminación), los clientes deben realizar solicitudes independientes a través de [Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): uno para Campaign y otro para Adobe Experience Platform. Para obtener más información, consulte [Acerca de las solicitudes de privacidad](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=es#getting-started) y [Administración de solicitudes de privacidad](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) en Campaign.

* Para cada campo XDM, el etiquetado DULE debe realizarse en Adobe Experience Platform. Es responsabilidad del cliente aplicar las etiquetas DULE.

* Las restricciones en las acciones de marketing solo se aplican después de aplicar las etiquetas DULE en Adobe Experience Platform. Antes de eso, todos los datos están disponibles para todos los tipos de acciones de marketing.

* Cada 15 minutos, el trabajo por lotes se está ejecutando e identifica los registros que han cambiado desde el último lote. Si todos los registros cambian al mismo tiempo, podría aparecer un cuello de botella de rendimiento para administrar la ingesta de todos los perfiles

## Tutorial en vídeo {#video}

Este vídeo proporciona información general sobre el conector de datos de Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Hay disponibles más vídeos relacionados con el conector de datos de Adobe Experience Platform [aquí](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

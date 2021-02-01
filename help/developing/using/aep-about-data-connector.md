---
solution: Campaign Standard
product: campaign
title: Acerca de Adobe Experience Platform Data Connector
description: Administre esquemas XDM para que los datos del Campaign Standard estén disponibles en Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 6%

---


# Acerca de Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.

El conector de datos de Adobe Experience Platform ayuda a los clientes existentes a que sus datos estén disponibles en Adobe Experience Platform asignando datos XTK (datos ingestados en Campaña) a datos del modelo de datos de experiencia (XDM) en Adobe Experience Platform.

Tenga en cuenta que el conector es **unidireccional** y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían de Adobe Experience Platform a Adobe Campaign Standard.

El conector de datos de Adobe Experience Platform está diseñado para **ingenieros de datos** que entienden los recursos personalizados de Adobe Campaign Standard y comprenden cómo debe estar el esquema de datos general del cliente dentro de Adobe Experience Platform.

Las secciones siguientes describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform. Esto inicio con la creación de un esquema XDM y un conjunto de datos.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#video)

>[!NOTE]
>Una vez configurado el conector de datos de Adobe Experience Platform y que los datos se transfieren correctamente a Adobe Experience Platform, debe habilitar el conjunto de datos para que los datos se incluyan en el Perfil del cliente en tiempo real.
>
>Esto se puede realizar a través de las API o de la interfaz de Adobe Experience Platform. Para obtener más información, consulte las documentaciones dedicadas:
>
>* [Habilitar un conjunto de datos para el Perfil del cliente en tiempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar un conjunto de datos para el Perfil de clientes en tiempo real y el servicio de identidad mediante API](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Conceptos clave {#key-concepts}

* La asignación de fuera de la caja solo está disponible para los campos que se proporcionan en Campaign Standard de forma predeterminada. Para ingerir todos los campos y recursos personalizados, cada cliente debe definir su propia asignación.

* Adobe Experience Platform Data Connector insertará datos de perfil a través de la plataforma a intervalos regulares. &#x200B; La duración del intervalo es de 15 minutos. Este valor se puede modificar mediante [API de Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* El ingeniero de datos puede publicar, modificar y pausar la asignación de Campaña a Adobe Experience Platform.

* Se puede asignar cualquier dimensión de segmentación. Se recomienda tener una sola asignación para todos los campos de una sola dimensión de segmentación.

* Todas las actualizaciones de perfil, incluidas las exclusiones y exclusiones de canal, forman parte de la actualización por lotes.

* Cualquier cambio de esquema de Adobe Campaign Standard o XDM debe reasignarse manualmente. &#x200B;

* El seguimiento de los datos de registro y Broadlog se transfiere automáticamente a Adobe Experience Platform como Eventos de experiencias. Esta ingesta se transmite en tiempo real a Adobe Experience Platform.

* El servicio de ID de Experience Cloud (ECID) es un identificador de dispositivo que se envía de forma predeterminada con Eventos de experiencia.

   Es un ID único y persistente asignado a un visitante, que puede utilizar el servicio de identidad de plataforma para identificar el mismo visitante y sus datos en distintas soluciones de Experience Cloud. Para obtener más información sobre esto, consulte la [Ayuda del servicio de identidad de Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html).

   >[!NOTE]
   >
   >Tenga en cuenta que, si dos o más perfiles comparten un mismo dispositivo, el ECID será el mismo para estos dos perfiles en el servicio de identidad unificada.

## Limitaciones {#limitations}

* No se admite la transferencia predeterminada de eventos de suscripción. Para transferir eventos de suscripción, puede crear el XDM y el conjunto de datos correspondientes en Adobe Experience Platform y, a continuación, configurar una asignación de datos personalizada para estos datos.

* En cuanto a las solicitudes de privacidad (acciones de acceso y eliminación), los clientes deben realizar solicitudes independientes a través de [Privacy Core Service](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): una para Campaña y otra para Adobe Experience Platform. Para obtener más información sobre esto, consulte [Acerca de las solicitudes de privacidad](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=es#getting-started) y [Administración de solicitudes de privacidad](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) en Campaña.

* Para cada campo XDM, el etiquetado DULE debe realizarse en Adobe Experience Platform. Es responsabilidad del cliente aplicar etiquetas DULE.

* Las restricciones de las acciones de marketing solo se aplican después de que las etiquetas DULE se apliquen en Adobe Experience Platform. Antes de eso, todos los datos están disponibles para todos los tipos de acciones de mercadotecnia.

* Cada 15 minutos, el trabajo por lotes se ejecuta e identifica los registros que han cambiado desde el último lote. Si todos los registros cambian con la misma marca de tiempo, podría aparecer un cuello de botella de rendimiento para administrar la ingestión de todos los perfiles

## Vídeo tutorial {#video}

Este vídeo proporciona información general sobre el conector de datos de Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Hay disponibles más vídeos relacionados con el conector de datos de Adobe Experience Platform [aquí](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

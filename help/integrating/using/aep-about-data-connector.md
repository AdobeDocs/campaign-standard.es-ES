---
solution: Campaign Standard
product: campaign
title: Acerca de Adobe Experience Platform Data Connector
description: Administre esquemas XDM para que los datos de Campaign Standard estén disponibles en Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 6%

---


# Acerca de Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector está actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Es necesario que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Adobe Experience Platform Data Connector ayuda a los clientes existentes a poner sus datos a disposición en Adobe Experience Platform asignando datos XTK (datos incorporados en Campaign) a datos del modelo de datos de Experience (XDM) en Adobe Experience Platform.

Tenga en cuenta que el conector es **unidireccional** y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían de Adobe Experience Platform a Adobe Campaign Standard.

Adobe Experience Platform Data Connector está diseñado para **ingenieros de datos** que comprenden los recursos personalizados de Adobe Campaign Standard y comprenden cómo debe estar el esquema de datos general del cliente dentro de Adobe Experience Platform.

Las secciones siguientes describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform. Esto comienza con la creación de un esquema XDM y un conjunto de datos.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#video)

>[!NOTE]
>Una vez configurado el conector de datos de Adobe Experience Platform y que los datos se incorporan correctamente en Adobe Experience Platform, debe habilitar el conjunto de datos para que los datos se incluyan en el perfil del cliente en tiempo real.
>
>Esto se puede realizar a través de las API o la interfaz de Adobe Experience Platform. Para obtener más información, consulte la documentación dedicada:
>
>* [Habilitar un conjunto de datos para el perfil del cliente en tiempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configuración de un conjunto de datos para el perfil del cliente en tiempo real y el servicio de identidad mediante API](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Conceptos clave {#key-concepts}

* La asignación predeterminada solo está disponible para los campos que se proporcionan en Campaign Standard de forma predeterminada. Para ingerir todos los campos y recursos personalizados, cada cliente debe definir su propia asignación.

* Adobe Experience Platform Data Connector insertará datos de perfil en la plataforma a intervalos regulares &#x200B;. La duración del intervalo es de 15 minutos. Este valor se puede modificar utilizando [API de Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* El ingeniero de datos puede publicar, modificar y pausar la asignación de Campaign a Adobe Experience Platform.

* Se puede asignar cualquier dimensión de segmentación. La recomendación es tener una sola asignación para todos los campos en una sola dimensión de segmentación.

* Todas las actualizaciones de perfil, incluidas las exclusiones y exclusiones del canal, forman parte de la actualización por lotes.

* Cualquier cambio en el esquema de Adobe Campaign Standard o XDM debe reasignarse manualmente &#x200B;

* Los datos de registro de seguimiento y Broadlog se introducen automáticamente en Adobe Experience Platform como eventos de experiencia. Esta ingesta se transmite en tiempo real a Adobe Experience Platform.

* El servicio de Experience Cloud ID (ECID) es un identificador de dispositivo que se envía de forma predeterminada con Experience Events.

   Se trata de un ID único y persistente asignado a un visitante, que el servicio de ID de plataforma puede usar para identificar al mismo visitante y sus datos en diferentes soluciones de Experience Cloud. Para obtener más información, consulte la [Ayuda del servicio de identidad de Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html).

   >[!NOTE]
   >
   >Tenga en cuenta que, si dos o más perfiles comparten un mismo dispositivo, el ECID sería el mismo para estos dos perfiles en el servicio de identidad unificada.

## Limitaciones {#limitations}

* No se admite la transferencia predeterminada de eventos de suscripción. Para transferir eventos de suscripción, puede crear el XDM y el conjunto de datos correspondientes en Adobe Experience Platform y, a continuación, configurar una asignación de datos personalizada para estos datos.

* En cuanto a las solicitudes de privacidad (tanto las acciones de Acceso como las de Eliminación), los clientes deben colocar solicitudes independientes a través del [Servicio principal de privacidad](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): una para Campaign y otra para Adobe Experience Platform. Para obtener más información, consulte [Acerca de las solicitudes de privacidad](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=es#getting-started) y [Administración de solicitudes de privacidad](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) en Campaign.

* Para cada campo XDM, el etiquetado DULE debe realizarse en Adobe Experience Platform. Es responsabilidad del cliente aplicar etiquetas DULE.

* Las restricciones en las acciones de marketing solo son aplicables después de aplicar las etiquetas DULE en Adobe Experience Platform. Antes de eso, todos los datos están disponibles para todos los tipos de acciones de marketing.

* Cada 15 minutos, el trabajo por lotes se ejecuta e identifica los registros que han cambiado desde el último lote. Si todos los registros cambian con la misma marca de tiempo, podría aparecer un cuello de botella en el rendimiento para administrar la ingesta de todos los perfiles

## Vídeo tutorial {#video}

Este vídeo proporciona información general sobre el conector de datos de Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Los vídeos adicionales relacionados con el conector de datos de Adobe Experience Platform están disponibles [aquí](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
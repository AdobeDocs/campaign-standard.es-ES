---
title: Acerca de Adobe Experience Platform Data Connector
description: Administre esquemas XDM para que los datos del Campaign Standard estén disponibles en Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9388df151eabbc6f63461e854d0276c14d9ef93d

---


# Acerca de Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>El conector de datos de la plataforma de Adobe Experience está actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

El conector de datos de la plataforma Adobe Experience Platform ayuda a los clientes existentes a poner sus datos a disposición en la plataforma Adobe Experience, asignando datos XTK (datos ingestados en Campaña) a datos del modelo de datos de experiencia (XDM) en la plataforma Adobe Experience.

Tenga en cuenta que el conector es **unidireccional** y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían desde Adobe Experience Platform a Adobe Campaign Standard.

El conector de datos de la plataforma de experiencia de Adobe está dirigido a ingenieros **de** datos que entienden los recursos personalizados de Adobe Campaign Standard y que entienden cómo debe estar el esquema general de datos del cliente en Adobe Experience Platform.

Las secciones siguientes describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform. Esto inicio con la creación de un esquema XDM y un conjunto de datos.

Los vídeos de procedimientos también están disponibles en [esta página](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Una vez configurado el conector de datos de la plataforma Adobe Experience Platform y que los datos se incorporan correctamente a la plataforma Adobe Experience, debe habilitar el conjunto de datos para que los datos se incluyan en el Perfil del cliente en tiempo real.
>
>Esto se puede realizar a través de las API o de la interfaz de Adobe Experience Platform. Para obtener más información, consulte las documentaciones dedicadas:
>
>* [Habilitar un conjunto de datos para el Perfil del cliente en tiempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar un conjunto de datos para el Perfil de clientes en tiempo real y el servicio de identidad mediante API](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Conceptos clave {#key-concepts}

* La asignación de fuera de la caja solo está disponible para los campos que se proporcionan en Campaign Standard de forma predeterminada. Para ingerir todos los campos y recursos personalizados, cada cliente debe definir su propia asignación.

* El conector de datos de la plataforma Adobe Experience Platform insertará datos de perfil a través de la plataforma a intervalos regulares. &#x200B; La duración del intervalo es de 15 mn. Este valor se puede modificar con las API de [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* El ingeniero de datos puede publicar, modificar y pausar la asignación de Campaña a Adobe Experience Platform.

* Se puede asignar cualquier dimensión de segmentación. Se recomienda tener una sola asignación para todos los campos de una sola dimensión de segmentación.

* Todas las actualizaciones de perfil, incluidas las exclusiones y exclusiones de canal, forman parte de la actualización por lotes.

* Cualquier cambio de esquema de Adobe Campaign Standard o XDM debe reasignarse manualmente. &#x200B;

* El seguimiento de los datos de registro y Broadlog se transfiere automáticamente a Adobe Experience Platform como Eventos de experiencias. Esta ingesta se transmite en tiempo real a Adobe Experience Platform.

* El servicio de ID de Experience Cloud (ECID) es un identificador de dispositivo que se envía de forma predeterminada con Experience Eventos.

   Se trata de un ID único y persistente asignado a un visitante que puede utilizar el servicio de identidad de plataforma para identificar el mismo visitante y sus datos en diferentes soluciones de Experience Cloud. Para obtener más información sobre esto, consulte la Ayuda [del servicio de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud.

   >[!NOTE]
   >
   >Tenga en cuenta que, si dos o más perfiles comparten un mismo dispositivo, el ECID será el mismo para estos dos perfiles en el servicio de identidad unificada.

## Limitaciones {#limitations}

* No se admite la transferencia predeterminada de eventos de suscripción. Para transferir eventos de suscripción, puede crear el XDM y el conjunto de datos correspondientes en Adobe Experience Platform y, a continuación, configurar una asignación de datos personalizada para estos datos.

* En cuanto a las solicitudes de privacidad (acciones de acceso y eliminación), los clientes deben realizar solicitudes independientes: una para la Campaña mediante la integración de Privacy Core Service (consulte [esta sección](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)) y otra para Adobe Experience Platform a través de [Privacy Service](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa). Para obtener más información sobre las solicitudes de acceso y eliminación, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess).

* Para cada campo XDM, el etiquetado DULE debe realizarse en Adobe Experience Platform. Es responsabilidad del cliente aplicar etiquetas DULE.

* Las restricciones de las acciones de marketing solo se aplican después de aplicar etiquetas DULE en Adobe Experience Platform. Antes de eso, todos los datos están disponibles para todos los tipos de acciones de mercadotecnia.

* Cada 15 minutos, el trabajo por lotes se ejecuta e identifica los registros que han cambiado desde el último lote. Si todos los registros cambian con la misma marca de tiempo, podría aparecer un cuello de botella de rendimiento para administrar la ingestión de todos los perfiles

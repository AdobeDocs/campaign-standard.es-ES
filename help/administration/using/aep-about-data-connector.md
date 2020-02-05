---
title: Acerca del conector de datos de la plataforma Adobe Experience
description: Administre esquemas XDM para que los datos de Campaign Standard estén disponibles en Adobe Experience Platform.
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
source-git-commit: 8ea3340e9ffb8b438c781aeff1a8554c9160474f

---


# Acerca del conector de datos de la plataforma Adobe Experience {#about-aep-data-connector}

>[!IMPORTANT]
>
>El conector de datos de la plataforma de Adobe Experience está actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

El conector de datos de la plataforma Adobe Experience Platform ayuda a los clientes existentes a poner sus datos a disposición en la plataforma Adobe Experience, asignando datos XTK (datos ingestados en Campaign) a datos del modelo de datos de experiencia (XDM) en la plataforma Adobe Experience.

Tenga en cuenta que el conector es **unidireccional** y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían desde Adobe Experience Platform a Adobe Campaign Standard.

El conector de datos de la plataforma de experiencia de Adobe está dirigido a ingenieros **de** datos que entienden los recursos personalizados de Adobe Campaign Standard y que entienden cómo debe estar el esquema de datos general del cliente dentro de la plataforma de Adobe Experience.

Las siguientes secciones describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform. Esto comienza con la creación de un esquema XDM y un conjunto de datos.

Los vídeos de procedimientos también están disponibles en [esta página](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Una vez configurado el conector de datos de la plataforma de experiencia de Adobe y que los datos se transfieran correctamente a la plataforma de Adobe Experience, debe habilitar el conjunto de datos para que los datos se incluyan en el perfil del cliente en tiempo real.
>
>Esto se puede realizar a través de las API o de la interfaz de Adobe Experience Platform. Para obtener más información, consulte las documentaciones dedicadas:
>
>* [Habilitar un conjunto de datos para el perfil del cliente en tiempo real](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [Configurar un conjunto de datos para el perfil del cliente en tiempo real y el servicio de identidad mediante API](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## Conceptos clave {#key-concepts}

* La asignación de fuera de la caja solo está disponible para los campos que se proporcionan en Campaign Standard de forma predeterminada. Para ingerir todos los campos y recursos personalizados, cada cliente debe definir su propia asignación.

* El conector de datos de la plataforma de Adobe Experience Server insertará datos de perfil a través de la plataforma a intervalos regulares. &#x200B; La duración del intervalo es de 15 mn. Este valor no se puede modificar.

   >[!NOTE]
   >
   >Esta duración se puede modificar con las API de [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md).

* El ingeniero de datos puede publicar, modificar y pausar la asignación de Campaign a Adobe Experience Platform.

* Se puede asignar cualquier dimensión de objetivo. La recomendación es tener una sola asignación para todos los campos de una única dimensión de objetivo.

* Todas las actualizaciones de perfil, incluidas las exclusiones y exclusiones del canal, forman parte de la actualización por lotes.

* Cualquier cambio de esquema de Adobe Campaign Standard o XDM debe reasignarse manualmente. &#x200B;

* El seguimiento de los datos de registro y Broadlog se transfiere automáticamente a Adobe Experience Platform como eventos de experiencia. Esta ingesta se transmite en tiempo real a Adobe Experience Platform.

## Limitaciones {#limitations}

* No se admite la transferencia predeterminada de eventos de suscripción. Para transferir eventos de suscripción, puede crear el XDM y el conjunto de datos correspondientes en la plataforma Adobe Experience y, a continuación, configurar una asignación de datos personalizada para estos datos.

* En cuanto a las solicitudes de privacidad, los clientes deben realizar solicitudes independientes para el servicio de privacidad principal de Campaign y Adobe Experience Platform para las acciones de acceso y eliminación.

* Para cada campo XDM, el etiquetado DULE debe realizarse en Adobe Experience Platform. Es responsabilidad del cliente aplicar etiquetas DULE.

* Las restricciones de las acciones de marketing solo se aplican después de aplicar etiquetas DULE en Adobe Experience Platform. Antes de eso, todos los datos están disponibles para todos los tipos de acciones de mercadotecnia.

* Cada 15 minutos, el trabajo por lotes se ejecuta e identifica los registros que han cambiado desde el último lote. Si todos los registros cambian con la misma marca de tiempo, podría aparecer un cuello de botella de rendimiento para administrar la ingestión de todos los perfiles

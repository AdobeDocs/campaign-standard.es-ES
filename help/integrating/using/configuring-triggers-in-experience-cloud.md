---
title: Configuración de activadores en Experience Cloud
seo-title: Configuración de activadores en Experience Cloud
description: Configuración de activadores en Experience Cloud
seo-description: 'Descubra cómo configurar la integración de Adobe Experience Cloud Triggers para empezar a enviar envíos personalizados a sus clientes en función de sus comportamientos anteriores. '
page-status-flag: nunca activado
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y activadores
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Configuración de activadores en Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activación de la funcionalidad {#activating-the-functionality}

Adobe debe activar la funcionalidad en Adobe Campaign. Póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe.

El equipo de Adobe necesitará la siguiente información para activar activadores:

* Nombre de empresa de Marketing Cloud
* ID DE ORIGEN DE IMS
* Empresa de inicio de sesión de Analytics (puede ser igual que el nombre de la empresa de Marketing Cloud)

## Configuración de soluciones y servicios {#configuring-solutions-and-services}

Para utilizar esta función, debe tener acceso a las siguientes soluciones y servicios principales:

* Espacio de trabajo de Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servicio principal de Experience Cloud Triggers

   ![](assets/trigger_uc_prereq_1.png)

* Servicio principal de DTM de Experience Cloud

   ![](assets/trigger_uc_prereq_2.png)

* ID de visitante de Experience Cloud y servicio principal Personas de Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

También necesita tener un sitio web de trabajo.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La delegación de subdominios es un elemento clave de entregabilidad. Asegúrese de que los correos electrónicos de Adobe Campaign se envían desde el mismo dominio que el utilizado por el sitio web.

Debe configurar [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) y [Campaign](#configuring-triggers-and-aliases-in-campaign) para ejecutar estos casos de uso.

### Configuración del servicio principal DTM de Experience Cloud {#configuring-experience-cloud-dtm-core-service}

1. En el servicio principal de DTM de Experience Cloud (administración dinámica de etiquetas), active Experience Cloud ID y Adobe Analytics para las páginas del sitio web.

   ![](assets/trigger_uc_conf_1.png)

1. La reconciliación de ID entre el sitio web, Adobe Analytics y Adobe Campaign requiere el uso de alias. Cree un alias, "visitorid" por ejemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configuración del servicio principal Personas de Experience Cloud {#configuring-experience-cloud-people-core-service}

El alias al que se hace referencia anteriormente en la DTM debe crearse en el servicio principal Personas de Experience Cloud mediante un atributo de cliente. Asegúrese de crear uno nuevo y de hacer referencia al mismo alias de la DTM en el código de integración (por ejemplo, "visitorid").

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Utilizaremos este atributo de cliente en la fuente de datos de Adobe Campaign (paso siguiente).

### Configuración de activadores y alias en Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Asegúrese de que está **[!UICONTROL Experience Cloud triggers]** visible en la instancia de Adobe Campaign Standard. Si no lo hace, póngase en contacto con los administradores de Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Los alias permiten reconciliar un contacto de Analytics con un perfil de Campaign. Debe coincidir los alias definidos en el servicio de ID de Experience Cloud con una fuente de datos compartida en Campaign. Debe configurar la resolución de alias en Adobe Campaign mediante una fuente de datos ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Asegúrese de elegir la fuente de datos correcta en el menú desplegable, que se asigna con la misma fuente de datos de Atributos del cliente creada en el paso anterior. **[!UICONTROL Data Source/Alias]**

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puede reconciliar los activadores tanto para los usuarios anónimos como para los que iniciaron sesión. Para los usuarios anónimos, el perfil debe existir en Adobe Campaign y antes se ha enviado un correo electrónico al usuario. Para ello, la configuración del ID de visitante es suficiente. Sin embargo, si desea reconciliar los activadores para los usuarios que iniciaron sesión, debe configurar la fuente de datos de ID declarados. Para obtener más información sobre esto, consulte Configuración [de fuentes de](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)datos.

## Creación de un activador en la interfaz de Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Es necesario crear un activador de Adobe Experience Cloud para poder utilizarlo en Campaign.

Cree un nuevo activador en Experience Cloud y asegúrese de seleccionar el grupo de informes utilizado en el sitio web. Asegúrese de elegir la dimensión adecuada para que el activador se active.

Consulte la documentación [de](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) Adobe Experience Cloud y vea este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Desencadena las prácticas recomendadas y las limitaciones {#triggers-best-practices-and-limitations}

Esta es una lista de prácticas recomendadas y limitaciones para el uso de la integración Campaña - Desencadenadores:

* Si tiene varias instancias de Campaign Standard, todas las instancias pueden recibir activadores siempre que estén en el mismo ID de organización de IMS. Analytics también debe estar en el mismo ID de organización de IMS.
* No se puede crear un activador en el servicio principal de activación mediante eventos de dos grupos de informes diferentes.
* Los activadores se basan en mensajes transaccionales. Los mensajes transaccionales se utilizan siempre que tiene que enviar un mensaje muy rápido. No puede poner en cola los mensajes transaccionales y, a continuación, reproducirlos en lote.
* Los activadores no son de naturaleza determinística. Cuando se genera un activador, envía todos los alias asociados con la cookie, de modo que en el caso de exploradores compartidos como en quioscos de venta minorista, bibliotecas, cibercafés o dispositivos compartidos en casa (marido y mujer que inician sesión desde el mismo dispositivo), no es posible asignar el ID correcto. Todos los ID utilizados para iniciar sesión con el explorador se envían a Campaign, que envía un mensaje en función de la primera reconciliación. Si hay varios "ID de correo electrónico" que cumplen los requisitos para la reconciliación, Campaign no envía un correo electrónico. Campaign no puede saber cuál es el ID de correo electrónico correcto a menos que Analytics lo capture y envíe.
* No puede almacenar contenido de la carga útil en Campaign. No se pueden usar activadores para actualizar los datos de un perfil.
* Los atributos del cliente no son compatibles con los activadores (es decir, solo se pueden usar datos de grupos de informes para definir las reglas comerciales de activadores).
* La colección de colecciones no es compatible con Campaign.

>[!CAUTION]
>
>El sitio web debe ejecutarse en el mismo dominio que el servidor de Adobe Campaign. De lo contrario, no puede utilizar la identificación del visitante para reconciliar y comunicarse con los usuarios que visitan el sitio web de forma anónima.


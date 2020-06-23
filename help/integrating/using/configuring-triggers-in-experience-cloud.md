---
title: Configuración de activadores en Experience Cloud
description: 'Obtenga información sobre cómo configurar la integración de Adobe Experience Cloud Triggers para que inicio envíe envíos personalizados a sus clientes en función de sus comportamientos anteriores. '
page-status-flag: never-activated
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 2%

---


# Configuración de activadores en Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activación de la funcionalidad {#activating-the-functionality}

Adobe debe activar la funcionalidad en Adobe Campaign. Póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe.

El equipo de Adobe necesitará la siguiente información para activar activadores:

* Nombre de Compañía de Marketing Cloud
* ID DE ORIGEN DE IMS
* Compañía de inicio de sesión de Analytics (puede ser la misma que el nombre de Compañía de Marketing Cloud)

## Configuración de soluciones y servicios {#configuring-solutions-and-services}

Para utilizar esta función, debe tener acceso a las siguientes soluciones y servicios principales:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Experience Cloud activa el servicio principal

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM Core Service

   ![](assets/trigger_uc_prereq_2.png)

* ID de Visitante de Experience Cloud y servicio principal de personas Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

También necesita tener un sitio web de trabajo.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La delegación de subdominios es un elemento clave de entregabilidad. Asegúrese de que los mensajes de correo electrónico de Adobe Campaign se envían desde el mismo dominio que el utilizado por el sitio web.

Debe configurar el servicio [principal](#configuring-experience-cloud-dtm-core-service)Experience Cloud DTM, el servicio [principal Personas](#configuring-experience-cloud-people-core-service) Experience Cloud y la [Campaña](#configuring-triggers-and-aliases-in-campaign) para ejecutar estos casos de uso.

### Configuración del servicio principal de Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. En el servicio principal de Experience Cloud DTM (administración dinámica de etiquetas), active el ID de Experience Cloud y Adobe Analytics para las páginas del sitio web.

   ![](assets/trigger_uc_conf_1.png)

1. La reconciliación de ID entre el sitio web, Adobe Analytics y Adobe Campaign requiere el uso de alias. Cree un alias, &quot;visitorid&quot; por ejemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configuración del servicio principal Personas Experience Cloud {#configuring-experience-cloud-people-core-service}

El alias al que se hace referencia anteriormente en la DTM debe crearse en el servicio principal Personas Experience Cloud a través de un atributo de cliente. Asegúrese de crear uno nuevo y de hacer referencia al mismo alias de la DTM en el código de integración (por ejemplo, &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Vamos a usar este atributo de cliente en la fuente de datos en Adobe Campaign (paso siguiente).

### Configuración de activadores y alias en la Campaña {#configuring-triggers-and-aliases-in-campaign}

1. Asegúrese de que está **[!UICONTROL Experience Cloud triggers]** visible en la instancia de Adobe Campaign Standard. Si no lo hace, póngase en contacto con los administradores de Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Los alias permiten que un contacto en Analytics se concilie con un perfil en Campaña. Debe coincidir los alias definidos en el servicio de ID de Experience Cloud con una fuente de datos compartida en la Campaña. Debe configurar la resolución de alias en Adobe Campaign mediante una fuente de datos ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Asegúrese de elegir la fuente de datos correcta en el menú desplegable, que se asigna con la misma fuente de datos de Atributos del cliente creada en el paso anterior. **[!UICONTROL Data Source/Alias]**

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puede reconciliar los activadores tanto para los usuarios anónimos como para los usuarios que iniciaron sesión. Para los usuarios anónimos, el perfil debe existir en Adobe Campaign y antes se ha enviado un correo electrónico al usuario. Para ello, la configuración del ID de Visitante es suficiente. Sin embargo, si desea reconciliar los activadores para los usuarios que iniciaron sesión, debe configurar la fuente de datos de ID declarados. For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creación de un activador en la interfaz de Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Es necesario crear un activador de Adobe Experience Cloud para poder utilizarlo en la Campaña.

Cree un nuevo activador en Experience Cloud y asegúrese de seleccionar el grupo de informes utilizado en el sitio web. Asegúrese de elegir la dimensión correcta para que el activador se active.

Consulte la documentación [de](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html) Adobe Experience Cloud y vea este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Desencadena las prácticas recomendadas y las limitaciones {#triggers-best-practices-and-limitations}

Esta es una lista de las prácticas recomendadas y las limitaciones para el uso de la Campaña: Desencadena la integración:

* Si tiene varias instancias de Campaign Standard, todos los casos pueden recibir activadores siempre que estén en el mismo ID de organización de IMS. Analytics también debe estar en el mismo ID de organización de IMS.
* No se puede crear un activador en el servicio principal de activación con eventos de dos grupos de informes diferentes.
* Los activadores se basan en mensajes transaccionales. Los Mensajes transaccionales se utilizan siempre que se tiene que enviar un mensaje muy rápido. No se pueden poner en cola mensajes transaccionales y, a continuación, reproducirlos por lotes.
* Los activadores no son de naturaleza determinística. Cuando se genera un activador, envía todos los alias asociados con la cookie, de modo que en el caso de exploradores compartidos como en quioscos de venta minorista, bibliotecas, cibercafés o dispositivos compartidos en casa (marido y mujer que inician sesión desde el mismo dispositivo), no es posible asignar el ID correcto. Todos los ID utilizados para iniciar sesión con el navegador se envían a Campaña, que envía un mensaje en función de la primera reconciliación. Si hay varios &quot;ID de correo electrónico&quot; que pueden conciliarse, la Campaña no envía un mensaje de correo electrónico. No hay forma de que la Campaña sepa cuál es el ID de correo electrónico correcto a menos que Analytics lo capture y envíe.
* No se puede almacenar el contenido de la carga útil en la Campaña. Los activadores no se pueden usar para actualizar los datos de un perfil.
* Los atributos del cliente no son compatibles con los activadores (es decir, solo se pueden usar datos de grupos de informes para definir las reglas comerciales de activadores).
* La colección de colecciones no se admite en la Campaña.

>[!CAUTION]
>
>El sitio web debe ejecutarse en el mismo dominio que el servidor de Adobe Campaign. Si no es así, no puede utilizar la identificación de visitante para reconciliar y ponerse en contacto con los usuarios que visitan el sitio web de forma anónima.


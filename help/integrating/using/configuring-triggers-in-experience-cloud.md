---
title: Configuración de activadores en Experience Cloud
description: Obtenga información sobre cómo configurar la integración de activadores de Adobe Experience Cloud para empezar a enviar envíos personalizados a sus clientes en función de sus comportamientos anteriores.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Configuración de activadores en Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activación de la funcionalidad {#activating-the-functionality}

Adobe debe activar la funcionalidad en Adobe Campaign. Póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales.

El equipo de Adobe necesitará la siguiente información para activar déclencheur:

* Nombre de empresa de Marketing Cloud
* ID de la organización
* Empresa de inicio de sesión de Analytics (puede ser la misma que el nombre de empresa de Marketing Cloud)

## Configuración de soluciones y servicios {#configuring-solutions-and-services}

Para utilizar esta función, debe tener acceso a las siguientes soluciones o servicios principales:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servicio principal de los activadores de Experience Cloud

  ![](assets/trigger_uc_prereq_1.png)

* Servicio principal de DTM de Experience Cloud

  ![](assets/trigger_uc_prereq_2.png)

* El ID de visitante de Experience Cloud y el servicio principal People de Experience Cloud

  ![](assets/trigger_uc_prereq_3.png)

También necesita tener un sitio web de trabajo.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La configuración de subdominios es un elemento clave de la capacidad de entrega. Asegúrese de que los correos electrónicos de Adobe Campaign se envían desde el mismo dominio que el utilizado por el sitio web.

Debe configurar el [servicio principal de DTM de Experience Cloud](#configuring-experience-cloud-dtm-core-service), el [servicio principal de personas de Experience Cloud](#configuring-experience-cloud-people-core-service) y [Campaign](#configuring-triggers-and-aliases-in-campaign) para ejecutar estos casos de uso.

### Configuración del servicio principal de Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. En el servicio principal de Experience Cloud DTM (Dynamic Tag Management), active Experience Cloud ID y Adobe Analytics para sus páginas de sitio web.

   ![](assets/trigger_uc_conf_1.png)

1. La reconciliación de ID entre el sitio web, Adobe Analytics y Adobe Campaign requiere el uso de un alias. Cree un alias, por ejemplo, &quot;visitorid&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Configuración del servicio principal People de Experience Cloud {#configuring-experience-cloud-people-core-service}

El alias al que se hace referencia anteriormente en la DTM debe crearse en el servicio principal People de Experience Cloud a través de un atributo del cliente. Asegúrese de crear uno nuevo y de hacer referencia al mismo alias de la DTM en el código de integración (por ejemplo, &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Vamos a utilizar este atributo del cliente en la fuente de datos en Adobe Campaign (paso siguiente).

### Configuración de déclencheur y alias en Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Asegúrese de que tenga **[!UICONTROL Experience Cloud triggers]** visible en la instancia de Adobe Campaign Standard. Si no lo hace, póngase en contacto con los administradores de Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Los alias permiten que un contacto en Analytics se reconcilie con un perfil en Campaign. Debe hacer coincidir los alias definidos en el servicio Experience Cloud ID con un Source de datos compartidos en Campaign. Debe configurar la resolución de alias en Adobe Campaign mediante una fuente de datos ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Asegúrese de elegir el origen de datos correcto en el menú desplegable **[!UICONTROL Data Source/Alias]**, que está asignado con el mismo origen de datos de atributos del cliente creado en el paso anterior.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puede reconciliar las déclencheur de los usuarios anónimos y los que han iniciado sesión. Para usuarios anónimos, el perfil debe existir en Adobe Campaign y antes se le ha enviado un correo electrónico. Para ello, la configuración del ID de visitante es suficiente. Sin embargo, si desea reconciliar las déclencheur de los usuarios que han iniciado sesión, debe configurar el Source de datos de ID declarados. Para obtener más información, consulte [Configuración de Data Source](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creación de un déclencheur en la interfaz de Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Es necesario crear un déclencheur de Adobe Experience Cloud para poder utilizarlo en Campaign.

Cree un nuevo déclencheur en Experience Cloud y asegúrese de seleccionar el grupo de informes utilizado en el sitio web. Asegúrese de elegir la dimensión correcta para que el déclencheur se active.

Consulte la [documentación de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=es).

## Prácticas recomendadas y limitaciones de Déclencheur {#triggers-best-practices-and-limitations}

A continuación, se muestra una lista de prácticas recomendadas y limitaciones para la integración de Campaign y Déclencheur:

* Si tiene varias instancias de Campaign Standard, todas las instancias pueden recibir déclencheur siempre y cuando estén en la misma organización. Analytics también debe estar en la misma organización.
* No se puede crear un déclencheur en el servicio principal de Déclencheur mediante eventos de dos grupos de informes diferentes.
* Los déclencheur se basan en mensajes transaccionales. Los mensajes transaccionales se utilizan siempre que tiene que enviar un mensaje muy rápidamente. No puede poner mensajes transaccionales en cola y después reproducirlos en lote.
* Los déclencheur no son de naturaleza determinista. Cuando se genera un déclencheur, envía todos los alias asociados con la cookie, por lo que en el caso de exploradores compartidos como en quioscos de venta minorista, bibliotecas, cibercafés o dispositivos compartidos en casa (marido y mujer que inician sesión desde el mismo dispositivo), no es posible asignar al ID correcto. Todos los ID utilizados para iniciar sesión con el explorador se envían a Campaign, que envía un mensaje en función de la primera reconciliación. Si hay varios &quot;ID de correo electrónico&quot; aptos para la reconciliación, Campaign no envía un correo electrónico. Campaign no puede saber cuál es el ID de correo electrónico correcto a menos que Analytics lo capture y lo envíe.
* No se puede almacenar el contenido de la carga útil en Campaign. No se pueden usar déclencheur para actualizar los datos de un perfil.
* Los atributos del cliente no se admiten en Déclencheur (es decir, solo se pueden utilizar datos del grupo de informes para definir reglas comerciales de Déclencheur).
* La colección de colecciones no es compatible con Campaign.

>[!CAUTION]
>
>El sitio web debe ejecutarse en el mismo dominio que el servidor de Adobe Campaign. Si no es así, no puede utilizar el ID de visitante para reconciliar y ponerse en contacto con usuarios que visitan el sitio web de forma anónima.

---
title: Configuración de activadores en Experience Cloud
seo-title: Configuración de activadores en Experience Cloud
description: Configuración de activadores en Experience Cloud
seo-description: 'Aprenda a configurar la integración de Adobe Experience Cloud Triggers para empezar a enviar entregas personalizadas a sus clientes en función de sus comportamientos anteriores. '
page-status-flag: no activado nunca
uuid: 8 fd 7 b 804-9528-46 a 5-a 060-bf 16 b 8 dc 555 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y activadores
discoiquuid: 4163 dc 0 c -8103-4425-b 8 bf -7 aa 45 c 4 d 3 a 06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

Adobe debe activar la funcionalidad en Adobe Campaign. Comuníquese con el socio de cuentas de Adobe o con el socio de servicios profesionales.

El equipo de Adobe necesitará la siguiente información para activar activadores:

* Nombre de empresa de Marketing Cloud
* ID de organización IMS
* Empresa de inicio de sesión de Analytics (puede ser igual que el nombre de empresa de Marketing Cloud)

## Configuring solutions and services {#configuring-solutions-and-services}

Para utilizar esta función, debe tener acceso a las siguientes soluciones/servicios principales:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Experience Cloud Triggers Core Service

   ![](assets/trigger_uc_prereq_1.png)

* Servicio principal de Experience Cloud DTM

   ![](assets/trigger_uc_prereq_2.png)

* ID del visitante de Experience Cloud y servicio principal de personas de Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

También necesita tener un sitio web de trabajo.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La delegación de subdominio es un elemento clave de entrega. Asegúrese de que los mensajes de correo electrónico de Adobe Campaign se envían desde el mismo dominio que el utilizado por el sitio web.

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. En Experience Cloud Core Service Service (Administración dinámica de etiquetas), active Experience Cloud ID y Adobe Analytics para las páginas de su sitio web.

   ![](assets/trigger_uc_conf_1.png)

1. La reconciliación de ID entre el sitio web, Adobe Analytics y Adobe Campaign requiere de la utilización de alias. Cree un alias, "visitorid", por ejemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

El alias al que se hace referencia anteriormente en DTM debe crearse en el servicio principal Personas de Experience Cloud a través de un atributo de cliente. Asegúrese de crear una nueva y haga referencia al mismo alias de la DTM en el código de integración (por ejemplo, "visitorid").

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Vamos a utilizar este Atributo del cliente en la fuente de datos de Adobe Campaign (paso siguiente).

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Make sure you have **[!UICONTROL Experience Cloud triggers]** visible on your Adobe Campaign Standard instance. Si no lo hace, póngase en contacto con los administradores de Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Los alias permiten que un contacto en Analytics se reconcilie con un perfil de Campaign. Debe coincidir con los alias definidos en el servicio Experience Cloud ID con una fuente de datos compartida en Campaign. You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Make sure you choose the correct data source in the **[!UICONTROL Data Source/Alias]** drop-down menu, which is mapped with the same Customer Attribute data source created in previous step.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puede reconciliar los activadores tanto para usuarios anónimos como para usuarios registrados. Para usuarios anónimos, el perfil debería existir en Adobe Campaign y se ha enviado un correo electrónico al usuario antes. Para esto, la configuración de ID de visitante es suficiente. Sin embargo, si desea reconciliar los activadores de usuarios que iniciaron sesión, debe configurar la fuente de datos de ID declarados. For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

Es necesario crear un activador de Adobe Experience Cloud para poder utilizarlo en Campaign.

Cree un nuevo activador en Experience Cloud y asegúrese de seleccionar el grupo de informes utilizado en el sitio web. Asegúrese de elegir la dimensión adecuada para activar el activador.

Refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) and watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

Esta es una lista de prácticas recomendadas y limitaciones para el uso de la integración de Campaign - Triggers:

* Si tiene varias instancias de Campaign Standard, todas las instancias pueden recibir activadores siempre y cuando estén en el mismo ID de organización de IMS. Analytics también debe estar en el mismo ID de organización de IMS.
* No se puede crear un activador en el activador principal mediante eventos de dos grupos de informes diferentes.
* Los activadores se basan en mensajes transaccionales. Los mensajes transaccionales se utilizan siempre que se tiene que enviar un mensaje rápidamente. No puede colocar mensajes transaccionales en cola y, a continuación, moverlos por lotes.
* Los activadores no son determinísticos. Cuando se genera un activador, envía todos los alias asociados con la cookie, por lo que, en el caso de los exploradores compartidos, como kioscos minoristas, bibliotecas, cibercafeterías o dispositivos compartidos en casa (inicio de sesión de marido y esposa en el mismo dispositivo), no es posible asignar a la ID correcta. Todos los ID utilizados para iniciar sesión con el navegador se envían a Campaign, que envía un mensaje en base a la primera reconciliación. Si hay varios "ID de correo electrónico" elegibles para la reconciliación, la campaña no envía un mensaje de correo electrónico. No hay forma de que Campaign sepa cuál es el ID de correo electrónico correcto a menos que lo capture y envíe Analytics.
* No puede almacenar contenido de carga útil en Campaign. No se pueden utilizar activadores para actualizar los datos de un perfil.
* Los atributos del cliente no son compatibles con Activadores (es decir, solo los datos del grupo de informes pueden utilizarse para definir reglas comerciales de Activadores).
* La campaña no admite colecciones de colecciones.

>[!CAUTION]
>
>El sitio web debe ejecutarse en el mismo dominio que el servidor de Adobe Campaign. Si no es así, no puede utilizar la identificación del visitante para reconciliar y comunicarse con los usuarios que visitan el sitio web de forma anónima.


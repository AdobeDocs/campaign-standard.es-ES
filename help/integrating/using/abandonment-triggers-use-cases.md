---
title: Casos de uso de activadores de abandono
seo-title: Casos de uso de activadores de abandono
description: Casos de uso de activadores de abandono
seo-description: Descubra cómo utilizar la integración de Experience Cloud Triggers con estos distintos casos de uso.
page-status-flag: nunca activado
uuid: 9e236165-afd5-4155-9151-c1941dc0af99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y activadores
discoiquuid: 1b9aeec5-70bb-4d72-a3e9-12342abf08f7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Casos de uso de activadores de abandono{#abandonment-triggers-use-cases}

Esta sección presenta diferentes casos de uso que se pueden implementar mediante la integración entre Adobe Campaign y Experience Cloud Triggers. Encontrará dos ejemplos de casos de uso:

* [Desencadenador](#browse-abandonment-trigger)de abandono de exploración: enviar una comunicación a los clientes que abandonaron la visita en el sitio web.
* [Activador](#search-abandonment-trigger)de abandono de búsqueda: vuelva a interactuar con los visitantes que realizaron una búsqueda en el sitio web, pero no realizaron una compra.

>[!NOTE]
>
>Los casos de uso descritos en esta sección se basan en el ID de visitante de Experience Cloud. También es posible implementarlos con el ID declarado de Experience Cloud. También se admiten los ID declarados con hash y cifrados. Puede enviar correos electrónicos/SMS a un perfil que no exista en Campaign descifrando directamente la dirección de correo electrónico o el número de móvil cifrados. Pero en este caso, no se puede utilizar la personalización mediante datos de perfil.

## Requisitos previos {#pre-requisites}

Para que estos casos de uso se implementen, debe tener acceso a las siguientes soluciones/servicios principales:

* Espacio de trabajo de Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servicio principal de Experience Cloud Triggers
* Servicio principal de DTM de Experience Cloud
* ID de visitante de Experience Cloud y servicio principal Personas de Experience Cloud

También necesita tener un sitio web de trabajo.

Para obtener más información, consulte [Configuración de soluciones y servicios](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Explorar activador de abandono {#browse-abandonment-trigger}

En este caso de uso, vamos a crear un activador simple que se activará cada vez que un cliente abandone una visita en el sitio web. En este ejemplo se asume que ya dispone de la DTM para recopilar y enviar datos a Adobe Analytics y que todos los eventos se han creado.

### Creación de un activador de Experience Cloud {#creating-an-experience-cloud-trigger}

1. Seleccione **[!UICONTROL Manage Triggers]** en el menú Servicio principal de activación de Experience Cloud.

   ![](assets/trigger_uc_browse_1.png)

1. Elija un tipo de activador ( **[!UICONTROL Abandonment]** en nuestro caso de uso).

   ![](assets/trigger_uc_browse_2.png)

1. Para este caso de uso, necesitamos un simple activador de abandono. El objetivo comercial es identificar a los visitantes que navegan por nuestro sitio web de reservación de viajes, que ven la página "Ofertas" pero no reservan ningún viaje. Una vez que identifiquemos a esta audiencia, queremos volver a contactarla en un corto período de tiempo. En este ejemplo, elegimos enviar el activador después de un período de 10 minutos.

   ![](assets/trigger_uc_browse_3.png)

### Uso del activador en Adobe Campaign {#using-the-trigger-in-adobe-campaign}

Ahora que hemos creado un activador de Experience Cloud, vamos a utilizarlo en Adobe Campaign.

En Adobe Campaign, debe crear un activador vinculado al que ha creado en Experience Cloud.

1. Para crear el activador en Adobe Campaign, haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la esquina superior izquierda y, a continuación, seleccione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. Seleccione el activador que ha creado anteriormente y haga clic en **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Seleccione el **[!UICONTROL Email]** canal y la dimensión de **[!UICONTROL Real-time event]** objetivo y haga clic en **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Publicar el activador en Adobe Campaign. Este proceso creará automáticamente una plantilla de mensaje transaccional.

   ![](assets/trigger_uc_browse_6.png)

1. Para mostrar la plantilla de mensaje, haga clic en el **[!UICONTROL More]** botón, en la parte superior derecha, y luego haga clic en **[!UICONTROL Trigger Transactional Template]**.

1. Personalice el contenido y los detalles del remitente.

   ![](assets/trigger_uc_browse_8.png)

1. Publique la plantilla de mensaje. El activador ahora está activo y en funcionamiento.

   ![](assets/trigger_uc_browse_0.png)

### Ejecución del escenario {#running-the-scenario}

1. Este caso de uso comienza con un mensaje de correo electrónico inicial enviado a la audiencia con Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. El destinatario abre el correo electrónico.

   ![](assets/trigger_uc_browse_10.png)

1. Él hace clic en un enlace que lo lleva a su sitio web. En este ejemplo, la pancarta lleva al destinatario a la página principal del sitio web de reservación de viajes.

   ![](assets/trigger_uc_browse_11.png)

1. El destinatario va a la página "Ofertas" pero de repente detiene su visita. Tras un período de 10 minutos, Adobe Campaign desencadena el envío del mensaje transaccional.

   ![](assets/trigger_uc_browse_12.png)

1. En cualquier momento, puede comprobar los registros de Experience Cloud para ver cuántas veces se activó el activador.

   ![](assets/trigger_uc_browse_13.png)

1. También puede mostrar el informe de activación de Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Activador de abandono de búsqueda {#search-abandonment-trigger}

En este caso de uso, vamos a crear un activador para volver a interactuar con los visitantes que fueron a nuestro sitio web de reservación de viajes, buscaron un destino, no encontraron resultados exitosos y no reservaron nada después de eso. El proceso general es el mismo que en el caso de uso anterior (consulte Activador de abandono de [exploración](#browse-abandonment-trigger)). Nos centraremos aquí en cómo personalizar el mensaje de correo electrónico de remercadotecnia.

### Creación de un activador de Experience Cloud {#creating-an-experience-cloud-trigger-1}

Siga los pasos descritos en el caso de uso anterior para crear Experience Cloud Trigger. Consulte [Creación de un activador](#creating-an-experience-cloud-trigger)de Experience Cloud. La diferencia principal es la definición del activador.

![](assets/trigger_uc_search_1.png)

La **[!UICONTROL Include Meta Data]** sección le permite pasar cualquier dato recopilado de Analytics a la carga útil Activador. En este ejemplo, creamos una eVar personalizada (por ejemplo, eVar 3) para recopilar el término de búsqueda que introduce el visitante. Este término se utilizará en el mensaje de correo electrónico transaccional enviado al mismo visitante.

### Uso del activador en Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. Siga los pasos descritos en el caso de uso anterior para crear el activador en Adobe Campaign. Consulte [Uso del activador en Adobe Campaign](#using-the-trigger-in-adobe-campaign). La diferencia principal es cómo accedemos a los metadatos insertados en la carga útil Activador y los utilizamos en Adobe Campaign.
1. En el activador de abandono de búsqueda que creó en Adobe Campaign, haga clic en el icono **[!UICONTROL Event content and enrichment]** para ver la carga útil que se ha insertado en Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. Como puede ver, la eVar personalizada se pasa en la carga útil Activador y se asigna a la tabla Contexto **de** evento (ctx). Ahora podemos acceder a él para personalizar el mensaje transaccional.

   ![](assets/trigger_uc_search_3.png)

1. En este ejemplo, elegimos incluir el término de búsqueda de destino tanto en la línea de asunto como en el cuerpo del correo electrónico.

   ![](assets/trigger_uc_search_4.png)

1. Al seleccionar un campo personalizado, busque los metadatos de carga útil en la tabla **Evento** transaccional (rtEvent) y, a continuación, en la subtabla de contexto **de** evento (ctx).

   ![](assets/trigger_uc_search_5.png)

### Ejecución del escenario {#running-the-scenario-1}

1. El visitante va al sitio web de reservación de viajes y busca un destino. En este ejemplo, el visitante busca un viaje a Japón pero no encuentra ningún resultado. Esta es una oportunidad para que podamos contactar con este visitante y recomendar un plan de viaje alternativo.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >En este caso de uso, suponemos que el visitante/destinatario ya se ha abierto y ha hecho clic en un correo electrónico que se origina en el mismo sitio web. Esto nos permite usar y recopilar VisitorID y asignarlo al destinatario. Solo necesitamos hacer esto una vez.

1. Pocos minutos después, el mismo visitante/destinatario recibe un mensaje de remercadotecnia. El mensaje incluye el destino de búsqueda reciente.

   ![](assets/trigger_uc_search_7.png)


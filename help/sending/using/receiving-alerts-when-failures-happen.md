---
title: Recepción de alertas cuando se producen errores
seo-title: Recepción de alertas cuando se producen errores
description: Recepción de alertas cuando se producen errores
seo-description: Descubra cómo utilizar el sistema de administración de alertas.
page-status-flag: no activado nunca
uuid: a 3 ab 733 a-e 3 db -4 adc-b 930-cd 4064 b 6 dc 1 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: monitoreo de mensajes
discoiquuid: 0766 bd 57-c 5 f 1-4 f 56-ac 84-e 5 a 04 d 3819 ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Receiving alerts when failures happen{#receiving-alerts-when-failures-happen}

## About delivery alerting {#about-delivery-alerting}

The **Delivery alerting** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

Las notificaciones enviadas contienen un informe basado de forma predeterminada en los siguientes criterios:

* Entregas fallidas
* Entregas con preparación fallida
* Entregas con una relación de error de salida hacia otro sitio errónea
* Entregas con una tasa de error de salida hacia otro sitio negativa
* Entregas con estado pendiente más largas de lo habitual
* Entregas con un bajo rendimiento
* Entregas en curso

Los destinatarios de las alertas pueden monitorear las entregas que procesan Adobe Campaign y tomar las medidas apropiadas cuando surjan problemas en la ejecución.

Estas notificaciones de alerta pueden personalizarse según criterios de alerta específicos definidos a través de un tablero en la interfaz de Adobe Campaign.

>[!NOTE]
>
>Las notificaciones de alerta se envían únicamente por correo electrónico.

Las notificaciones enviadas contienen:

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* **[!UICONTROL Details]** Sección que enumera todos los criterios de entrega definidos para el tablero correspondiente y todos los envíos para cada criterio.

![](assets/delivery-alerting_notification.png)

## Delivery alerting dashboards {#delivery-alerting-dashboards}

### About delivery alerting dashboards {#about-delivery-alerting-dashboards}

Para administrar los destinatarios de las notificaciones, definir los criterios de alerta y acceder al historial de las alertas, debe utilizar tableros.

>[!NOTE]
>
>To access and configure the dashboards and the alerting criteria, you must have administration rights or appear in the **Delivery supervisors** security group. Los usuarios estándar no pueden acceder a los tableros en la interfaz de Adobe Campaign. Solo pueden recibir notificaciones de alerta. For more on users and security in Adobe Campaign, see [Types of users](../../administration/using/types-of-users.md) and [About security groups](../../administration/using/managing-groups-and-users.md#about-security-groups).

Desde la interfaz de Adobe Campaign puede:

* Cree y administre tableros de alerta de entrega. See [Creating a delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard).
* Defina y administre los criterios de alerta de entrega para cada tablero. Por ejemplo, puede generar alertas basadas en entregas con errores de preparación o entregas con un solo rendimiento. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
* Modifique los parámetros de criterios para cada tablero. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
* Defina un grupo de destinatarios para cada tablero.

   Por ejemplo, sólo desea informar a los usuarios de los derechos de administración de los envíos fallidos. Sin embargo, desea que los usuarios de mercadotecnia reciban información sobre los envíos con una tasa de error incorrecta negativa. Por lo tanto, debe crear dos tableros distintos y definir los criterios que desee para cada grupo de destinatarios.

* Acceda al historial de todas las alertas enviadas para cada tablero.

   Al seleccionar un tablero, la última alerta enviada para este tablero se muestra de forma predeterminada. Todas las alertas enviadas aparecen en la parte izquierda de la pantalla. Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Creating a delivery alerting dashboard {#creating-a-delivery-alerting-dashboard}

Si desea enviar notificaciones basadas en criterios específicos para grupos de usuarios diferentes, necesita utilizar varios tableros. Para crear un nuevo tablero:

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Select **[!UICONTROL Delivery alerting dashboards]** and click **[!UICONTROL Create]**.
1. Check the **[!UICONTROL Enabled]** box to activate the current dashboard.

   Si esta opción está deshabilitada, las notificaciones vinculadas a este tablero ya no se envían. Esta opción está deshabilitada de forma predeterminada.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. To modify or create a group, see [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. From the **[!UICONTROL Delivery alerting criteria]** section, click **[!UICONTROL Create element]** to add criteria. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
1. Select the **[!UICONTROL Edit properties]** button. In the **[!UICONTROL Criteria parameters]** tab, define how the criteria will be applied. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

Ahora cada vez que una entrega cumpla con los criterios definidos en este tablero, se enviará una notificación de alerta al grupo de usuarios especificado.

## Delivery alerting criteria {#delivery-alerting-criteria}

### About alerting criteria {#about-alerting-criteria}

To access the delivery alerting criteria, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** and select **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Los siguientes criterios se pueden utilizar en los tableros de alerta de entrega:

* **[!UICONTROL Deliveries failed]**: Cualquier envío programado dentro de un intervalo definido, con un estado erróneo.
* **[!UICONTROL Deliveries with preparation failed]**: Cualquier envío modificado dentro de un intervalo definido para el cual falló el paso de preparación (cálculo de objetivos y generación de contenido). For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Cualquier envío programado dentro de un intervalo definido, con un estado al menos **[!UICONTROL In progress]**, con una relación de error de salida hacia otro sitio mayor que un porcentaje definido.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Cualquier envío programado dentro de un intervalo definido, con un estado al menos **[!UICONTROL In progress]**, con una proporción de error de salida hacia otro sitio durada que un porcentaje definido.
* **[!UICONTROL Deliveries with long start pending]**: Cualquier envío programado dentro de un intervalo definido, con **[!UICONTROL Start pending]** estado durante más tiempo que una duración definida, lo que significa **[!UICONTROL Start pending]** que el sistema aún no tiene en cuenta los mensajes.
* **[!UICONTROL Deliveries with low throughput]**: Cualquier entrega iniciada durante más tiempo que una duración definida, con menos de un porcentaje definido de mensajes procesados, con un rendimiento inferior al valor definido.
* **[!UICONTROL Deliveries in progress]**: Cualquier envío programado dentro de un intervalo definido, con **[!UICONTROL In progress]** el estado.

>[!NOTE]
>
>Todos los parámetros aplicados a los criterios anteriores tienen valores predeterminados. These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

Para cada criterio, puede definir la siguiente configuración:

* **[!UICONTROL Indicators to add in alerts]**, es decir, las columnas que aparecerán en **[!UICONTROL Details]** la sección de notificación para los envíos correspondientes al criterio seleccionado.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, lo que significa la etiqueta y el color que aparecerá junto al criterio de entrega en el resumen de la notificación.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Si se cumple un criterio para una entrega, se repite en cada notificación enviada dentro del período de supervisión. De lo contrario, solo se enviará una alerta al día (en la primera incidencia) según el criterio de alerta de una entrega.

   De forma predeterminada, esta opción se establece una vez al día para todos los criterios.

**Temas relacionados:**

* [Envío de registros](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frecuencia de alertas](../../sending/using/receiving-alerts-when-failures-happen.md#alerting-frequency)
* [Iconos y estados de actividad de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creating a delivery alerting criterion {#creating-a-delivery-alerting-criterion}

Puede crear nuevos criterios de alerta de entrega para adaptarlos mejor a sus necesidades.

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. Go to **Adobe Campaign** &gt; **Administration** &gt; **Development** &gt; **Custom resources** and click **[!UICONTROL Create]**.
1. Select **[!UICONTROL Extend an existing resource]**, select the **[!UICONTROL Delivery]** resource from the drop-down list and click **[!UICONTROL Create]** to edit it.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   For more on extending an existing resource, see [Define the resource](../../developing/using/creating-or-extending-the-resource.md).

1. In the **[!UICONTROL Delivery]** resource, go to the **[!UICONTROL Filter definition]** tab and click **[!UICONTROL Add an element]** to create a filter.

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   For more on creating and editing custom filters, see [Define filters](../../developing/using/configuring-filter-definition.md).

1. Guarde los cambios y publique sus recursos. For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   El filtro se crea y ahora se puede seleccionar en un nuevo criterio de alerta de entrega.

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, select **[!UICONTROL Delivery alerting criteria]** and click **[!UICONTROL Create]**.
1. In the **[!UICONTROL Delivery filter applied by this criterion]** drop-down list, select the filter that you just created.

   ![](assets/delivery-alerting_cus-filter.png)

   Puede definir la configuración de los criterios de la misma manera que con los criterios predeterminados. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).

Una vez creados, estos criterios se pueden agregar a un tablero de alerta de entrega, así como a otros criterios. See [About delivery alerting dashboards](../../sending/using/receiving-alerts-when-failures-happen.md#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Tema relacionado:**

[Adición o ampliación de un recurso](../../developing/using/key-steps-of-adding-a-resource.md)

## Delivery alerting parameters {#delivery-alerting-parameters}

### Criteria parameters {#criteria-parameters}

In the **[!UICONTROL Criteria parameters]** tab of a [delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard), you can define the settings that apply to the criteria selected in this dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Por ejemplo, si se introduce 100 en este campo, se envía una notificación solo para envíos con un destino igual o superior a 100 destinatarios. Este parámetro se aplica a todos los criterios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes y después del tiempo actual. Solo se tienen en cuenta las entregas que tienen una fecha de contacto en este intervalo de tiempo. Este parámetro se aplica a todos los criterios. De forma predeterminada, el valor de este campo se establece en 24 horas.

   For more information on the contact date, see [About the scheduling](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Se envía una notificación para todas las entregas con una relación de error de salida hacia otro sitio suave mayor que el valor especificado. De forma predeterminada, el valor de este campo es 0,05 (5%).

   For more on soft bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Se envía una notificación para todas las entregas con una relación de error de salida hacia otro sitio durada que el valor especificado. De forma predeterminada, el valor de este campo es 0,05 (5%).

   For more on hard bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Se envía una notificación para todos los envíos con **[!UICONTROL Start pending]** estado durante más tiempo que la especificada en este campo, **[!UICONTROL Start pending]** el estado significa que el sistema aún no tiene en cuenta los mensajes.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Para el criterio, solo se tienen en cuenta los envíos iniciados (con **[!UICONTROL In progress]** estado) durante más de la duración **[!UICONTROL Deliveries with low throughput]** especificada.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Solo se toman en cuenta los envíos con un porcentaje de mensajes procesados inferiores al porcentaje especificado para **[!UICONTROL Deliveries with low throughput]** el criterio.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Solo se toman en cuenta los envíos con un rendimiento inferior al valor especificado para **[!UICONTROL Deliveries with low throughput]** el criterio.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Solo se tienen en cuenta los envíos con un porcentaje de mensajes procesados superiores al porcentaje especificado.

### Alerting frequency {#alerting-frequency}

The **[!UICONTROL Frequency of delivery alerting]** option allows to define the delay between two alert sendings. De forma predeterminada, se establece en 10 minutos.

You can change this setting through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

>[!NOTE]
>
>Esta opción se aplica a todos los tableros definidos en Adobe Campaign. No puede configurar una frecuencia específica para cada tablero.

## Delivery alerting reasons {#delivery-alerting-reasons}

The **Delivery alerting** feature keeps all of your involved Adobe Campaign users automatically informed about the delivery execution status, via email and dashboard.

Ahora, cuando reciba una notificación de alerta de entrega, le sugerimos que le proporcione algunas sugerencias.

First of all, check the delivery's **Log** tab to view all information relating to the delivery and proofs. Los iconos rojo y amarillo permiten identificar errores o advertencias. El icono rojo indica un error crítico que impide que se inicie la entrega.

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. Contiene la lista de mensajes enviados y sus estados. There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Estos son algunos posibles motivos para recibir notificaciones de alerta según los criterios que se cumplen para una entrega.

* **[!UICONTROL Deliveries failed]**: Este criterio le informa de todos los envíos con un estado erróneo. Puede deberse a:

   * Un problema con el servidor de entrega (MTA, Agent Transfer Agent)
   * Un tiempo de espera de conexión entre el servidor de entrega de Adobe Campaign y el servidor receptor
   * Un problema de entrega
   * Flujo de trabajo erróneo
   Si la entrega se activa con un flujo de trabajo, compruebe si el flujo de trabajo se ha iniciado correctamente. For more on this, see [Executing a workflow](../../automating/using/executing-a-workflow.md). De lo contrario, póngase en contacto con el administrador de Adobe Campaign para resolver el problema.

* **[!UICONTROL Deliveries with preparation failed]**: Se puede producir un error durante la preparación de la entrega en los siguientes casos:

   * Falta un asunto en la entrega.
   * Hay una sintaxis incorrecta en los campos de personalización.
   * Falta el objetivo.
   * La entrega sobrepasa el límite de tamaño.
   For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md). Sin embargo, estos errores suelen conocerse durante el análisis de mensajes. See [Control rules](../../administration/using/control-rules.md).

* The possible causes for a **[!UICONTROL Delivery with bad error ratio for soft bounces]** alert can be:

   * El servidor del destinatario está inactivo.
   * El buzón de correo del destinatario está lleno.
   For more information, check the **[!UICONTROL Exclusion logs]** and **[!UICONTROL Exclusion causes]** tabs of the delivery logs. See [Exclusion logs](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   The possible causes for a **[!UICONTROL Delivery with bad error ratio for hard bounces]** alert can be:

   * El destinatario está bloqueado, lo que significa que ya no desean ponerse en contacto con ellos.
   * La dirección de correo electrónico del destinatario no existe.
   * El dominio del destinatario no existe.
   * El servidor del destinatario está bloqueando la entrega.
   Para evitar errores de salida hacia otro sitio y suave, siga las optimizaciones siguientes:

   * Cree reglas de tipología para excluir una parte del objetivo del mensaje durante el análisis de entrega, como los destinatarios en cuarentena. See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * Actualice periódicamente la base de datos de clientes para mantener procesos de administración de cuarentena adecuados. See [About quarantines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * En términos generales, mejore la capacidad de entrega lo mejor posible. See the Adobe Campaign v7 [Managing deliverability](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) detailed guide and contact your Adobe Campaign administrator for assistance.



* **[!UICONTROL Deliveries with long start pending]**: Esto suele significar que existe un problema en el nivel de MTA (Agent Transfer Agent). El proceso de ejecución está esperando la disponibilidad de algunos recursos. Puede que la llamada a acción no se haya iniciado.

   **[!UICONTROL Deliveries with low throughput]**: Nuevamente, se trata de un problema de entrega que significa que el MTA es demasiado lento.

   Para obtener más información sobre estos problemas, póngase en contacto con su administrador de Adobe Campaign.

**Temas relacionados:**

* [Explicación de los fallos de entrega](../../sending/using/understanding-delivery-failures.md)
* [Información sobre la administración de cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Administración de listas bloqueadas en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)


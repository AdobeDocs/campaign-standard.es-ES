---
solution: Campaign Standard
product: campaign
title: Recibir alertas cuando se produzcan errores
description: Aprenda a utilizar el sistema de gestión de alertas.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 3%

---


# Recibir alertas cuando se produzcan errores{#receiving-alerts-when-failures-happen}

## Acerca de las alertas de envío {#about-delivery-alerting}

La función **Delivery alert alert** es un sistema de administración de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Las notificaciones enviadas contienen un informe basado de forma predeterminada en los siguientes criterios:

* Entregas fallidas
* Entregas con una preparación fallida
* Entregas con una relación de error de rechazo suave incorrecta
* Entregas con una mala proporción de errores de devolución
* Entregas con un estado pendiente mayor que el habitual
* Entregas con un bajo rendimiento
* Entregas en curso

Los destinatarios de las alertas pueden monitorizar los envíos que está procesando Adobe Campaign y realizar las acciones adecuadas cuando hay problemas en su ejecución.

Estas notificaciones de alerta se pueden personalizar en función de criterios de alerta específicos definidos a través de un panel en la interfaz de Adobe Campaign.

>[!NOTE]
>
>Las notificaciones de alertas se envían únicamente por correo electrónico.

Las notificaciones enviadas contienen:

* Un **[!UICONTROL Summary]** que muestra el número de envíos que cumplen los criterios definidos y la etiqueta/color que se ha elegido para cada criterio.
* Una sección **[!UICONTROL Details]** que enumera todos los criterios de envío definidos para el panel correspondiente y todos los envíos para cada criterio.

![](assets/delivery-alerting_notification.png)

## Tableros de alerta de envío {#delivery-alerting-dashboards}

### Acerca de los paneles de alerta de envío {#about-delivery-alerting-dashboards}

Para administrar los destinatarios de las notificaciones, definir los criterios de alerta y acceder al historial de las alertas, debe utilizar los paneles.

>[!NOTE]
>
>Para acceder y configurar los paneles y los criterios de alerta, debe tener derechos de administración o aparecer en el grupo de seguridad **Delivery supervisors** . Los usuarios de Standard no pueden acceder a los paneles de la interfaz de Adobe Campaign. Solo pueden recibir las notificaciones de alerta. Para obtener más información sobre los usuarios y la seguridad en Adobe Campaign, consulte [Tipos de usuarios](../../administration/using/users-management.md) y [Acerca de los grupos de seguridad](../../administration/using/managing-groups-and-users.md#about-security-groups).

Desde la interfaz de Adobe Campaign, puede:

* Cree y administre tableros de alertas de entrega. Consulte [Creación de un panel de alerta de envío](#creating-a-delivery-alerting-dashboard).
* Defina y administre los criterios de alerta de envío para cada tablero. Por ejemplo, puede generar alertas basadas en envíos con errores de preparación o envíos con un rendimiento bajo solamente. Consulte [Acerca de los criterios de alerta](#about-alerting-criteria).
* Modifique los parámetros de criterios para cada tablero. Consulte [Parámetros de criterios](#criteria-parameters).
* Defina un grupo de destinatarios para cada tablero.

   Por ejemplo, desea informar a los usuarios solo con derechos de administración de los envíos fallidos. Sin embargo, desea que los usuarios de marketing reciban información sobre los envíos con una tasa de error de rechazo suave. Por lo tanto, debe crear dos tableros diferentes y definir los criterios que desee para cada grupo de destinatarios.

* Acceda al historial de todas las alertas enviadas para cada panel.

   Al seleccionar un tablero, la última alerta enviada para este tablero se muestra de forma predeterminada. Todas las alertas enviadas se muestran a la izquierda de la pantalla. Haga clic en un elemento de la lista **[!UICONTROL History]** para acceder a las alertas correspondientes.

![](assets/delivery-alerting_dashboard.png)

### Creación de un panel de alertas de envío {#creating-a-delivery-alerting-dashboard}

Si desea enviar notificaciones basadas en criterios específicos a distintos grupos de usuarios, debe utilizar varios paneles. Para crear un tablero nuevo:

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Seleccione **[!UICONTROL Delivery alerting dashboards]** y haga clic en **[!UICONTROL Create]**.
1. Marque la casilla **[!UICONTROL Enabled]** para activar el tablero actual.

   Si esta opción está desactivada, ya no se envían las notificaciones vinculadas a este panel. Esta opción está desactivada de forma predeterminada.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Seleccione el grupo de destinatarios al que desea enviar la notificación en la lista desplegable **[!UICONTROL Alert group]**. Para modificar o crear un grupo, consulte [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. En la sección **[!UICONTROL Delivery alerting criteria]** , haga clic en **[!UICONTROL Create element]** para agregar criterios. Consulte [Acerca de los criterios de alerta](#about-alerting-criteria).
1. Seleccione el botón **[!UICONTROL Edit properties]**. En la pestaña **[!UICONTROL Criteria parameters]**, defina cómo se aplicarán los criterios. Consulte [Parámetros de criterios](#criteria-parameters).
1. Haga clic en **[!UICONTROL Create]** para guardar el tablero.

Ahora, cada vez que una entrega cumple los criterios definidos en este panel, se envía una notificación de alerta al grupo de usuarios especificado.

## Criterios de alerta de envío {#delivery-alerting-criteria}

### Acerca de los criterios de alerta {#about-alerting-criteria}

Para acceder a los criterios de alerta de envío, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** y seleccione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

En los paneles de alerta de envío se pueden usar los criterios siguientes:

* **[!UICONTROL Deliveries failed]**: Cualquier entrega programada dentro de un intervalo definido, con un estado incorrecto.
* **[!UICONTROL Deliveries with preparation failed]**: Cualquier entrega modificado dentro de un intervalo definido y para el que se ha producido un error en el paso de preparación (cálculo del objetivo y generación de contenido). Para obtener más información, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Cualquier entrega programada dentro de un intervalo definido, con un estado de al menos  **[!UICONTROL In progress]**, con una proporción de error de rechazo suave buena a un porcentaje definido.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Cualquier envío programado dentro de un intervalo definido, con un estado de al menos  **[!UICONTROL In progress]**, con una proporción de error de rechazo grave buena a la definida.
* **[!UICONTROL Deliveries with long start pending]**: Cualquier entrega programada dentro de un intervalo definido, con un  **[!UICONTROL Start pending]** estado de más de una duración definida, lo que significa que el  **[!UICONTROL Start pending]** estado no ha tenido en cuenta los mensajes aún.
* **[!UICONTROL Deliveries with low throughput]**: Cualquier envío iniciado durante más de una duración definida, con menos de un porcentaje definido de mensajes procesados, con un rendimiento inferior al valor definido.
* **[!UICONTROL Deliveries in progress]**: Cualquier envío programado dentro de un intervalo definido, con el  **[!UICONTROL In progress]** estado .

>[!NOTE]
>
>Todos los parámetros que se aplican a los criterios anteriores tienen valores predeterminados. Estos valores se pueden cambiar en la pestaña **[!UICONTROL Criteria parameters]** de los paneles de alerta de envío. Consulte [Parámetros de criterios](#criteria-parameters).

Puede seleccionar cualquier elemento de la lista **[!UICONTROL Delivery alerting criteria]** para acceder a sus detalles.

![](assets/delivery-alerting_criteria_definition.png)

Para cada criterio, puede definir la siguiente configuración:

* **[!UICONTROL Indicators to add in alerts]**, es decir, las columnas que aparecen en la  **[!UICONTROL Details]** sección de la notificación para los envíos correspondientes al criterio seleccionado.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, es decir, la etiqueta y el color que aparecen junto al criterio de entrega en el resumen de la notificación.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Si se cumple un criterio para una entrega, se repite en cada notificación enviada dentro del periodo de monitorización. De lo contrario, solo se enviará una alerta por día (en la primera incidencia) según el criterio de alerta para una entrega.

   De forma predeterminada, esta opción se establece en una vez al día para todos los criterios.

**Temas relacionados:**

* [Registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frecuencia de alertas](#alerting-frequency)
* [Iconos y estados de la actividad de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creación de un criterio de alerta de envío {#creating-a-delivery-alerting-criterion}

Puede crear nuevos criterios de alerta de envío para adaptarlos mejor a sus necesidades.

Por ejemplo, puede crear un nuevo criterio que permita enviar una notificación que enumere todos los envíos con estado **[!UICONTROL Finished]**.

Para ello, primero debe ampliar el recurso **Delivery** y agregar un nuevo filtro que le permita seleccionar solo los envíos con estado **[!UICONTROL Finished]**.

1. Vaya a **Adobe Campaign** > **Administración** > **Desarrollo** > **Recursos personalizados** y haga clic en **[!UICONTROL Create]**.
1. Seleccione **[!UICONTROL Extend an existing resource]**, seleccione el recurso **[!UICONTROL Delivery]** en la lista desplegable y haga clic en **[!UICONTROL Create]** para editarlo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obtener más información sobre la ampliación de un recurso existente, consulte [Definición del recurso](../../developing/using/creating-or-extending-the-resource.md).

1. En el recurso **[!UICONTROL Delivery]**, vaya a la pestaña **[!UICONTROL Filter definition]** y haga clic en **[!UICONTROL Add an element]** para crear un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Edite la nueva definición del filtro: en la ventana **[!UICONTROL Filter definition]** , arrastre y suelte el elemento **[!UICONTROL Status]** en el espacio de trabajo y seleccione **[!UICONTROL Finished]** como condición de filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obtener más información sobre la creación y edición de filtros personalizados, consulte [Definir filtros](../../developing/using/configuring-filter-definition.md).

1. Guarde los cambios y publique los recursos. Para obtener más información, consulte [Publicación de un recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   El filtro se crea y ahora se puede seleccionar en un nuevo criterio de alerta de envío.

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, seleccione **[!UICONTROL Delivery alerting criteria]** y haga clic en **[!UICONTROL Create]**.
1. En la lista desplegable **[!UICONTROL Delivery filter applied by this criterion]**, seleccione el filtro que acaba de crear.

   ![](assets/delivery-alerting_cus-filter.png)

   Puede definir la configuración del criterio del mismo modo que para los criterios predeterminados. Consulte [Acerca de los criterios de alerta](#about-alerting-criteria).

Una vez creados, estos criterios se pueden añadir a un panel de alertas de envío, así como a otros criterios. Consulte [Acerca de los paneles de alerta de envío](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Temas relacionados:**

[Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parámetros de alerta de envío {#delivery-alerting-parameters}

### Parámetros de criterios {#criteria-parameters}

En la pestaña **[!UICONTROL Criteria parameters]** de un [panel de alertas de envío](#creating-a-delivery-alerting-dashboard), puede definir la configuración que se aplica a los criterios seleccionados en este panel.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Por ejemplo, si introduce 100 en este campo, se envía una notificación solo para las entregas con un objetivo igual o bueno a 100 destinatarios. Este parámetro se aplica a todos los criterios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes y después de la hora actual. Solo se tienen en cuenta las entregas con una fecha de contacto en este intervalo de tiempo. Este parámetro se aplica a todos los criterios. De forma predeterminada, el valor de este campo se establece en 24 horas.

   Para obtener más información sobre la fecha de contacto, consulte [Acerca de la programación](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Se envía una notificación para todas las entregas con una proporción de error de rechazo leve buena que el valor especificado. De forma predeterminada, el valor de este campo se establece en 0,05 (5%).

   Para obtener más información sobre los errores de rechazos leves, consulte [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) y [List of delivery failed types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Se envía una notificación para todas las entregas con una proporción de error de rechazo grave buena que el valor especificado. De forma predeterminada, el valor de este campo se establece en 0,05 (5%).

   Para obtener más información sobre los errores de rechazo grave, consulte [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) y [Lista de tipos de error de envío](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Se envía una notificación para todas las entregas con un  **[!UICONTROL Start pending]** estado de más de la duración especificada en este campo, lo que significa que el sistema aún no ha tenido en  **[!UICONTROL Start pending]** cuenta los mensajes.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Solo se tienen en cuenta para el  **[!UICONTROL In progress]** criterio los envíos iniciados (con  **[!UICONTROL Deliveries with low throughput]** estado ) durante más de la duración especificada.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Solo se tienen en cuenta para el  **[!UICONTROL Deliveries with low throughput]** criterio los envíos con un porcentaje de mensajes procesados inferior al porcentaje especificado.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Solo se tienen en cuenta para el  **[!UICONTROL Deliveries with low throughput]** criterio los envíos con un rendimiento inferior al valor especificado.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Solo se tienen en cuenta las entregas con un porcentaje de mensajes procesados superior al porcentaje especificado.

### Frecuencia de alerta {#alerting-frequency}

La opción **[!UICONTROL Frequency of delivery alerting]** permite definir el retardo entre dos envíos de alertas. De forma predeterminada, se establece en 10 minutos.

Puede cambiar esta configuración mediante el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

>[!NOTE]
>
>Esta opción se aplica a todos los tableros definidos en Adobe Campaign. No puede establecer una frecuencia específica para cada tablero.

## Motivos de las alertas de entrega {#delivery-alerting-reasons}

La función **Delivery alert alert** mantiene informados automáticamente a todos los usuarios de Adobe Campaign implicados sobre el estado de ejecución del envío, a través de correo electrónico y tablero.

Ahora, cuando reciba una notificación de alerta de envío, aquí tiene algunas sugerencias sobre lo que puede hacer.

En primer lugar, marque la pestaña **Log** del envío para ver toda la información relacionada con el envío y las pruebas. Los iconos rojo y amarillo le permiten identificar errores o advertencias. El icono rojo indica un error crítico que impide que se inicie el envío.

Para ver el historial de cada ocurrencia de un envío, seleccione la pestaña **[!UICONTROL Sending logs]** . Contiene la lista de mensajes enviados y sus estados. Allí puede comprobar el estado de envío de cada destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). Para obtener más información, consulte [Envío de registros](../../sending/using/monitoring-a-delivery.md#sending-logs).

A continuación, se indican algunos motivos posibles para recibir notificaciones de alerta según los criterios que se cumplan para una entrega.

* **[!UICONTROL Deliveries failed]**: Este criterio le informa de todas las entregas con un estado incorrecto. Puede deberse a:

   * Un problema con el servidor de entrega (MTA, Agente de transferencia de mensajes)
   * Tiempo de espera de conexión entre el servidor de entrega de Adobe Campaign y el servidor receptor
   * Un problema de envío
   * Un flujo de trabajo incorrecto

   Si la entrega se activa con un flujo de trabajo, compruebe si dicho flujo de trabajo se inició correctamente. Para obtener más información, consulte [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md). De lo contrario, póngase en contacto con el administrador de Adobe Campaign para resolver el problema.

* **[!UICONTROL Deliveries with preparation failed]**: Se puede producir un error durante la preparación del envío en los siguientes casos:

   * A la entrega le falta un asunto.
   * Hay una sintaxis incorrecta en los campos de personalización.
   * Falta el objetivo.
   * La entrega supera el límite de tamaño.

   Para obtener más información, consulte [Preparación del envío](../../sending/using/preparing-the-send.md). Sin embargo, estos errores generalmente se detectan durante el análisis del mensaje. Consulte [Reglas de control](../../sending/using/control-rules.md).

* Las posibles causas de una alerta **[!UICONTROL Delivery with bad error ratio for soft bounces]** pueden ser:

   * El servidor del destinatario está inactivo.
   * El buzón del destinatario está lleno.

   Para obtener más información, consulte las pestañas **[!UICONTROL Exclusion logs]** y **[!UICONTROL Exclusion causes]** de los registros de envío. Consulte [Registros de exclusión](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   Las posibles causas de una alerta **[!UICONTROL Delivery with bad error ratio for hard bounces]** pueden ser:

   * El destinatario se añade a la  de lista de bloqueados, lo que significa que ya no desea que se le siga contactando.
   * La dirección de correo electrónico del destinatario no existe.
   * El dominio del destinatario no existe.
   * El servidor del destinatario está bloqueando la entrega.

   Para evitar errores de rechazos leves y graves, siga las prácticas recomendadas a continuación:

   * Genere reglas de tipología de filtrado para excluir una parte del destinatario de mensajes durante el análisis de envío, como los destinatarios en cuarentena. Consulte [Creación de una regla de filtrado](../../sending/using/filtering-rules.md).
   * Actualice con regularidad la base de datos de clientes para mantener buenos procesos de administración de cuarentena. Consulte [Acerca de las cuarentenas](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * En términos generales, mejore la capacidad de envío lo mejor que pueda. Consulte la documentación detallada de Adobe Campaign [Deliverability](../../sending/using/about-deliverability.md) y póngase en contacto con el administrador de Adobe Campaign para obtener ayuda.



* **[!UICONTROL Deliveries with long start pending]**: Normalmente esto significa que hay un problema en el nivel de MTA (Agente de transferencia de mensajes). El proceso de ejecución está esperando a que estén disponibles algunos recursos. Es posible que el MTA no se haya iniciado.

   **[!UICONTROL Deliveries with low throughput]**: De nuevo, se trata de un problema de entrega que significa que el MTA es demasiado lento.

   Para obtener más información sobre estos problemas, póngase en contacto con su administrador de Adobe Campaign.

**Temas relacionados:**

* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)


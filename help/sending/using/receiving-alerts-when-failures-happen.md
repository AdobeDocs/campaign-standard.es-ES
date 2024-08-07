---
title: Recepción de alertas cuando se produzcan errores
description: Aprenda a utilizar el sistema de administración de alertas.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2038'
ht-degree: 2%

---

# Recepción de alertas cuando se produzcan errores{#receiving-alerts-when-failures-happen}

## Acerca de las alertas de envío {#about-delivery-alerting}

La característica **Alerta de entrega** es un sistema de administración de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Las notificaciones enviadas contienen un informe basado de forma predeterminada en los siguientes criterios:

* Envíos fallidos
* Envíos con preparación fallida
* Envíos con una proporción de errores de rechazos leves incorrecta
* Envíos con una proporción de errores de rechazo grave incorrecta
* Envíos con un estado pendiente más largo de lo habitual
* Envíos con un bajo rendimiento
* Entregas en curso

Los destinatarios de las alertas pueden monitorizar los envíos que Adobe Campaign está procesando y realizar las acciones adecuadas cuando hay problemas en su ejecución.

Estas notificaciones de alerta se pueden personalizar según los criterios de alerta específicos definidos a través de un panel en la interfaz de Adobe Campaign.

>[!NOTE]
>
>Las notificaciones de alerta se envían únicamente por correo electrónico.

Las notificaciones enviadas contienen:

* Un **[!UICONTROL Summary]** que muestra el número de envíos que cumplen los criterios definidos y la etiqueta/color que eligió para cada criterio.
* Una sección **[!UICONTROL Details]** que enumera todos los criterios de entrega definidos para el panel correspondiente y todas las entregas de cada criterio.

![](assets/delivery-alerting_notification.png)

## Paneles de alertas de envío {#delivery-alerting-dashboards}

### Acerca de los paneles de alertas de envío {#about-delivery-alerting-dashboards}

Para administrar los destinatarios de las notificaciones, definir los criterios de alerta y acceder al historial de las alertas, debe utilizar los paneles.

>[!NOTE]
>
>Para acceder y configurar los paneles y los criterios de alerta, debe tener derechos de administración o aparecer en el grupo de seguridad **Supervisores de entrega**. Los usuarios estándar no pueden acceder a los paneles de la interfaz de Adobe Campaign. Solo pueden recibir las notificaciones de alerta. Para obtener más información sobre usuarios y seguridad en Adobe Campaign, consulte [Tipos de usuarios](../../administration/using/users-management.md) y [Acerca de los grupos de seguridad](../../administration/using/managing-groups-and-users.md#about-security-groups).

Desde la interfaz de Adobe Campaign, puede:

* Cree y administre paneles de alertas de entrega. Consulte [Creación de un panel de alertas de envío](#creating-a-delivery-alerting-dashboard).
* Defina y administre criterios de alerta de entrega para cada panel. Por ejemplo, puede generar alertas basadas en envíos con preparación fallida o envíos con un rendimiento bajo únicamente. Ver [Acerca de los criterios de alerta](#about-alerting-criteria).
* Modifique los parámetros de criterio para cada tablero. Consulte [Parámetros de criterios](#criteria-parameters).
* Defina un grupo de destinatarios para cada panel.

  Por ejemplo, desea informar a los usuarios con derechos de administración solo de los envíos fallidos. Sin embargo, desea que los usuarios de marketing reciban información sobre los envíos con una proporción de errores no válidos de rebote suave. Por lo tanto, debe crear dos paneles diferentes y definir los criterios que desee para cada grupo de destinatarios.

* Acceda al historial de todas las alertas enviadas para cada panel.

  Al seleccionar un tablero, se muestra de forma predeterminada la última alerta enviada para este tablero. Todas las alertas enviadas se muestran a la izquierda de la pantalla. Haga clic en un elemento de la lista **[!UICONTROL History]** para obtener acceso a las alertas correspondientes.

![](assets/delivery-alerting_dashboard.png)

### Creación de un panel de alertas de entrega {#creating-a-delivery-alerting-dashboard}

Si desea enviar notificaciones basadas en criterios específicos a diferentes grupos de usuarios, debe utilizar varios paneles. Para crear un nuevo tablero:

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Seleccione **[!UICONTROL Delivery alerting dashboards]** y haga clic en **[!UICONTROL Create]**.
1. Marque la casilla **[!UICONTROL Enabled]** para activar el tablero actual.

   Si esta opción está desactivada, ya no se envían las notificaciones vinculadas a este panel. Esta opción está desactivada de forma predeterminada.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Seleccione el grupo de destinatarios al que desee notificar en la lista desplegable **[!UICONTROL Alert group]**. Para modificar o crear un grupo, vea [Crear un grupo de seguridad y asignar usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. En la sección **[!UICONTROL Delivery alerting criteria]**, haga clic en **[!UICONTROL Create element]** para agregar criterios. Ver [Acerca de los criterios de alerta](#about-alerting-criteria).
1. Seleccione el botón **[!UICONTROL Edit properties]**. En la ficha **[!UICONTROL Criteria parameters]**, defina cómo se aplicarán los criterios. Consulte [Parámetros de criterios](#criteria-parameters).
1. Haga clic en **[!UICONTROL Create]** para guardar el tablero.

Ahora, cada vez que una entrega cumple los criterios definidos en este panel, se envía una notificación de alerta al grupo de usuarios especificado.

## Criterios de alertas de envío {#delivery-alerting-criteria}

### Acerca de los criterios de alerta {#about-alerting-criteria}

Para acceder a los criterios de alerta de entrega, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** y seleccione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

En los paneles de alertas de envío se pueden utilizar los siguientes criterios:

* **[!UICONTROL Deliveries failed]**: cualquier envío programado dentro de un intervalo definido, con un estado erróneo.
* **[!UICONTROL Deliveries with preparation failed]**: cualquier envío modificado dentro de un intervalo definido, para el cual el paso de preparación (cálculo del objetivo y generación de contenido) ha fallado. Para obtener más información, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: cualquier envío programado dentro de un intervalo definido, con un estado de al menos **[!UICONTROL In progress]**, con una proporción de errores de rebote suave mayor que un porcentaje definido.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: cualquier envío programado dentro de un intervalo definido, con un estado de al menos **[!UICONTROL In progress]**, con una proporción de errores de devolución dura mayor que un porcentaje definido.
* **[!UICONTROL Deliveries with long start pending]**: cualquier envío programado dentro de un intervalo definido, con un estado **[!UICONTROL Start pending]** durante más de una duración definida, estado **[!UICONTROL Start pending]** que significa que el sistema aún no ha tenido en cuenta los mensajes.
* **[!UICONTROL Deliveries with low throughput]**: cualquier envío que se inicie durante más tiempo del definido, con menos de un porcentaje definido de mensajes procesados, con un rendimiento inferior a un valor definido.
* **[!UICONTROL Deliveries in progress]**: cualquier envío programado dentro de un intervalo definido, con el estado **[!UICONTROL In progress]**.

>[!NOTE]
>
>Todos los parámetros que se aplican a los criterios anteriores tienen valores predeterminados. Estos valores se pueden cambiar en la pestaña **[!UICONTROL Criteria parameters]** de los paneles de alertas de envío. Consulte [Parámetros de criterios](#criteria-parameters).

Puede seleccionar cualquier elemento de la lista **[!UICONTROL Delivery alerting criteria]** para acceder a sus detalles.

![](assets/delivery-alerting_criteria_definition.png)

Para cada criterio, puede definir la siguiente configuración:

* **[!UICONTROL Indicators to add in alerts]**, que significa las columnas que aparecerán en la sección **[!UICONTROL Details]** de la notificación para los envíos correspondientes al criterio seleccionado.

  ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, que significa la etiqueta y el color que aparecerán junto al criterio de envío en el resumen de la notificación.

  ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: si se cumple un criterio para una entrega, se repite en cada notificación enviada dentro del período de monitorización. De lo contrario, solo se envía una alerta al día (en la primera incidencia) según el criterio de alerta de una entrega.

  De forma predeterminada, esta opción se establece en una vez al día para todos los criterios.

**Temas relacionados:**

* [Envío de registros](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frecuencia de alerta](#alerting-frequency)
* [Iconos y estados de la actividad de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creación de un criterio de alerta de entrega {#creating-a-delivery-alerting-criterion}

Puede crear nuevos criterios de alerta de entrega para adaptarlos mejor a sus necesidades.

Por ejemplo, puede crear un nuevo criterio que permita enviar una notificación con todas las entregas con un estado **[!UICONTROL Finished]**.

Para ello, primero debe ampliar el recurso **Delivery** y agregar un nuevo filtro que le permita seleccionar solo los envíos con un estado **[!UICONTROL Finished]**.

1. Vaya a **Adobe Campaign** > **Administración** > **Desarrollo** > **Recursos personalizados** y haga clic en **[!UICONTROL Create]**.
1. Seleccione **[!UICONTROL Extend an existing resource]**, seleccione el recurso **[!UICONTROL Delivery]** de la lista desplegable y haga clic en **[!UICONTROL Create]** para editarlo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obtener más información sobre cómo ampliar un recurso existente, consulte [Definir el recurso](../../developing/using/creating-or-extending-the-resource.md).

1. En el recurso **[!UICONTROL Delivery]**, vaya a la ficha **[!UICONTROL Filter definition]** y haga clic en **[!UICONTROL Add an element]** para crear un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Edite la nueva definición del filtro: en la ventana **[!UICONTROL Filter definition]**, arrastre y suelte el elemento **[!UICONTROL Status]** en el área de trabajo y seleccione **[!UICONTROL Finished]** como condición de filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obtener más información sobre cómo crear y editar filtros personalizados, consulte [Definir filtros](../../developing/using/configuring-filter-definition.md).

1. Guarde los cambios y publique los recursos. Para obtener más información, consulte [Publicación de un recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   El filtro se crea y ahora se puede seleccionar en un nuevo criterio de alerta de entrega.

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, seleccione **[!UICONTROL Delivery alerting criteria]** y haga clic en **[!UICONTROL Create]**.
1. En la lista desplegable **[!UICONTROL Delivery filter applied by this criterion]**, seleccione el filtro que acaba de crear.

   ![](assets/delivery-alerting_cus-filter.png)

   Puede definir la configuración del criterio del mismo modo que para los criterios predeterminados. Ver [Acerca de los criterios de alerta](#about-alerting-criteria).

Una vez creados, estos criterios se pueden añadir a un panel de alertas de envío, así como otros criterios. Ver [Acerca de los paneles de alertas de envío](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Temas relacionados:**

[Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parámetros de alerta de envío {#delivery-alerting-parameters}

### Parámetros de criterios {#criteria-parameters}

En la ficha **[!UICONTROL Criteria parameters]** de un [panel de alertas de entrega](#creating-a-delivery-alerting-dashboard), puede definir la configuración que se aplica a los criterios seleccionados en este panel.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: por ejemplo, si introduce 100 en este campo, se envía una notificación solo para las entregas con un objetivo igual o superior a 100 destinatarios. Este parámetro se aplica a todos los criterios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: número de horas antes y después de la hora actual. Solo se tienen en cuenta las entregas que tienen una fecha de contacto en este intervalo de tiempo. Este parámetro se aplica a todos los criterios. De forma predeterminada, el valor de este campo se establece en 24 horas.

  Para obtener más información sobre la fecha de contacto, consulte [Acerca de la programación](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: se envía una notificación para todas las entregas con una proporción de errores de devolución suave mayor que el valor especificado. De forma predeterminada, el valor de este campo se establece en 0,05 (5 %).

  Para obtener más información sobre los errores de rechazos leves, consulte [Calificación de correos rechazados](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) y [Lista de tipos de errores de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: se envía una notificación para todas las entregas con una proporción de errores de devolución grave mayor que el valor especificado. De forma predeterminada, el valor de este campo se establece en 0,05 (5 %).

  Para obtener más información sobre los errores de devoluciones graves, consulte [Calificación de correos rechazados](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) y [Lista de tipos de errores de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: se envía una notificación para todas las entregas con un estado **[!UICONTROL Start pending]** durante más tiempo que el especificado en este campo, estado **[!UICONTROL Start pending]** que significa que el sistema aún no ha tenido en cuenta los mensajes.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: solo se tienen en cuenta las entregas iniciadas (con estado **[!UICONTROL In progress]**) durante más tiempo del especificado para el criterio **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: solo se tienen en cuenta las entregas con un porcentaje de mensajes procesados inferior al porcentaje especificado para el criterio **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: solo se tienen en cuenta los envíos con un rendimiento inferior al valor especificado para el criterio **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: solo se tienen en cuenta las entregas con un porcentaje de mensajes procesados mayor que el porcentaje especificado.

### Frecuencia de alerta {#alerting-frequency}

La opción **[!UICONTROL Frequency of delivery alerting]** permite definir el retraso entre dos envíos de alertas. De forma predeterminada, se establece en 10 minutos.

Puede cambiar esta configuración a través del menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

>[!NOTE]
>
>Esta opción se aplica a todos los paneles definidos en Adobe Campaign. No puede establecer una frecuencia específica para cada panel.

## Motivos de alerta de envío {#delivery-alerting-reasons}

La función **Alerta de entrega** mantiene a todos los usuarios de Adobe Campaign involucrados informados automáticamente sobre el estado de ejecución de la entrega, a través del correo electrónico y el panel.

Ahora, cuando reciba una notificación de alerta de entrega, aquí hay algunas sugerencias sobre lo que puede hacer.

En primer lugar, compruebe la pestaña **Log** de la entrega para ver toda la información relacionada con la entrega y las pruebas. Los iconos rojo y amarillo le permiten identificar errores o advertencias. El icono rojo indica un error crítico que impide que se inicie el envío.

Para ver el historial de cada ocurrencia de una entrega, seleccione la pestaña **[!UICONTROL Sending logs]**. Contiene la lista de mensajes enviados y sus estados. Aquí puede comprobar el estado de entrega de cada destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). Para obtener más información, consulte [Registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs).

Estos son algunos de los posibles motivos para recibir notificaciones de alerta según los criterios que se cumplen para una entrega.

* **[!UICONTROL Deliveries failed]**: este criterio le informa de todas las entregas con un estado erróneo. Puede deberse a lo siguiente:

   * Problema con el servidor de entrega (MTA, Agente de transferencia de mensajes)
   * Tiempo de espera de conexión entre el servidor de envío de Adobe Campaign y el servidor receptor
   * Un problema de envío
   * Un flujo de trabajo erróneo

  Si la entrega se activa con un flujo de trabajo, compruebe si dicho flujo de trabajo se inició correctamente. Para obtener más información, consulte [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md). De lo contrario, póngase en contacto con el administrador de Adobe Campaign para solucionar el problema.

* **[!UICONTROL Deliveries with preparation failed]**: se puede producir un error durante la preparación del envío en los siguientes casos:

   * Falta un asunto en la entrega.
   * Hay una sintaxis incorrecta en los campos de personalización.
   * Falta el destino.
   * La entrega supera el límite de tamaño.

  Para obtener más información, consulte [Preparación del envío](../../sending/using/preparing-the-send.md). Sin embargo, estos errores generalmente se detectan durante el análisis del mensaje. Ver [Reglas de control](../../sending/using/control-rules.md).

* Las posibles causas de una alerta **[!UICONTROL Delivery with bad error ratio for soft bounces]** pueden ser:

   * El servidor del destinatario está inactivo.
   * El buzón del destinatario está lleno.

  Para obtener más información, consulte las fichas **[!UICONTROL Exclusion logs]** y **[!UICONTROL Exclusion causes]** de los registros de envío. Ver [registros de exclusión](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

  Las posibles causas de una alerta **[!UICONTROL Delivery with bad error ratio for hard bounces]** pueden ser:

   * El destinatario se añade a la lista de bloqueados de la, lo que significa que ya no desea que se le contacte.
   * La dirección de correo electrónico del destinatario no existe.
   * El dominio del destinatario no existe.
   * El servidor del destinatario está bloqueando la entrega.

  Para evitar errores de rechazos leves y graves, siga las prácticas recomendadas a continuación:

   * Cree reglas de tipología de filtrado para excluir una parte del destinatario del mensaje durante el análisis de la entrega, como los destinatarios en cuarentena. Consulte [Creación de una regla de filtrado](../../sending/using/filtering-rules.md).
   * Actualice regularmente la base de datos de clientes para mantener buenos procesos de administración de cuarentena. Ver [Acerca de las cuarentenas](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * En términos generales, mejore la capacidad de envío lo mejor que pueda. Consulte la documentación detallada de Adobe Campaign [Envío](../../sending/using/about-deliverability.md) y póngase en contacto con su administrador de Adobe Campaign para obtener ayuda.

* **[!UICONTROL Deliveries with long start pending]**: Normalmente esto significa que hay un problema en el nivel de MTA (Agente de transferencia de mensajes). El proceso de ejecución está esperando a que estén disponibles algunos recursos. Es posible que el MTA no se haya iniciado.

  **[!UICONTROL Deliveries with low throughput]**: de nuevo, este es un problema de entrega que significa que el MTA es demasiado lento.

  Para obtener más información sobre estos problemas, póngase en contacto con el administrador de Adobe Campaign.

**Temas relacionados:**

* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

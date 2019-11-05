---
title: Recibir alertas cuando se produzcan errores
description: Aprenda a utilizar el sistema de gestión de alertas.
page-status-flag: nunca activado
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: monitoreo-mensajes
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Recibir alertas cuando se produzcan errores{#receiving-alerts-when-failures-happen}

## Acerca de las alertas de entrega {#about-delivery-alerting}

La función de alerta **de** envío es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Las notificaciones enviadas contienen un informe basado de forma predeterminada en los siguientes criterios:

* Entregas fallidas
* Entregas con error de preparación
* Entregas con una relación de error de devolución en blanco incorrecta
* Entregas con un índice de error de devolución en bruto incorrecto
* Entregas con un estado pendiente mayor que el habitual
* Entregas con un bajo rendimiento
* Entregas en curso

Los destinatarios de las alertas pueden supervisar las entregas que está procesando Adobe Campaign y realizar las acciones oportunas cuando hay problemas en su ejecución.

Estas notificaciones de alerta se pueden personalizar en función de criterios de alerta específicos definidos mediante un tablero en la interfaz de Adobe Campaign.

>[!NOTE]
>
>Las notificaciones de alertas se envían únicamente por correo electrónico.

Las notificaciones enviadas contienen:

* Un **[!UICONTROL Summary]** cuadro que muestra el número de entregas que cumplen los criterios definidos y la etiqueta o el color elegidos para cada criterio.
* Una **[!UICONTROL Details]** sección que enumera todos los criterios de entrega definidos para el tablero correspondiente y todos los envíos para cada criterio.

![](assets/delivery-alerting_notification.png)

## Tableros de alerta de envío {#delivery-alerting-dashboards}

### Acerca de los tableros de alertas de envío {#about-delivery-alerting-dashboards}

Para administrar los destinatarios de las notificaciones, definir los criterios de alerta y acceder al historial de las alertas, debe utilizar los tableros.

>[!NOTE]
>
>Para acceder y configurar los tableros y los criterios de alerta, debe tener derechos de administración o aparecer en el grupo de seguridad Supervisores **de** envío. Los usuarios estándar no pueden acceder a los tableros en la interfaz de Adobe Campaign. Solo pueden recibir las notificaciones de alerta. Para obtener más información sobre usuarios y seguridad en Adobe Campaign, consulte [Tipos de usuarios](../../administration/using/users-management.md) y [Acerca de los grupos](../../administration/using/managing-groups-and-users.md#about-security-groups)de seguridad.

Desde la interfaz de Adobe Campaign puede:

* Cree y administre tableros de alerta de envío. Consulte [Creación de un tablero](#creating-a-delivery-alerting-dashboard)de alertas de envío.
* Defina y administre los criterios de alerta de entrega para cada tablero. Por ejemplo, puede generar alertas en función de entregas con una preparación fallida o entregas con un rendimiento reducido únicamente. Consulte [Acerca de los criterios](#about-alerting-criteria)de alerta.
* Modifique los parámetros de criterios para cada tablero. Consulte Parámetros [de criterios](#criteria-parameters).
* Defina un grupo de destinatarios para cada tablero.

   Por ejemplo, desea informar a los usuarios con derechos de administración únicamente de los envíos fallidos. Sin embargo, desea que los usuarios de mercadotecnia reciban información sobre los envíos con un índice de errores de devolución suave. Por lo tanto, debe crear dos tableros diferentes y definir los criterios que desee para cada grupo de destinatarios.

* Acceda al historial de todas las alertas enviadas para cada tablero.

   Al seleccionar un tablero, se muestra la última alerta enviada para este tablero de forma predeterminada. Todas las alertas enviadas se muestran a la izquierda de la pantalla. Haga clic en un elemento de la **[!UICONTROL History]** lista para acceder a las alertas correspondientes.

![](assets/delivery-alerting_dashboard.png)

### Creación de un tablero de alertas de entrega {#creating-a-delivery-alerting-dashboard}

Si desea enviar notificaciones basadas en criterios específicos a diferentes grupos de usuarios, debe utilizar varios tableros. Para crear un nuevo tablero:

1. Vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Seleccione **[!UICONTROL Delivery alerting dashboards]** y haga clic en **[!UICONTROL Create]**.
1. Marque la **[!UICONTROL Enabled]** casilla para activar el tablero actual.

   Si esta opción está desactivada, ya no se envían las notificaciones vinculadas a este tablero. Esta opción está desactivada de forma predeterminada.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Seleccione el grupo de destinatarios al que desea notificar en la lista **[!UICONTROL Alert group]** desplegable. Para modificar o crear un grupo, consulte [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. En la **[!UICONTROL Delivery alerting criteria]** sección, haga clic en **[!UICONTROL Create element]** para agregar criterios. Consulte [Acerca de los criterios](#about-alerting-criteria)de alerta.
1. Seleccione el **[!UICONTROL Edit properties]** botón. En la **[!UICONTROL Criteria parameters]** ficha, defina cómo se aplicarán los criterios. Consulte Parámetros [de criterios](#criteria-parameters).
1. Haga clic en **[!UICONTROL Create]** para guardar el tablero.

Ahora, cada vez que una entrega cumple los criterios definidos en este tablero, se enviará una notificación de alerta al grupo de usuarios especificado.

## Criterios de alerta de envío {#delivery-alerting-criteria}

### Acerca de los criterios de alerta {#about-alerting-criteria}

Para acceder a los criterios de alerta de envío, vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** y seleccione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Los siguientes criterios se pueden usar en los tableros de alerta de envío:

* **[!UICONTROL Deliveries failed]**:: Cualquier entrega programada dentro de un rango definido, con un estado erróneo.
* **[!UICONTROL Deliveries with preparation failed]**:: Cualquier entrega modificada dentro de un rango definido, para la cual ha fallado el paso de preparación (cálculo de objetivo y generación de contenido). Para obtener más información sobre esto, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:: Cualquier entrega programada dentro de un rango definido, con un estado al menos **[!UICONTROL In progress]**, con un índice de error de devolución suave superior a un porcentaje definido.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:: Cualquier entrega programada dentro de un rango definido, con un estado al menos **[!UICONTROL In progress]**, con un índice de error de devolución en bruto superior a un porcentaje definido.
* **[!UICONTROL Deliveries with long start pending]**:: Cualquier entrega programada dentro de un rango definido, con un estado **[!UICONTROL Start pending]** mayor que una duración definida, **[!UICONTROL Start pending]** lo que significa que el sistema aún no ha tenido en cuenta los mensajes.
* **[!UICONTROL Deliveries with low throughput]**:: Cualquier entrega iniciada durante más tiempo que una duración definida, con menos de un porcentaje definido de mensajes procesados, con un rendimiento inferior al valor definido.
* **[!UICONTROL Deliveries in progress]**:: Cualquier entrega programada dentro de un intervalo definido, con el **[!UICONTROL In progress]** estado.

>[!NOTE]
>
>Todos los parámetros que se aplican a los criterios anteriores tienen valores predeterminados. Estos valores se pueden cambiar en la **[!UICONTROL Criteria parameters]** ficha de los tableros de alerta de envío. Consulte Parámetros [de criterios](#criteria-parameters).

Puede seleccionar cualquier elemento de la **[!UICONTROL Delivery alerting criteria]** lista para acceder a sus detalles.

![](assets/delivery-alerting_criteria_definition.png)

Para cada criterio, puede definir la siguiente configuración:

* **[!UICONTROL Indicators to add in alerts]**, es decir, las columnas que aparecerán en la sección de la notificación para las entregas que correspondan al criterio seleccionado. **[!UICONTROL Details]**

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, es decir, la etiqueta y el color que aparecerán junto al criterio de entrega en el resumen de la notificación.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:: Si se cumple un criterio para una entrega, se repite en cada notificación enviada dentro del período de supervisión. De lo contrario, solo se enviará una alerta por día (en la primera incidencia) según el criterio de alerta para una entrega.

   De forma predeterminada, esta opción se establece en una vez al día para todos los criterios.

**Temas relacionados:**

* [Envío de registros](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frecuencia de alerta](#alerting-frequency)
* [Iconos y estados de actividades de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creación de un criterio de alerta de entrega {#creating-a-delivery-alerting-criterion}

Puede crear nuevos criterios de alerta de entrega para adaptarlos mejor a sus necesidades.

Por ejemplo, puede crear un nuevo criterio que permita enviar una notificación con todos los envíos con un **[!UICONTROL Finished]** estado.

Para ello, primero debe ampliar el recurso de **envío** y agregar un nuevo filtro que le permita seleccionar únicamente los envíos con un **[!UICONTROL Finished]** estado.

1. Vaya a **Adobe Campaign** &gt; **Administración** &gt; **Desarrollo** &gt; Recursos **** personalizados y haga clic en **[!UICONTROL Create]**.
1. Seleccione **[!UICONTROL Extend an existing resource]**, seleccione el **[!UICONTROL Delivery]** recurso en la lista desplegable y haga clic en **[!UICONTROL Create]** para editarlo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obtener más información sobre cómo ampliar un recurso existente, consulte [Definir el recurso](../../developing/using/creating-or-extending-the-resource.md).

1. En el **[!UICONTROL Delivery]** recurso, vaya a la **[!UICONTROL Filter definition]** ficha y haga clic en **[!UICONTROL Add an element]** para crear un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Editar la nueva definición del filtro: en la **[!UICONTROL Filter definition]** ventana, arrastre y suelte el **[!UICONTROL Status]** elemento en el espacio de trabajo y selecciónelo **[!UICONTROL Finished]** como condición del filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obtener más información sobre la creación y edición de filtros personalizados, consulte [Definición de filtros](../../developing/using/configuring-filter-definition.md).

1. Guarde los cambios y publique los recursos. Para obtener más información sobre esto, consulte [Publicación de un recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

   El filtro se crea y ahora se puede seleccionar en un nuevo criterio de alerta de entrega.

1. Vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, seleccione **[!UICONTROL Delivery alerting criteria]** y haga clic en **[!UICONTROL Create]**.
1. En la lista **[!UICONTROL Delivery filter applied by this criterion]** desplegable, seleccione el filtro que acaba de crear.

   ![](assets/delivery-alerting_cus-filter.png)

   Puede definir la configuración del criterio del mismo modo que para los criterios predeterminados. Consulte [Acerca de los criterios](#about-alerting-criteria)de alerta.

Una vez creados, estos criterios se pueden agregar a un tablero de alertas de entrega, así como a otros criterios. Consulte [Acerca de los tableros](#about-delivery-alerting-dashboards)de alertas de envío.

![](assets/delivery-alerting_new-criterion.png)

**Tema relacionado:**

[Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parámetros de alerta de envío {#delivery-alerting-parameters}

### Parámetros de criterios {#criteria-parameters}

En la **[!UICONTROL Criteria parameters]** ficha de un tablero [de alertas de](#creating-a-delivery-alerting-dashboard)entrega, puede definir la configuración que se aplica a los criterios seleccionados en este tablero.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:: Por ejemplo, si introduce 100 en este campo, se enviará una notificación solo para las entregas con un objetivo igual o superior a 100 destinatarios. Este parámetro se aplica a todos los criterios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:: Número de horas antes y después de la hora actual. Sólo se tienen en cuenta las entregas con una fecha de contacto en este intervalo de tiempo. Este parámetro se aplica a todos los criterios. De forma predeterminada, el valor de este campo se establece en 24 horas.

   Para obtener más información sobre la fecha de contacto, consulte [Acerca de la programación](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**:: Se envía una notificación para todas las entregas con un índice de error de devolución en blanco superior al valor especificado. De forma predeterminada, el valor de este campo está establecido en 0,05 (5%).

   Para obtener más información acerca de los errores de devolución suave, consulte [Rebotar cualificación](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) de correo y [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de error de entrega.

* **[!UICONTROL Maximum ratio of hard bounce errors]**:: Se envía una notificación para todas las entregas con un índice de error de devolución en bruto superior al valor especificado. De forma predeterminada, el valor de este campo está establecido en 0,05 (5%).

   Para obtener más información acerca de los errores de devolución en firme, consulte [Rebotar cualificación](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) de correo y [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de error de entrega.

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:: Se envía una notificación para todas las entregas con un estado **[!UICONTROL Start pending]** mayor que el especificado en este campo, lo que significa que el sistema no ha tenido en cuenta los mensajes aún **[!UICONTROL Start pending]** .
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:: Solo se tienen en cuenta para el criterio las entregas iniciadas (con **[!UICONTROL In progress]** estado) durante más tiempo del especificado **[!UICONTROL Deliveries with low throughput]** .
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:: Para el **[!UICONTROL Deliveries with low throughput]** criterio solo se tienen en cuenta las entregas con un porcentaje de mensajes procesados inferior al porcentaje especificado.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:: Para el **[!UICONTROL Deliveries with low throughput]** criterio solo se tienen en cuenta las entregas con un rendimiento inferior al valor especificado.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:: Solo se tienen en cuenta las entregas con un porcentaje de mensajes procesados superior al porcentaje especificado.

### Frecuencia de alerta {#alerting-frequency}

La **[!UICONTROL Frequency of delivery alerting]** opción permite definir el retraso entre dos envíos de alertas. De forma predeterminada, se establece en 10 minutos.

Puede cambiar esta configuración a través del menú **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** .

>[!NOTE]
>
>Esta opción se aplica a todos los tableros definidos en Adobe Campaign. No puede establecer una frecuencia específica para cada tablero.

## Motivos de las alertas de envío {#delivery-alerting-reasons}

La función de alerta **de** envío mantiene informados automáticamente a todos los usuarios de Adobe Campaign sobre el estado de ejecución de la entrega, a través del correo electrónico y el tablero.

Ahora, cuando reciba una notificación de alerta de envío, aquí tiene algunos consejos sobre lo que puede hacer.

En primer lugar, marque la ficha **Registro** de la entrega para ver toda la información relacionada con la entrega y las pruebas. Los iconos rojo y amarillo permiten identificar errores o advertencias. El icono rojo indica un error crítico que impide que se inicie la entrega.

Para ver el historial de cada incidencia de un envío, seleccione la **[!UICONTROL Sending logs]** ficha. Contiene la lista de mensajes enviados y sus estados. Allí puede comprobar el estado de entrega de cada destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). Para obtener más información sobre esto, consulte [Envío de registros](../../sending/using/monitoring-a-delivery.md#sending-logs).

A continuación se indican algunos motivos posibles para recibir notificaciones de alerta según los criterios que se cumplan para una entrega.

* **[!UICONTROL Deliveries failed]**:: Este criterio le informa de todas las entregas con un estado erróneo. Puede deberse a:

   * Un problema con el servidor de entrega (MTA, Agente de transferencia de mensajes)
   * Tiempo de espera de conexión entre el servidor de entrega de Adobe Campaign y el servidor receptor
   * Un problema de entrega
   * Un flujo de trabajo erróneo
   Si la entrega se activa con un flujo de trabajo, compruebe si el flujo de trabajo se inició correctamente. Para obtener más información sobre esto, consulte [Ejecución de un flujo de trabajo](../../automating/using/executing-a-workflow.md). De lo contrario, póngase en contacto con el administrador de Adobe Campaign para resolver el problema.

* **[!UICONTROL Deliveries with preparation failed]**:: Se puede producir un error durante la preparación de la entrega en los siguientes casos:

   * Falta un asunto en la entrega.
   * Hay una sintaxis incorrecta en los campos de personalización.
   * Falta el objetivo.
   * El envío supera el límite de tamaño.
   Para obtener más información sobre esto, consulte [Preparación del envío](../../sending/using/preparing-the-send.md). Sin embargo, estos errores generalmente se detectan durante el análisis de mensajes. Consulte Reglas [de control](../../administration/using/control-rules.md).

* Las posibles causas de una **[!UICONTROL Delivery with bad error ratio for soft bounces]** alerta pueden ser:

   * El servidor del destinatario está inactivo.
   * El buzón del destinatario está lleno.
   Para obtener más información, consulte las fichas **[!UICONTROL Exclusion logs]** y **[!UICONTROL Exclusion causes]** los registros de entrega. Consulte Registros [de](../../sending/using/monitoring-a-delivery.md#exclusion-logs)exclusión.

   Las posibles causas de una **[!UICONTROL Delivery with bad error ratio for hard bounces]** alerta pueden ser:

   * El destinatario está bloqueado, lo que significa que ya no desea que se contacte con él.
   * La dirección de correo electrónico del destinatario no existe.
   * El dominio del destinatario no existe.
   * El servidor del destinatario está bloqueando la entrega.
   Para evitar errores de devolución en blanco y en bruto, siga las optimizaciones a continuación:

   * Genere reglas de tipología de filtrado para excluir una parte del destino del mensaje durante el análisis de entrega, como los destinatarios en cuarentena. See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * Actualice regularmente su base de datos de clientes para mantener buenos procesos de gestión de cuarentena. Consulte [Acerca de las cuarentena](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * En términos generales, mejore la capacidad de entrega lo mejor posible. Consulte la guía detallada de la [administración de entregas](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) de Adobe Campaign v7 y póngase en contacto con el administrador de Adobe Campaign para obtener ayuda.



* **[!UICONTROL Deliveries with long start pending]**:: Generalmente esto significa que hay un problema en el nivel de MTA (Agente de transferencia de mensajes). El proceso de ejecución está esperando la disponibilidad de algunos recursos. Es posible que el MTA no se haya iniciado.

   **[!UICONTROL Deliveries with low throughput]**:: Nuevamente, este es un problema de entrega, lo que significa que el MTA es demasiado lento.

   Para obtener más información sobre estos problemas, póngase en contacto con el administrador de Adobe Campaign.

**Temas relacionados:**

* [Comprensión de los errores de envío](../../sending/using/understanding-delivery-failures.md)
* [Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Administración de la lista negra en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)


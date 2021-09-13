---
title: Comprensión de la gestión de la cuarentena
description: Aprenda a optimizar la capacidad de entrega con la gestión de la cuarentena.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 51%

---

# Comprensión de la gestión de la cuarentena{#understanding-quarantine-management}

## Acerca de la cuarentena {#about-quarantines}

Se puede poner en cuarentena una dirección de correo electrónico o un número de teléfono, por ejemplo, cuando el buzón está lleno o si la dirección no existe.

En cualquier caso, el procedimiento de cuarentena satisface las reglas específicas que se describen en esta [sección](#conditions-for-sending-an-address-to-quarantine).

### Optimización de la entrega mediante cuarentenas {#optimizing-your-delivery-through-quarantines}

Los perfiles cuyas direcciones de correo electrónico o número de teléfono están en cuarentena se excluyen automáticamente durante la preparación del mensaje (consulte [Identificación de direcciones en cuarentena para una entrega](#identifying-quarantined-addresses-for-a-delivery)). Esto acelera las entregas, ya que la tasa de error afecta significativamente a la velocidad de entrega.

Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como no deseados si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser incluido en la lista de bloqueados de bloqueados por estos proveedores.

Además, la cuarentena reduce el coste de entrega de los SMS mediante la exclusión en las entregas de los números de teléfono incorrectos.

Para obtener más información sobre las prácticas recomendadas para proteger y optimizar las entregas, consulte [esta página](../../sending/using/delivery-best-practices.md).

### Cuarentena frente a Lista de bloqueados {#quarantine-vs-denylist}

La cuarentena y la lista de bloqueados no se aplican al mismo objeto:

* **** La cuarentena solo se aplica a una  **dirección**  (o número de teléfono, etc.), no al propio perfil. Por ejemplo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva dirección, y luego puede volver a recibir acciones de envío. Del mismo modo, si dos perfiles tienen el mismo número de teléfono, ambos se verán afectados si el número está en cuarentena.

   Las direcciones en cuarentena o los números de teléfono se muestran en los [registros de exclusión](#identifying-quarantined-addresses-for-a-delivery) (para un envío) o en la [lista de cuarentena](#identifying-quarantined-addresses-for-the-entire-platform) (para toda la plataforma).

* Al estar en la **lista de bloqueados**, por otro lado, el **perfil** ya no se tendrá en cuenta para el envío, como después de una baja (exclusión) de un canal determinado. Por ejemplo, si un perfil de la  de lista de bloqueados del canal de correo electrónico tiene dos direcciones de correo electrónico, ambas se excluirán del envío. Para obtener más información sobre el proceso de  de lista de bloqueados, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

   Puede comprobar si un perfil está en la  de lista de bloqueados para uno o más canales en la sección **[!UICONTROL No longer contact (on denylist)]** de la pestaña **[!UICONTROL General]** del perfil. Consulte [esta sección](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>La cuarentena incluye un estado **On lista de bloqueados**, que se aplica cuando los destinatarios informan del mensaje como correo no deseado o responden a un mensaje SMS con una palabra clave como &quot;STOP&quot;. En ese caso, la dirección o el número de teléfono implicados del perfil se envían a cuarentena con el estado **[!UICONTROL On denylist]**. Para obtener más información sobre la administración de mensajes STOP SMS, consulte [esta sección](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

<!--When a user replies to an SMS message with a keyword such as STOP in order to opt-out from SMS deliveries, his profile is not added to the denylist like in the email opt-out process. Instead, the profile's phone number is sent to quarantine with the **[!UICONTROL On denylist]** status. This status refers to the phone number only, meaning that the profile will continue receiving email messages.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## Identificación de direcciones en cuarentena {#identifying-quarantined-addresses}

Las direcciones en cuarentena se pueden mostrar para un envío específico o para toda la plataforma.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### Identificación de direcciones en cuarentena para una entrega {#identifying-quarantined-addresses-for-a-delivery}

Las direcciones en cuarentena para una entrega específica se enumeran durante la fase de preparación de la entrega, en la pestaña **[!UICONTROL Exclusion logs]** del panel de entrega (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Para obtener más información sobre preparación de entregas, consulte [esta sección](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificación de direcciones en cuarentena para toda la plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Los administradores pueden acceder a la lista detallada de las direcciones de correo electrónico en cuarentena para toda la plataforma desde el menú **[!UICONTROL Administration > Channels > Quarantines > Addresses]** .

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>El aumento del número de cuarentenas es un efecto normal, relacionado con el &quot;desgaste&quot; de la base de datos. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la lista de distribución aumenta en un 50 % cada año, el aumento de la cuarentena se puede calcular de la siguiente manera: Fin de año 1: (1*0,33)/(1+0,5) = 22 %. Fin de año 2: ((1,22*0,33)+0,33)/(1,5+0,75) = 32,5 %.

Los filtros están disponibles para ayudarle a navegar por la lista. Puede filtrar por la dirección, el estado o el canal.

![](assets/quarantines-filters.png)

Puede editar o [eliminar](#removing-a-quarantined-address) cada entrada, así como crear otras nuevas.

Para editar una entrada, haga clic en la fila correspondiente y modifique los campos según sea necesario.

![](assets/quarantines-edit.png)

Para añadir manualmente una nueva entrada, utilice el botón **[!UICONTROL Create]**.

![](assets/quarantines-create-button.png)

Defina la dirección (o el número de teléfono, etc.) y tipo de canal. Puede establecer un estado para que esté en la lista de cuarentena y un motivo de error. También puede indicar la fecha en la que se produjo el error, el número de errores e introducir el texto del error. Si es necesario, seleccione la última entrega que se envió a la dirección en la lista desplegable.

![](assets/quarantines-create-last-delivery.png)

### Eliminación de una dirección en cuarentena {#removing-a-quarantined-address}

Si es necesario, puede eliminar manualmente una dirección de la lista de cuarentena. Además, el flujo de trabajo **[!UICONTROL Database cleanup]** elimina automáticamente de la lista de cuarentena las direcciones que coinciden con condiciones específicas. (Para obtener más información sobre los flujos de trabajo técnicos, consulte [esta sección](../../administration/using/technical-workflows.md#list-of-technical-workflows)).

Para eliminar manualmente una dirección de la lista de cuarentena, realice una de las acciones siguientes.

>[!IMPORTANT]
Eliminar manualmente una dirección de correo electrónico de la cuarentena significa que volverá a enviar a esta dirección. Por lo tanto, esto puede tener un impacto grave en la capacidad de envío y la reputación de la IP, lo que eventualmente podría provocar que se bloqueara su dirección IP o dominio de envío. Proceda con cuidado adicional cuando considere la posibilidad de eliminar cualquier dirección de la cuarentena. En caso de duda, póngase en contacto con un experto en entregas.

* Seleccione la dirección de la lista **[!UICONTROL Administration > Channels > Quarantines > Addresses]** y seleccione **[!UICONTROL Delete element]**.

   ![](assets/quarantine-delete-address.png)

* Seleccione una dirección y cambie su **[!UICONTROL Status]** a **[!UICONTROL Valid]**.

   ![](assets/quarantine-valid-status.png)

   También puede cambiar su estado a **[!UICONTROL On allowlist]**. En este caso, la dirección permanece en la lista de la cuarentena, pero se dirigirá sistemáticamente, incluso si se produce un error.

Las direcciones se eliminan automáticamente de la lista de cuarentena en los siguientes casos:

* Las direcciones de un estado **[!UICONTROL Erroneous]** se eliminarán de la lista de cuarentena tras un envío correcto.
* Las direcciones de un estado **[!UICONTROL Erroneous]** se eliminarán de la lista de cuarentena si el último rebote suave se produjo hace más de 10 días. Para obtener más información sobre la administración de errores leves, consulte [esta sección](#soft-error-management).
* Las direcciones con un estado **[!UICONTROL Erroneous]** que rebotó con el error **[!UICONTROL Mailbox full]** se eliminarán de la lista de cuarentena pasados 30 días.

A continuación, su estado cambia a **[!UICONTROL Valid]**.

>[!IMPORTANT]
Los destinatarios con una dirección en estado **[!UICONTROL Quarantine]** o **[!UICONTROL On denylist]** nunca se eliminarán automáticamente, aunque reciban un correo electrónico.

El número máximo de reintentos que se deben realizar en caso del estado **[!UICONTROL Erroneous]** y el retraso mínimo entre reintentos ahora se basan en el rendimiento histórico y actual de una IP en un dominio determinado.

## Condiciones para enviar una dirección a cuarentena {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign administra la cuarentena según el tipo de error de entrega y el motivo asignado durante la calificación de mensajes de error (consulte [Tipos y motivos de error de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) y [Clasificación del correo rechazado](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Error ignorado**: los errores ignorados no envían una dirección a la cuarentena.
* **Error grave:** la dirección de correo electrónico correspondiente se envía inmediatamente a la cuarentena.
* **Error leve**: los errores leves no envían inmediatamente una dirección a la cuarentena, sino que se suman a un contador de errores. Para obtener más información, consulte [Gestión de errores en software](#soft-error-management).

   <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Si un usuario clasifica un correo electrónico como correo no deseado ([bucle de comentarios](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops)), el mensaje se redirige automáticamente a un buzón de correo técnico administrado por Adobe. A continuación, la dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el estado **[!UICONTROL On denylist]**. Este estado hace referencia únicamente a la dirección y el perfil no está en la  de lista de bloqueados, de modo que el usuario siga recibiendo mensajes SMS y notificaciones push.

>[!NOTE]
La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

En la lista de direcciones en cuarentena (consulte [Identificación de direcciones en cuarentena para toda la plataforma](#identifying-quarantined-addresses-for-the-entire-platform)), el campo **[!UICONTROL Error reason]** indica por qué la dirección seleccionada se colocó en cuarentena.

![](assets/quarantines2.png)

### Administración de errores en software {#soft-error-management}

A diferencia de los errores en hardware, los errores en software no envían inmediatamente una dirección a la cuarentena, sino que se suman a un contador de errores.

Los reintentos se realizarán durante la [duración del envío](../../administration/using/configuring-email-channel.md#validity-period-parameters). Cuando el contador de errores alcanza el umbral de límite, la dirección se pone en cuarentena. Para obtener más información, consulte [Reintentos después de un error temporal de entrega](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

El contador de errores se reinicia si el último error significativo se produjo hace más de 10 días. El estado de la dirección cambia a **válido** y se elimina de la lista de cuarentena mediante el flujo de trabajo de **Limpieza de la base de datos.** (Para obtener más información sobre los flujos de trabajo técnicos, consulte [esta sección](../../administration/using/technical-workflows.md#list-of-technical-workflows)).

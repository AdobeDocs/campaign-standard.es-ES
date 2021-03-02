---
solution: Campaign Standard
product: campaign
title: Confirmación del envío
description: Aprenda a finalizar la preparación del mensaje.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: d08821c526d54dabc3b74651449a2f01e99c2a6a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Confirmación del envío{#confirming-the-send}

Una vez que haya terminado de preparar sus mensajes y se hayan realizado los pasos de aprobación, puede enviarlos. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

Solo los usuarios con la función **[!UICONTROL Start deliveries]** pueden confirmar el envío. Para obtener más información al respecto, consulte la sección [Lista de funciones](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Envío de mensajes {#sending-message}

Una vez finalizada la preparación, siga los pasos a continuación para enviar el mensaje.

1. Haga clic en el botón **[!UICONTROL Confirm send]** que se encuentra en la barra de acciones del mensaje.

   ![](assets/confirm_delivery.png)

1. Finalice el envío haciendo clic en el botón **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Espere mientras se envía el mensaje. El bloque **[!UICONTROL Deployment]** muestra el progreso del envío.

>[!NOTE]
>
>Si el mensaje está programado, se envía cuando se llega a la hora de envío. Para obtener más información sobre la programación de mensajes, consulte [esta sección](../../sending/using/about-scheduling-messages.md).

Si utiliza un envío recurrente sin período de acumulación, puede solicitar confirmación antes de proceder con el envío. Al configurar el mensaje, abra el bloque **[!UICONTROL Schedule]** del panel de envío y active la opción dedicada.

![](assets/confirmation_recurring_deliveries.png)

## Entender los indicadores de mensaje {#message-indicators}

Una vez que el mensaje se envía a los contactos, la zona **[!UICONTROL Deployment]** muestra los datos de KPI (indicador de rendimiento clave), que incluye la siguiente información:

* El número de mensajes que enviar
* El número de mensajes enviados
* El porcentaje de mensajes entregados
* El porcentaje de devoluciones y errores
* El porcentaje de mensajes abiertos
* El porcentaje de clics en los mensajes (en el caso de correos electrónicos)

   >[!NOTE]
   >
   >La **[!UICONTROL Open rate]** y **[!UICONTROL Click-through rate]** se actualiza cada hora.

![](assets/sending_delivery.png)

Si los KPI tardan demasiado en actualizarse o no reflejan los resultados de los registros de envío, haga clic en el botón **[!UICONTROL Compute stats]** en la ventana **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles objetivo. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Una vez enviado un mensaje, puede realizar un seguimiento del comportamiento de sus destinatarios y monitorearlo para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)

### Informes de éxito de envío {#delivered-status-report}

>[!NOTE]
>
>Esta sección se aplica solo al canal de correo electrónico.

En la vista **[!UICONTROL Summary]** de cada correo electrónico, el porcentaje **[!UICONTROL Delivered]** comienza en el 100% y luego se reduce progresivamente a lo largo del [periodo de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters) del envío, a medida que se informan los rechazos leves y graves<!--from the Enhanced MTA to Campaign-->.

De hecho, todos los mensajes aparecen como **[!UICONTROL Sent]** en los [registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs) en cuanto se retransmiten correctamente desde Campaign al MTA mejorado (Agente de transferencia de mensajes). Permanecen en ese estado a menos o hasta que un [rechazo](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) para ese mensaje se comunique de nuevo desde el MTA mejorado a Campaign.

Cuando los mensajes rechazados en el disco duro se devuelven desde el MTA mejorado, su estado cambia de **[!UICONTROL Sent]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Delivered]** disminuye en consecuencia.

Cuando los mensajes de rebote en blanco se devuelven desde el MTA mejorado, siguen mostrándose como **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** aún no se ha actualizado. A continuación, los mensajes rechazados en software se [reintentan](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante todo el periodo de validez del envío:

* Si un reintento se realiza correctamente antes del final del periodo de validez, el estado del mensaje permanece como **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** permanece sin cambios.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Delivered]** disminuye según corresponda.

Por lo tanto, debe esperar hasta el final del periodo de validez para ver el porcentaje final **[!UICONTROL Delivered]** y el número final de mensajes **[!UICONTROL Sent]** y **[!UICONTROL Failed]**.

### Servicio de comentarios de correo electrónico (beta) {#email-feedback-service}

Con la capacidad Servicio de comentarios de correo electrónico (EFS) , el estado de cada correo electrónico se informa con precisión, ya que los comentarios se capturan directamente desde el MTA mejorado (Agente de transferencia de mensajes).

>[!IMPORTANT]
>
>El servicio de comentarios de correo electrónico está disponible actualmente como una capacidad beta.

Una vez iniciado el envío, no hay ningún cambio en el porcentaje **[!UICONTROL Delivered]** cuando el mensaje se reenvía correctamente de Campaign al MTA mejorado.

![](assets/efs-sending.png)

Los registros de envío muestran el estado **[!UICONTROL Pending]** de cada dirección de destino.

![](assets/efs-pending.png)

Cuando el envío de mensajes a los perfiles de destino se realiza en tiempo real desde el MTA mejorado, los registros de envío muestran el estado **[!UICONTROL Sent]** de cada dirección que recibió el mensaje correctamente. El porcentaje **[!UICONTROL Delivered]** aumenta en consecuencia con cada envío exitoso.

Cuando los mensajes rechazados en el disco duro se devuelven desde el MTA mejorado, su estado de registro cambia de **[!UICONTROL Pending]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Bounces + errors]** se incrementa en consecuencia.

Cuando los mensajes de devolución en blanco se devuelven desde el MTA mejorado, su estado de registro también cambia de **[!UICONTROL Pending]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Bounces + errors]** se incrementa en consecuencia. El porcentaje **[!UICONTROL Delivered]** permanece sin cambios. A continuación, se vuelven a intentar los mensajes de rechazo en software durante el [periodo de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters) del envío:

* Si un reintento se realiza correctamente antes del final del periodo de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** aumenta en consecuencia.

* De lo contrario, el estado se mantiene como **[!UICONTROL Failed]**. Los porcentajes **[!UICONTROL Delivered]** y **[!UICONTROL Bounces + errors]** no cambian.

>[!NOTE]
>
>Para obtener más información sobre los rechazos graves y leves, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Para obtener más información sobre los reintentos después de un error temporal de envío, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Cambios introducidos por EFS {#changes-introduced-by-efs}

Las tablas siguientes muestran los cambios en los KPI y en los estados de registros de envío introducidos por la capacidad de EFS.

**Con el servicio de comentarios por correo electrónico**

| Paso en el proceso de envío | Resumen de KPI | Envío del estado de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente de Campaign al MTA mejorado | <ul><li>**[!UICONTROL Delivered]** el porcentaje empieza en 0%</li><li>**[!UICONTROL Bounces + errors]** el porcentaje empieza en 0%</li></ul> | Pendiente |
| Los mensajes de rechazo grave se devuelven desde el MTA mejorado | <ul><li>Sin cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** el porcentaje aumenta en consecuencia</li></ul> | Error |
| Los mensajes de devolución en software se devuelven desde el MTA mejorado | <ul><li>Sin cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** el porcentaje aumenta en consecuencia</li></ul> | Error |
| Los reintentos de mensajes rechazados en software son correctos | <ul><li>**[!UICONTROL Delivered]** el porcentaje aumenta en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje disminuye en consecuencia</li></ul> | Enviado |
| Fallo en los reintentos de mensajes de devolución en blanco | <ul><li> Sin cambios en el porcentaje **[!UICONTROL Delivered]** </li><li> Sin cambios en el porcentaje **[!UICONTROL Bounces + errors]** </li></ul> | Error |

**Sin servicio de comentarios de correo electrónico**

| Paso en el proceso de envío | Resumen de KPI | Envío del estado de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente de Campaign al MTA mejorado | <ul><li>**[!UICONTROL Delivered]** el porcentaje empieza al 100%</li><li>**[!UICONTROL Bounces + errors]** el porcentaje empieza en 0%</li></ul> | Enviado |
| Los mensajes de rechazo grave se devuelven desde el MTA mejorado | <ul><li>**[!UICONTROL Delivered]** el porcentaje disminuye en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje aumenta en consecuencia</li></ul> | Error |
| Los mensajes de devolución en software se devuelven desde el MTA mejorado | <ul><li>Sin cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>Sin cambios en el porcentaje **[!UICONTROL Bounces + errors]**</li></ul> | Enviado |
| Los reintentos de mensajes rechazados en software son correctos | <ul><li>Sin cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>Sin cambios en el porcentaje **[!UICONTROL Bounces + errors]**</li></ul> | Enviado |
| Fallo en los reintentos de mensajes de devolución en blanco | <ul><li>**[!UICONTROL Delivered]** el porcentaje disminuye en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje aumenta en consecuencia</li></ul> | Error |

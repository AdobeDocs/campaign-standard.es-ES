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
source-git-commit: 8c636ec7a35e9c34210bbb04b1b13aaa6a431345
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 22%

---


# Confirmación del envío{#confirming-the-send}

Una vez que haya terminado de preparar sus mensajes y se hayan realizado los pasos de aprobación, puede enviarlos. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

Solo los usuarios con la función **[!UICONTROL Start deliveries]** pueden confirmar el envío. Para obtener más información al respecto, consulte la sección [Lista de funciones](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Envío de mensajes {#sending-message}

Una vez finalizada la preparación, siga los pasos a continuación para enviar su mensaje.

1. Haga clic en el botón **[!UICONTROL Confirm send]** que se encuentra en la barra de acciones del mensaje.

   ![](assets/confirm_delivery.png)

1. Para finalizar el envío, haga clic en el botón **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Espere mientras se envía el mensaje. El bloque **[!UICONTROL Deployment]** muestra el progreso del envío.

>[!NOTE]
>
>Si el mensaje está programado, se enviará cuando se llegue a la hora de envío. Para obtener más información sobre la programación de mensajes, consulte [esta sección](../../sending/using/about-scheduling-messages.md).

Si utiliza un envío recurrente sin período de acumulación, puede solicitar confirmación antes de proceder con el envío. Para ello, al configurar el mensaje, abra el bloque **[!UICONTROL Schedule]** del panel de envío y active la opción dedicada.

![](assets/confirmation_recurring_deliveries.png)

## Explicación de los indicadores de mensaje {#message-indicators}

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

Si los KPI tardan demasiado en actualizarse o no tienen en cuenta los resultados de los registros de envío, haga clic en el botón **[!UICONTROL Compute stats]** en la ventana **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles objetivo. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Una vez que se envía un mensaje, puede realizar un seguimiento del comportamiento de sus destinatarios y monitorearlo para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)

### Sistema de informes de éxito de envío {#delivered-status-report}

>[!NOTE]
>
>Esta sección se aplica solo al canal por correo electrónico.

En la vista **[!UICONTROL Summary]** de cada correo electrónico, el **[!UICONTROL Delivered]** inicio al 100% y luego disminuye progresivamente a lo largo del período de validez del envío [](../../administration/using/configuring-email-channel.md#validity-period-parameters), a medida que se informan las devoluciones en bruto y en bruto<!--from the Enhanced MTA to Campaign-->.

De hecho, todos los mensajes se muestran como **[!UICONTROL Sent]** en los [registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs) tan pronto como se transmiten correctamente desde la Campaña al MTA mejorado (Agente de transferencia de mensajes). Permanecen en ese estado a menos o hasta que un [rebote](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) para ese mensaje se comunique de vuelta del MTA mejorado a la Campaña.

Cuando se generan informes de los mensajes de rebote desde el MTA mejorado, su estado cambia de **[!UICONTROL Sent]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Delivered]** disminuye en consecuencia.

Cuando los mensajes de devolución en pantalla vuelven a informarse desde el MTA mejorado, siguen mostrándose como **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** aún no se ha actualizado. A continuación, los mensajes de rebote en pantalla se [reintentan](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante todo el período de validez del envío:

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje permanece como **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** permanece sin cambios.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Delivered]** disminuye en consecuencia.

Por lo tanto, debe esperar hasta el final del período de validez para ver el porcentaje final **[!UICONTROL Delivered]** y el número final de mensajes **[!UICONTROL Sent]** y **[!UICONTROL Failed]**.

### Servicio de comentarios de correo electrónico (beta) {#email-feedback-service}

Con la capacidad del servicio de comentarios de correo electrónico (EFS), el estado de cada correo electrónico se informa con precisión, ya que los comentarios se capturan directamente desde el MTA mejorado (Agente de transferencia de mensajes).

>[!IMPORTANT]
>
>El servicio de comentarios de correo electrónico está disponible actualmente como una capacidad beta.

Una vez que se ha iniciado el envío, no se produce ningún cambio en el porcentaje **[!UICONTROL Delivered]** cuando el mensaje se transmite correctamente de la Campaña al MTA mejorado.

![](assets/efs-sending.png)

Los registros de envío muestran el estado **[!UICONTROL Pending]** de cada dirección de destino.

![](assets/efs-pending.png)

Cuando el mensaje se envía realmente a los perfiles objetivo y una vez que esta información se reporta en tiempo real desde el MTA mejorado, los registros de envío muestran el estado **[!UICONTROL Sent]** de cada dirección que recibió el mensaje correctamente. El porcentaje **[!UICONTROL Delivered]** se incrementa en consecuencia con cada envío exitoso.

Cuando se generan informes de los mensajes de rebote desde el MTA mejorado, su estado de registro cambia de **[!UICONTROL Pending]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Bounces + errors]** aumenta en consecuencia.

Cuando los mensajes de devolución en pantalla vuelven a informarse desde el MTA mejorado, su estado de registro también cambia de **[!UICONTROL Pending]** a **[!UICONTROL Failed]** y el porcentaje **[!UICONTROL Bounces + errors]** aumenta en consecuencia. El porcentaje **[!UICONTROL Delivered]** permanece sin cambios. A continuación, se vuelven a intentar los mensajes de devolución en pantalla a lo largo del envío [período de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje **[!UICONTROL Delivered]** se incrementa en consecuencia.

* De lo contrario, el estado permanece como **[!UICONTROL Failed]**. Los porcentajes **[!UICONTROL Delivered]** y **[!UICONTROL Bounces + errors]** permanecen sin cambios.

>[!NOTE]
>
>Para obtener más información acerca de las devoluciones en bruto y en blanco, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Para obtener más información sobre reintentos después de un error temporal de envío, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Cambios introducidos por EFS {#changes-introduced-by-efs}

La siguiente tabla muestra los cambios en los KPI y los estados de envío de registros introducidos por la capacidad de EFS.

| Paso en el proceso de envío<br> | Resumen de KPI<br>SIN EFS | Envío del estado de registros<br>SIN EFS | Resumen de KPI<br>CON EFS | Envío del estado de registros<br>CON EFS |
|--- |--- |--- | --- | --- |
| El mensaje se retransmite correctamente desde la Campaña al MTA mejorado | <ul><li>**[!UICONTROL Delivered]** inicios porcentuales en 100%</li><li>**[!UICONTROL Bounces + errors]** inicios porcentuales en 0 %</li></ul> | Enviado | <ul><li>**[!UICONTROL Delivered]** inicios porcentuales en 0 %</li><li>**[!UICONTROL Bounces + errors]** inicios porcentuales en 0 %</li></ul> | Pendiente |
| Los mensajes de devolución del hardware se informan desde el MTA mejorado | <ul><li>**[!UICONTROL Delivered]** el porcentaje disminuye en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje se incrementa en consecuencia</li></ul> | Error | <ul><li>No hay cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** el porcentaje se incrementa en consecuencia</li></ul> | Error |
| Los mensajes de devolución en pantalla se informan desde el MTA mejorado | <ul><li>No hay cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>No hay cambios en el porcentaje **[!UICONTROL Bounces + errors]**</li></ul> | Enviado | <ul><li>No hay cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** el porcentaje se incrementa en consecuencia</li></ul> | Error |
| Los reintentos de mensajes de devolución en pantalla se realizan correctamente | <ul><li>No hay cambios en el porcentaje **[!UICONTROL Delivered]**</li><li>No hay cambios en el porcentaje **[!UICONTROL Bounces + errors]**</li></ul> | Enviado | <ul><li>**[!UICONTROL Delivered]** el porcentaje se incrementa en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje disminuye en consecuencia</li></ul> | Enviado |
| Fallan los reintentos de mensajes de devolución en pantalla | <ul><li>**[!UICONTROL Delivered]** el porcentaje disminuye en consecuencia</li><li>**[!UICONTROL Bounces + errors]** el porcentaje se incrementa en consecuencia</li></ul> | Error | <ul><li> No hay cambios en el porcentaje **[!UICONTROL Delivered]** </li><li> No hay cambios en el porcentaje **[!UICONTROL Bounces + errors]** </li></ul> | Error |

---
title: Confirmación del envío
description: Aprenda a finalizar la preparación del mensaje.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 66%

---

# Confirmación del envío{#confirming-the-send}

Una vez que haya terminado de preparar sus mensajes y se hayan realizado los pasos de aprobación, puede enviarlos. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

Solo los usuarios con **[!UICONTROL Start deliveries]** función puede confirmar el envío. Para obtener más información al respecto, consulte la sección [Lista de funciones](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Envío de mensajes {#sending-message}

Una vez completada la preparación, siga los pasos a continuación para enviar su mensaje.

1. Haga clic en **[!UICONTROL Confirm send]** botón situado en la barra de acciones del mensaje.

   ![](assets/confirm_delivery.png)

1. Finalice el envío haciendo clic en **[!UICONTROL OK]** botón.

   ![](assets/confirm_delivery1.png)

1. Espere mientras se envía el mensaje. El bloque **[!UICONTROL Deployment]** muestra el progreso del envío.

>[!NOTE]
>
>Si el mensaje está programado, se envía cuando se llega a la hora de envío. Para obtener más información sobre la programación de mensajes, consulte [esta sección](../../sending/using/about-scheduling-messages.md).

Si utiliza un envío recurrente sin período de acumulación, puede solicitar confirmación antes de proceder con el envío. Al configurar el mensaje, abra el **[!UICONTROL Schedule]** del panel de envío y active la opción dedicada.

![](assets/confirmation_recurring_deliveries.png)

## Comprender los indicadores de mensajes {#message-indicators}

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

Si los KPI tardan demasiado en actualizarse o no reflejan los resultados de los registros de envío, haga clic en **[!UICONTROL Compute stats]** botón en el **[!UICONTROL Deployment]** ventana.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles objetivo. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Una vez enviado un mensaje, puede realizar un seguimiento del comportamiento de sus destinatarios y monitorizarlo para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Seguimiento de un envío](../../sending/using/monitoring-a-delivery.md)

### Sistema de informes de éxito de envío {#delivered-status-report}

>[!NOTE]
>
>Esta sección se aplica solo al canal de correo electrónico.

En el **[!UICONTROL Summary]** vista de cada correo electrónico, la variable **[!UICONTROL Delivered]** El porcentaje de comienza en el 100 % y luego desciende progresivamente a lo largo de la entrega [período de validez](../../administration/using/configuring-email-channel.md#validity-period-parameters), a medida que se informan los rebotes suaves y duros<!--from the Enhanced MTA to Campaign-->.

De hecho, todos los mensajes se muestran como **[!UICONTROL Sent]** en el [registros de envío](../../sending/using/monitoring-a-delivery.md#sending-logs) tan pronto como se transmitan correctamente desde Campaign al servidor de correo mejorado (MTA). Permanecen en ese estado a menos que un [rebote](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) de ese mensaje se comunique desde el servidor de correo mejorado a Campaign, o hasta que esto ocurra.

Cuando se generan informes de los mensajes de rebote duro desde el servidor de correo mejorado, su estado cambia de **[!UICONTROL Sent]** a **[!UICONTROL Failed]** y el porcentaje de **[!UICONTROL Delivered]** disminuye en consecuencia.

Cuando se generan informes de los mensajes de rebote suave desde el servidor de correo mejorado, siguen mostrándose como **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Delivered]** todavía no se actualiza. A continuación, la entrega de los mensajes de rebote suave se [reintenta](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante todo el período de validez del envío:

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje permanece como **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Delivered]** permanece sin cambios.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]** y el porcentaje de **[!UICONTROL Delivered]** disminuye en consecuencia.

Por lo tanto, debe esperar hasta el final del periodo de validez para ver el final **[!UICONTROL Delivered]** y el número final de **[!UICONTROL Sent]** y **[!UICONTROL Failed]** mensajes.

### Servicio de comentarios de correo electrónico (beta) {#email-feedback-service}

Con el servicio de comentarios de correo electrónico (SCCE), se informa del estado de cada correo electrónico con precisión, ya que los comentarios se capturan directamente desde el servidor de correo mejorado.

>[!IMPORTANT]
>
>El servicio de comentarios de correo electrónico está disponible actualmente como una funcionalidad beta.

Una vez que se ha iniciado el envío, no se produce ningún cambio en el porcentaje de **[!UICONTROL Delivered]** cuando el mensaje se transmite correctamente de Campaign al servidor de correo mejorado.

![](assets/efs-sending.png)

Los registros de envío muestran el estado **[!UICONTROL Pending]** de cada dirección de destino.

![](assets/efs-pending.png)

Cuando se informa en tiempo real del envío de mensajes a los perfiles de destino desde el servidor de correo mejorado, los registros de envío muestran el **[!UICONTROL Sent]** estado de cada dirección que recibió correctamente el mensaje. El porcentaje de **[!UICONTROL Delivered]** se incrementa en consecuencia con cada envío correcto.

Cuando el servidor de correo mejorado devuelve mensajes de rebote duro, su estado de registro cambia de **[!UICONTROL Pending]** hasta **[!UICONTROL Failed]** y el **[!UICONTROL Bounces + errors]** El porcentaje de sube en consecuencia.

Cuando se generan informes de los mensajes de rebote suave desde el servidor de correo mejorado, su estado de registro también cambia de **[!UICONTROL Pending]** hasta **[!UICONTROL Failed]** y el **[!UICONTROL Bounces + errors]** El porcentaje de sube en consecuencia. El porcentaje de **[!UICONTROL Delivered]** permanece sin cambios. A continuación, se vuelven a intentar los mensajes de devolución suave a lo largo del [período de validez del envío](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Delivered]** sube en consecuencia.

* De lo contrario, el estado se mantiene como **[!UICONTROL Failed]**. El **[!UICONTROL Delivered]** y **[!UICONTROL Bounces + errors]** los porcentajes permanecen inalterados.

>[!NOTE]
>
>Para obtener más información acerca de las devoluciones suaves y duras, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Para obtener más información sobre reintentos después de un error temporal de envío, consulte [esta sección](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Cambios introducidos por EFS {#changes-introduced-by-efs}

Las siguientes tablas muestran los cambios en los KPI y los estados de envío de registros introducidos por la capacidad de EFS.

**Con servicio de comentarios de correo electrónico**

| Paso en el proceso de envío | Resumen de KPI | Estado de envío de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente desde Campaign al servidor de correo mejorado | <ul><li>**[!UICONTROL Delivered]** El porcentaje de empieza en 0%</li><li>**[!UICONTROL Bounces + errors]** El porcentaje de empieza en 0%</li></ul> | Pendiente |
| Los mensajes de devolución dura se informan desde el servidor de correo mejorado | <ul><li>No hay cambios en el porcentaje de **[!UICONTROL Delivered]**</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** sube en consecuencia</li></ul> | Error |
| Los mensajes de devolución suave se informan desde el servidor de correo mejorado | <ul><li>No hay cambios en el porcentaje de **[!UICONTROL Delivered]**</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** sube en consecuencia</li></ul> | Error |
| Los reintentos de mensajes de devolución suave se realizan correctamente | <ul><li>El porcentaje de **[!UICONTROL Delivered]** sube en consecuencia</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** baja en consecuencia</li></ul> | Enviado |
| Error en los reintentos de mensajes de devolución suave | <ul><li> No hay cambios en el porcentaje de **[!UICONTROL Delivered]** </li><li> No hay cambios en el porcentaje de **[!UICONTROL Bounces + errors]** </li></ul> | Error |

**Sin servicio de comentarios de correo electrónico**

| Paso en el proceso de envío | Resumen de KPI | Estado de envío de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente desde Campaign al servidor de correo mejorado | <ul><li>El porcentaje de **[!UICONTROL Delivered]** comienza en 100 %</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** comienza en 0 %</li></ul> | Enviado |
| Los mensajes de devolución dura se informan desde el servidor de correo mejorado | <ul><li>El porcentaje de **[!UICONTROL Delivered]** baja en consecuencia</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** sube en consecuencia</li></ul> | Error |
| Los mensajes de devolución suave se informan desde el servidor de correo mejorado | <ul><li>No hay cambios en el porcentaje de **[!UICONTROL Delivered]**</li><li>No hay cambios en el porcentaje de **[!UICONTROL Bounces + errors]**</li></ul> | Enviado |
| Los reintentos de mensajes de devolución suave se realizan correctamente | <ul><li>No hay cambios en el porcentaje de **[!UICONTROL Delivered]**</li><li>No hay cambios en el porcentaje de **[!UICONTROL Bounces + errors]**</li></ul> | Enviado |
| Error en los reintentos de mensajes de devolución suave | <ul><li>El porcentaje de **[!UICONTROL Delivered]** baja en consecuencia</li><li>El porcentaje de **[!UICONTROL Bounces + errors]** sube en consecuencia</li></ul> | Error |

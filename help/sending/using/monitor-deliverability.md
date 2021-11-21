---
title: Monitorización de la capacidad de entrega en Adobe Campaign Standard
description: Utilice las herramientas que ofrece Adobe Campaign Standard para monitorizar la capacidad de envío de su plataforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 58%

---

# Supervisión de la capacidad de entrega{#monitor-deliverability}

A continuación encontrará detalles sobre la **[!UICONTROL Delivery throughput]** , así como las diferentes herramientas de monitorización que ofrece Adobe Campaign. Estas son algunas directrices adicionales sobre la monitorización de la capacidad de envío:
* Compruebe regularmente el rendimiento del envío de toda la plataforma para comprobar si es coherente con la configuración original.
* Compruebe que los reintentos estén correctamente configurados (30 minutos para el periodo de reintento y más de 20 reintentos) en plantillas de envíos.
* Compruebe periódicamente si puede acceder al buzón de rechazados y que la cuenta no esté a punto de caducar.
* Compruebe el rendimiento de cada envío para asegurarse de que es coherente con la validez del contenido del envío (p. ej. las “ventas flash” deben entregarse en minutos, no en días).
* Compruebe que las cantidades de errores y nuevas cuarentenas sean coherentes con otros envíos.
* Consulte cuidadosamente los registros de envío en detalle para comprobar el tipo de errores resaltados (lista de bloqueados, problemas de DNS, reglas de correo no deseado, etc…).

## Rendimiento de la entrega {#delivery-throughput}

Este informe contiene información sobre el rendimiento de entrega de toda la plataforma durante un periodo determinado para medir la velocidad a la que se envían los mensajes.

Para obtener más información sobre esto, consulte [Rendimiento de los envíos](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Puede configurar los valores visualizados cambiando la escala temporal.

Hay otros informes disponibles, como **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Para obtener más información, consulte [Informes dinámicos](../../reporting/using/about-dynamic-reports.md).

## Seguimiento de entregas {#monitoring-deliveries}

El panel de mensajes le permite acceder a los registros de envío: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** y **[!UICONTROL Tracked URLs]**. Muestran los detalles del envío, qué destinatario se ha excluido y por qué, así como la información de seguimiento como aperturas y clics.

Para obtener más información sobre esto, consulte [Monitorización de un envío](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Recibir alertas {#receiving-alerts}

La variable **[!UICONTROL Delivery alerting]** es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus entregas.

Para obtener más información, consulte [Recibir alertas cuando se produzcan errores](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->

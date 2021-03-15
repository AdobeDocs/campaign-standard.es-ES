---
solution: Campaign Standard
product: campaign
title: Monitorización de la capacidad de entrega en Adobe Campaign Standard
description: Utilice las herramientas que ofrece Adobe Campaign Standard para monitorizar la capacidad de envío de su plataforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Capacidad de entrega
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 63%

---


# Supervisión de la capacidad de entrega{#monitor-deliverability}

A continuación encontrará detalles sobre el informe **[!UICONTROL Delivery throughput]**, así como las diferentes herramientas de monitorización que ofrece Adobe Campaign. Estas son algunas directrices adicionales sobre la monitorización de la capacidad de envío:
* Compruebe regularmente el rendimiento del envío de toda la plataforma para comprobar si es coherente con la configuración original.
* Compruebe que los reintentos estén correctamente configurados (30 minutos para el periodo de reintento y más de 20 reintentos) en plantillas de envíos.
* Compruebe periódicamente si puede acceder al buzón de rechazados y que la cuenta no esté a punto de caducar.
* Compruebe el rendimiento de cada envío para asegurarse de que es coherente con la validez del contenido del envío (p. ej. las “ventas flash” deben entregarse en minutos, no en días).
* Cuando utilice olas, compruebe que cada ola tenga tiempo suficiente para finalizar antes de que se active la siguiente.
* Compruebe que las cantidades de errores y nuevas cuarentenas sean coherentes con otros envíos.
* Consulte cuidadosamente los registros de envío en detalle para comprobar el tipo de errores resaltados (lista de bloqueados, problemas de DNS, reglas de correo no deseado, etc…).

## Rendimiento de entrega {#delivery-throughput}

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

La función **[!UICONTROL Delivery alerting]** es un sistema de administración de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Para obtener más información sobre esto, consulte [Recibir alertas cuando se producen errores](../../sending/using/receiving-alerts-when-failures-happen.md).

## Signal Spam {#signal-spam}

Signal Spam es un servicio francés que ofrece el sistema de informes de bucle de retroalimentación anonimizado para los ISP franceses (Orange, SFR).

Este servicio le permite seguir la reputación de los ISP franceses y la evolución de la actividad de los clientes.

Signal Spam también proporciona quejas directas de que los usuarios finales registran a través de una interfaz dedicada. Esas quejas se ponen en cuarentena a partir de la base de datos de direcciones de correo electrónico.

## 250ok {#solution-250ok}

250ok es una solución de monitorización que proporciona  de IP y lista de bloqueados de dominio, así como indicadores de reputación.

La información se proporciona en tiempo real, lo que permite una asistencia proactiva. 250ok una solución complementaria a las herramientas internas de capacidad de envío de Adobe.

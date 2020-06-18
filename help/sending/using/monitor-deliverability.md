---
title: Monitoreo de la capacidad de entrega en Adobe Campaign Standard
description: Utilice las herramientas ofrecidas por Adobe Campaign Standard para supervisar la capacidad de entrega de la plataforma.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c89973e2c733d9c0b1c4434e77ef51103ccde0fa
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 50%

---


# Supervisión de la capacidad de entrega{#monitor-deliverability}

A continuación encontrará detalles sobre el **[!UICONTROL Delivery throughput]** informe, así como las diferentes herramientas de supervisión que ofrece Adobe Campaign. Estas son algunas directrices adicionales sobre la monitorización de la capacidad de envío:
* Compruebe regularmente el rendimiento del envío de toda la plataforma para comprobar si es coherente con la configuración original.
* Compruebe que los reintentos estén correctamente configurados (30 minutos para el periodo de reintento y más de 20 reintentos) en plantillas de envíos.
* Compruebe periódicamente si puede acceder al buzón de rechazados y que la cuenta no esté a punto de caducar.
* Compruebe el rendimiento de cada envío para asegurarse de que es coherente con la validez del contenido del envío (p. ej. las “ventas flash” deben entregarse en minutos, no en días).
* Cuando utilice olas, compruebe que cada ola tenga tiempo suficiente para finalizar antes de que se active la siguiente.
* Compruebe que las cantidades de errores y nuevas cuarentenas sean coherentes con otros envíos.
* Consulte detenidamente a los registros de envío en detalle para comprobar el tipo de errores que se resaltan (listas de bloques, problemas de DNS, reglas antispam, etc.).

## Rendimiento de entrega {#delivery-throughput}

Este informe contiene información sobre el rendimiento del envío de toda la plataforma durante un período determinado para medir la velocidad a la que se entregan los mensajes.

Para obtener más información sobre esto, consulte Rendimiento [de Envío](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Puede configurar los valores visualizados cambiando la escala temporal.

Hay otros informes disponibles, como **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Para obtener más información sobre esto, consulte Informes [](../../reporting/using/about-dynamic-reports.md)dinámicos.

## Seguimiento de entregas {#monitoring-deliveries}

El panel de mensajes le permite acceder a los registros de envío: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** y **[!UICONTROL Tracked URLs]**. Muestran los detalles del envío, qué destinatario se ha excluido y por qué, así como la información de seguimiento como aperturas y clics.

Para obtener más información sobre esto, consulte [Monitorización de un envío](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Recibir alertas {#receiving-alerts}

La **[!UICONTROL Delivery alerting]** función es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Para obtener más información sobre esto, consulte [Recepción de alertas cuando se producen](../../sending/using/receiving-alerts-when-failures-happen.md)errores.

## Signal Spam {#signal-spam}

Signal Spam es un servicio francés que ofrece el sistema de informes de bucle de retroalimentación anonimizado para los ISP franceses (Orange, SFR).

Este servicio le permite seguir la reputación de los ISP franceses y la evolución de la actividad de los clientes.

Signal Spam también proporciona quejas directas de que los usuarios finales registran a través de una interfaz dedicada. Esas quejas se ponen en cuarentena a partir de la base de datos de direcciones de correo electrónico.

## 250ok {#solution-250ok}

250ok es una solución de monitoreo que proporciona listas de IP y bloques de dominio, así como indicadores de reputación.

La información se proporciona en tiempo real, lo que permite una asistencia proactiva. 250ok es una solución complementaria a las herramientas internas de entrega de Adobe.

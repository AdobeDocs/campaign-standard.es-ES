---
title: Monitoreo de la capacidad de entrega en Adobe Campaign Standard
description: Utilice las herramientas ofrecidas por Adobe Campaign Standard para supervisar la capacidad de entrega de su plataforma.
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
source-git-commit: 1d5bb21ab16df87e268b9eabe92965be1b052556

---


# Monitoreo de la capacidad de entrega{#monitor-deliverability}

A continuación encontrará detalles sobre el **[!UICONTROL Delivery throughput]** informe, así como las distintas herramientas de supervisión ofrecidas por Adobe Campaign. Estas son algunas directrices adicionales sobre la supervisión de la capacidad de entrega:
* Compruebe regularmente el rendimiento de la entrega para toda la plataforma para comprobar si es coherente con la configuración original.
* Compruebe que los reintentos están correctamente configurados (30 minutos para el período de reintento y más de 20 reintentos) en las plantillas de entrega.
* Compruebe periódicamente que el buzón de devoluciones esté accesible y que la cuenta no esté a punto de caducar.
* Compruebe el rendimiento de cada entrega para asegurarse de que es coherente con la validez del contenido de entrega (p. ej. 'ventas flash' deben entregarse en minutos, no en días).
* Cuando utilice ondas, compruebe que cada onda tiene tiempo suficiente para finalizar antes de que se active la siguiente.
* Compruebe que el número de errores y de nuevas cuarentena son coherentes con otras entregas.
* Consulte detenidamente los registros de entrega para comprobar el tipo de errores resaltados (listas grises o negras, problemas de DNS, reglas antispam, etc.).

## Rendimiento de envío {#delivery-throughput}

Este informe contiene información sobre el rendimiento de entrega de toda la plataforma durante un período determinado para medir la velocidad a la que se entregan los mensajes.

Para obtener más información sobre esto, consulte Rendimiento [de envío](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Puede configurar los valores mostrados cambiando la escala de tiempo.

Hay otros informes disponibles, como **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Para obtener más información sobre esto, consulte Informes [](../../reporting/using/about-dynamic-reports.md)dinámicos.

## Supervisión de entregas {#monitoring-deliveries}

El tablero de mensajes le permite acceder a los registros de entrega: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** y **[!UICONTROL Tracked URLs]**. Muestran los detalles del envío, qué destino se ha excluido y por qué, así como la información de seguimiento como aperturas y clics.

Para obtener más información sobre esto, consulte [Supervisión de un envío](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Recibir alertas {#receiving-alerts}

La **[!UICONTROL Delivery alerting]** función es un sistema de gestión de alertas que permite a un grupo de usuarios recibir automáticamente notificaciones que contengan información sobre la ejecución de sus envíos.

Para obtener más información sobre esto, consulte [Recepción de alertas cuando se producen](../../sending/using/receiving-alerts-when-failures-happen.md)errores.

## Correo no deseado de señal {#signal-spam}

Signal Spam es un servicio francés que ofrece informes de bucle de retroalimentación anónimos para los ISP franceses (Orange, SFR).

Este servicio le permite seguir la reputación de los ISP franceses y la evolución de la actividad de los clientes.

El correo no deseado de señal también proporciona quejas directas de que los usuarios finales inician sesión a través de una interfaz dedicada. Esas quejas se ponen en cuarentena a partir de la base de datos de direcciones de correo electrónico.

## 250 ok {#solution-250ok}

250ok es una solución de monitoreo que proporciona IP, listas negras de dominios e indicadores de reputación.

La información proporcionada es en tiempo real, lo que permite una asistencia proactiva. 250ok es una solución complementaria a las herramientas internas de entrega de Adobe.

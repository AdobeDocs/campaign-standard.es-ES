---
title: Mensajes de seguimiento y monitorización
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Descubra cómo Adobe Campaign le permite realizar un seguimiento de los mensajes enviados y descubrir cómo reaccionan sus destinatarios al envío
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 39%

---

# Seguimiento y monitorización {#track-and-monitor}

¿Ha hecho clic en el botón Enviar? Veamos qué pasa. Una vez entregado el envío, Adobe Campaign le permite realizar un seguimiento de los mensajes enviados y descubrir cómo reaccionan sus destinatarios al envío. Esto le ayuda a mejorar los envíos futuros y a optimizar sus próximas campañas.

## Seguimiento de entregas {#monitoring-deliveries}

Para controlar sus campañas, debe asegurarse de que el mensaje se haya enviado a sus destinatarios.

**Sugerencias**

* Puede controlar el estado de los mensajes en los registros de envío.

* Para realizar un seguimiento de los envíos erróneos o correctos, Adobe Campaign proporciona un sistema de alertas por correo electrónico que envía notificaciones para informar a los usuarios de las actividades importantes del sistema.

* Desde el panel de mensajes, puede acceder a varios informes para este mensaje específico.

Para obtener más información, consulte [Monitorización de un envío](../../sending/using/monitoring-a-delivery.md).

## Seguimiento {#tracking-deliveries}

Para conocer mejor el comportamiento de los perfiles de destino, puede realizar un seguimiento de cómo reaccionan a un envío: recepción, apertura, clics en vínculos, bajas de suscripción, etc. Consulte la pestaña **Tracking logs** del envío.

**Sugerencia**: El seguimiento de mensajes está activado de forma predeterminada. Para configurar direcciones URL, seleccione la opción Mostrar direcciones URL en la sección inferior del asistente de envíos. Por cada dirección URL del mensaje, puede elegir si desea activar el seguimiento.

Para obtener más información, consulte la sección [Seguimiento de mensajes](../../sending/using/tracking-messages.md) y la descripción [Seguimiento de indicadores](../../reporting/using/tracking-indicators.md).

## Informes dinámicos {#dyn-reports}

Los informes dinámicos le permiten crear informes totalmente personalizables y en tiempo real para supervisar sus campañas. Los Dimension, las métricas y las visualizaciones le permiten medir el impacto y el éxito de sus campañas en los destinatarios.

**Sugerencia** : Los informes integrados están disponibles para que usted supervise sus campañas, pero estos informes también se pueden personalizar si arrastra y suelta cualquier métrica o dimensión en el informe.

Para obtener más información, consulte la [Guía de informes](../../reporting/using/about-dynamic-reports.md).

## Clics activos

El informe de clics activos presenta el contenido del mensaje (HTML o texto) con el porcentaje de clics en cada vínculo. Al mostrar el porcentaje de clics en cada contenido dinámico, puede medir qué contenido atrae más a los destinatarios.

Para obtener más información, consulte el [Informe de clics activos](../../reporting/using/hot-clicks.md).

## Sugerencias de rendimiento de entrega {#performance-tips}

* Evite mantener las entregas en estado de error en la instancia, ya que esto mantiene tablas temporales e influye en el rendimiento.

* Elimine los envíos que ya no sean necesarios y los destinatarios inactivos de la base de datos para mantener la calidad de la dirección.

* Evite programar entregas grandes al mismo tiempo. Tenga en cuenta que la carga puede tardar entre 5 y 10 minutos en propagarse uniformemente en el sistema.

**Temas relacionados:**

* [Recepción de alertas cuando se produzcan errores](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informes](../../reporting/using/about-dynamic-reports.md)

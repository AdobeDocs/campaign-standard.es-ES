---
title: Mensajes de seguimiento y monitorización
seo-title: Mensajes de seguimiento y monitorización
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 44%

---


# Seguimiento y monitorización {#track-and-monitor}

¿Ha hecho clic en el botón Enviar? Veamos qué pasa. Una vez entregado el envío, Adobe Campaign le permite realizar un seguimiento de los mensajes enviados y descubrir cómo reaccionan sus destinatarios al envío. Esto le ayudará a mejorar los envíos futuros y a optimizar sus próximas campañas.

## Seguimiento de envíos {#monitoring-deliveries}

Para controlar sus campañas, debe asegurarse de que el mensaje se haya enviado a sus destinatarios.

**Sugerencias**

* Puede controlar el estado de los mensajes en los registros de envío.

* Para realizar un seguimiento de los éxitos o errores del envío, Adobe Campaign proporciona un sistema de alertas por correo electrónico que envía notificaciones para informar a los usuarios de las actividades importantes del sistema.

* Desde el panel de mensajes, puede acceder a varios informes para este mensaje específico.

For more this, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

## Seguimiento {#tracking-deliveries}

Para conocer mejor el comportamiento de los perfiles objetivo, puede rastrear cómo reaccionan a un envío: recepción, apertura, clics en enlaces, suscripciones, etc. Consulte la ficha **Registros de seguimiento** del envío.

**Sugerencia**: El seguimiento de mensajes está activado de forma predeterminada. Para configurar direcciones URL, seleccione la opción Mostrar direcciones URL en la sección inferior del asistente de envíos. Por cada dirección URL del mensaje, puede elegir si desea activar el seguimiento.

For more on this, refer to the [Tracking messages](../../sending/using/tracking-messages.md) section and the [Tracking indicators](../../reporting/using/tracking-indicators.md) description.

## Informes dinámicos {#dyn-reports}

Los informes dinámicos le permiten crear informes totalmente personalizables y en tiempo real para supervisar sus campañas. Los Dimension, las métricas y las visualizaciones le permiten medir el impacto y el éxito de sus campañas en los destinatarios.

**Sugerencia** : Los informes integrados están disponibles para que usted pueda monitorear sus campañas, pero estos informes también se pueden personalizar arrastrando y soltando cualquier métrica o dimensión en el informe.

For more on this, refer to the [Reporting guide](../../reporting/using/about-dynamic-reports.md).

## Clics activos

El informe de clics interactivos presenta el contenido del mensaje (HTML o texto) con el porcentaje de clics en cada vínculo. Al mostrar el porcentaje de clics en cada contenido dinámico, puede medir el contenido que más atrae a los destinatarios.

Para obtener más información sobre esto, consulte el informe [de clic](../../reporting/using/hot-clicks.md)urgente.

## Sugerencias de rendimiento de envío {#performance-tips}

* Evite mantener las entregas en estado de error en la instancia, ya que esto mantiene tablas temporales e influye en el rendimiento.

* Elimine los envíos que ya no sean necesarios y los destinatarios inactivos de la base de datos para mantener la calidad de la dirección.

* Evite programar entregas grandes al mismo tiempo. Tenga en cuenta que la carga puede tardar entre 5 y 10 minutos en propagarse uniformemente en el sistema.

**Temas relacionados:**

* [Recibir alertas cuando se produzcan errores](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informes](../../reporting/using/about-dynamic-reports.md)

---
solution: Campaign Standard
product: campaign
title: Directrices de monitorización
description: Esta sección presenta las directrices generales para la monitorización del Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

---


# Directrices de monitorización {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoreo del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitorización de flujos de trabajo</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Seguimiento de entregas</a></p></td></tr>
</table>

Campaign Standard proporciona varias formas de monitorear las instancias para asegurarse de que el sistema está en buen estado y, finalmente, solucionar los problemas que pueden producirse al configurar flujos de trabajo, enviar envíos, etc.

## Monitoreo del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificaciones**
del sistemaLa interfaz de Campaign Standard proporciona un panel de notificación que le permite estar informado de lo que sucede en el sistema: estados de eventos, actualizaciones del sistema, acción requerida, etc. [Más información](../../start/using/interface-description.md#top-bar)


**Flujos de**
trabajo técnicosLos flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse de forma regular en el servidor. Para asegurarse de que la instancia está sana y funciona correctamente, debe asegurarse de que siempre está funcionando. [Más información](../../administration/using/technical-workflows.md)

**Panel**
de controlEl Panel de control de Campaign le permite administrar varias configuraciones de su instancia: Permisos de URL, compruebe los detalles de la instancia como las versiones de compilación de los servidores, supervise el uso de perfiles activos, etc. También permite supervisar el espacio disponible en los servidores SFTP conectados a la instancia. [Más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Tenga en cuenta que el Panel de control de Campaign solo está disponible para los usuarios administradores y para todos los clientes que utilicen los servicios gestionados de Adobe.

**Objetos técnicosEl**
  **[!UICONTROL Diagnosis]** menú es una herramienta clave para monitorear y analizar los diferentes objetos técnicos generados por la aplicación: esquemas de datos, páginas web, trabajos por lotes, etc. [Más información](../../developing/using/monitoring-data-model-changes.md)

**Exportar**
auditoríasLas auditorías de exportación permiten supervisar las exportaciones realizadas en las instancias: archivos cargados desde flujos de trabajo, exportaciones de listas y archivos descargados desde mensajes de correo directo.
[Más información](../../administration/using/auditing-export-logs.md)

****
LicenciasEn el  **[!UICONTROL Licenses]** menú, supervise la información sobre las instancias: licencias instaladas, versiones de compilación y aceptaciones de acuerdos de términos.
[Más información](../../administration/using/licenses.md)

## Monitorización de flujos de trabajo {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Prácticas recomendadas y**
solución de problemasLas siguientes optimizaciones y directrices de solución de problemas al utilizar flujos de trabajo pueden ayudar a mejorar el rendimiento.
[Más información](../../automating/using/best-practices-workflows.md)

**Registros y**
tareasLa supervisión de registros de flujo de trabajo es un paso clave para analizar los flujos de trabajo y asegurarse de que se ejecutan correctamente.
[Más información](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

****
NotificacionesCampaign Standard le permite enviar notificaciones a los supervisores para supervisar la ejecución de sus flujos de trabajo y ver si hay algún error que requiera su atención.
[Más información](../../automating/using/monitoring-workflow-execution.md#error-management)

## Seguimiento de entregas {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

****
EntregabilidadCampaign Standard proporciona varias herramientas de entrega para ayudarle a mejorar el número de mensajes entregados correctamente: informes de perspectiva de envío, envío de optimización de tiempo, previsualización de mensajes, procesamiento de correo electrónico, administración de cuarentenas, etc.
[Más información](../../sending/using/about-deliverability.md)

****
EntregasUna vez enviados los mensajes, los registros detallados le permiten monitorear los envíos y medir el éxito de la campaña, así como también rastrear el comportamiento de los destinatarios de mensajes.
[Más información](../../sending/using/monitoring-a-delivery.md)

**Alerta**
de envíoCon la función de alerta de Envío, puede configurar alertas que se enviarán automáticamente a un grupo de usuarios en relación con la ejecución de envíos: error de envío o preparación, tasa de devoluciones incorrecta, rendimiento bajo, etc.
[Más información](../../sending/using/receiving-alerts-when-failures-happen.md)

**Informes**
dinámicosEl sistema de informes dinámico proporciona varios informes que le ayudan a mantenerse informado del rendimiento de sus envíos: devoluciones, entregas más visualizadas por destinatarios, rendimiento de envíos, etc.
[Más información](../../reporting/using/about-dynamic-reports.md)

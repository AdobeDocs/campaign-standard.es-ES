---
solution: Campaign Standard
product: campaign
title: Directrices de monitorización
description: Esta sección presenta las directrices generales para el Campaign Standard de monitorización.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---


# Directrices de monitorización {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitorización del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitorización de flujos de trabajo</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Seguimiento de entregas</a></p></td></tr>
</table>

Campaign Standard proporciona varias formas de monitorizar las instancias para asegurarse de que el sistema está en buen estado y, finalmente, solucionar los problemas que pueden producirse al configurar flujos de trabajo, enviar envíos, etc.

## Monitorización del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificaciones del sistema**

La interfaz del Campaign Standard proporciona un panel de notificación que le permite estar informado de lo que está sucediendo en el sistema: estados de eventos, actualizaciones del sistema, acciones necesarias, etc. [Obtenga más información](../../start/using/interface-description.md#top-bar)


**Flujos de trabajo técnicos**

Los flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse de forma regular en el servidor. Para garantizar que la instancia esté en buen estado y funcionando correctamente, debe asegurarse de que esté siempre en funcionamiento. [Obtenga más información](../../administration/using/technical-workflows.md)

**Panel de control de Campaign**

El Panel de control de Campaign le permite administrar varias configuraciones de su instancia: Permisos de URL, compruebe los detalles de su instancia como las versiones de compilación de sus servidores, supervise el uso de perfiles activos, etc. También le permite supervisar el espacio disponible en los servidores SFTP conectados a su instancia. [Obtenga más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Todos los usuarios administradores pueden acceder a Panel de control de Campaign. Los pasos para otorgar acceso de administrador a un usuario se detallan en [esta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel).

**Objetos técnicos**

El menú **[!UICONTROL Diagnosis]** es una herramienta clave para monitorear y analizar los diferentes objetos técnicos generados por la aplicación: esquemas de datos, páginas web, trabajos por lotes, etc. [Obtenga más información](../../developing/using/monitoring-data-model-changes.md)

**Exportación de auditorías**

Las auditorías de exportación permiten supervisar las exportaciones realizadas en las instancias: archivos cargados desde flujos de trabajo, exportaciones de listas y archivos descargados desde mensajes de correo postal.
[Obtenga más información](../../administration/using/auditing-export-logs.md)

**Licencias**

Con el menú **[!UICONTROL Licenses]**, supervise la información sobre las instancias: licencias instaladas, versiones de compilación y aceptaciones de acuerdos de términos.
[Obtenga más información](../../administration/using/licenses.md)

## Monitorización de flujos de trabajo {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Prácticas recomendadas y solución de problemas**

Las siguientes prácticas recomendadas y directrices para la resolución de problemas al utilizar flujos de trabajo pueden ayudar a mejorar el rendimiento.
[Obtenga más información](../../automating/using/best-practices-workflows.md)

**Registros y tareas**

La monitorización de registros de flujo de trabajo es un paso clave para analizar los flujos de trabajo y asegurarse de que se ejecutan correctamente.
[Obtenga más información](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notificaciones**

Campaign Standard le permite enviar notificaciones a los supervisores para supervisar la ejecución de los flujos de trabajo y ver si hay algún error que requiera su atención.
[Obtenga más información](../../automating/using/monitoring-workflow-execution.md#error-management)

## Seguimiento de entregas {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Capacidad de entrega**

Campaign Standard proporciona varias herramientas de envío para ayudarle a mejorar el número de mensajes enviados correctamente: informes de rendimiento de entrega, optimización del tiempo de envío, previsualización de mensajes, procesamiento de correo electrónico, administración de cuarentena, etc.
[Obtenga más información](../../sending/using/about-deliverability.md)

**Entregas**

Una vez enviados los mensajes, los registros detallados le permiten monitorizar los envíos y medir el éxito de la campaña, así como rastrear el comportamiento de los destinatarios de los mensajes.
[Obtenga más información](../../sending/using/monitoring-a-delivery.md)

**Alertas de envío**

Con la función Alerta de entrega , puede configurar alertas que se envían automáticamente a un grupo de usuarios en relación con la ejecución de los envíos: error de envío o preparación, tasa de devoluciones incorrecta, rendimiento bajo, etc.
[Obtenga más información](../../sending/using/receiving-alerts-when-failures-happen.md)

**Informes dinámicos**

Los informes dinámicos proporcionan varios informes para ayudarle a estar informado del rendimiento de los envíos: devoluciones, envíos más vistos por destinatarios, rendimiento de los envíos, etc.
[Obtenga más información](../../reporting/using/about-dynamic-reports.md)

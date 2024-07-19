---
title: Directrices de monitorización
description: Esta página presenta las directrices generales para el Campaign Standard de monitorización
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 13%

---

# Directrices de monitorización {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitorización del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitorización de flujos de trabajo</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Seguimiento de entregas</a></p></td></tr>
</table>

Campaign Standard proporciona varias formas de monitorizar las instancias para asegurarse de que el sistema esté en buen estado y, finalmente, solucionar problemas que pueden producirse al configurar flujos de trabajo, realizar envíos, etc.

## Monitorización del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificaciones del sistema**

La interfaz de Campaign Standard proporciona un panel de notificaciones que le permite mantenerse informado de lo que está ocurriendo en el sistema: eventos, estados, actualizaciones del sistema, acciones requeridas, etc. [Más información](../../start/using/interface-description.md#top-bar)


**Flujos de trabajo técnicos**

Los flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse de forma regular en el servidor. Para garantizar que la instancia esté en buen estado y funcione correctamente, debe asegurarse de que estén siempre en funcionamiento. [Más información](../../administration/using/technical-workflows.md)

**Panel de control**

El Panel de control de Campaign le permite administrar varias configuraciones de la instancia: permisos de URL, comprobar los detalles de la instancia, como las versiones de compilación de los servidores, monitorizar el uso de perfiles activos, etc. También le permite monitorizar el espacio disponible en los servidores SFTP conectados a su instancia. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es).

>[!NOTE]
>
>Todos los usuarios administradores pueden acceder al Panel de control. Los pasos para otorgar acceso de administrador a un usuario se detallan en [esta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=es#discover-control-panel).

**Objetos técnicos**

El menú **[!UICONTROL Diagnosis]** es una herramienta clave para monitorizar y analizar los diferentes objetos técnicos generados por la aplicación: esquemas de datos, páginas web, trabajos por lotes, etc. [Más información](../../developing/using/monitoring-data-model-changes.md)

**Exportar auditorías**

Las auditorías de exportación permiten monitorizar las exportaciones realizadas en las instancias: archivos cargados desde flujos de trabajo, exportaciones de listas y archivos descargados de mensajes de correo postal.
[Más información](../../administration/using/auditing-export-logs.md)

**Licencias**

Con el menú **[!UICONTROL Licenses]**, supervise la información sobre las instancias: licencias instaladas, versiones de compilación y aceptaciones de acuerdos de términos.
[Más información](../../administration/using/licenses.md)

## Monitorización de flujos de trabajo {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Prácticas recomendadas y solución de problemas**

Las siguientes prácticas recomendadas y directrices para la resolución de problemas al utilizar flujos de trabajo pueden ayudar a mejorar el rendimiento.
[Más información](../../automating/using/best-practices-workflows.md)

**Registros y tareas**

La monitorización de los registros de flujo de trabajo es un paso clave para analizar los flujos de trabajo y asegurarse de que se ejecutan correctamente.
[Más información](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notificaciones**

Campaign Standard permite enviar notificaciones a los supervisores para monitorizar la ejecución de los flujos de trabajo y ver si hay algún error que requiera su atención.
[Más información](../../automating/using/monitoring-workflow-execution.md#error-management)

## Seguimiento de entregas {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Capacidad de entrega**

Campaign Standard proporciona varias herramientas de envío para ayudarle a mejorar el número de mensajes enviados correctamente: informes de rendimiento de envío, optimización del tiempo de envío, previsualización de mensajes, procesamiento de correo electrónico, administración de cuarentena, etc.
[Más información](../../sending/using/about-deliverability.md)

**Entregas**

Una vez enviados los mensajes, los registros detallados le permiten monitorizar los envíos y medir el éxito de la campaña, así como rastrear el comportamiento de los destinatarios de los mensajes.
[Más información](../../sending/using/monitoring-a-delivery.md)

**Alertas de envío**

Con la función de alerta de entrega, puede configurar alertas que se envían automáticamente a un grupo de usuarios con respecto a la ejecución de entregas: envío o preparación fallidos, proporción de devoluciones incorrecta, bajo rendimiento, etc.
[Más información](../../sending/using/receiving-alerts-when-failures-happen.md)

**Informes dinámicos**

La creación de informes dinámicos proporciona varios informes que le ayudan a mantenerse informado del rendimiento de las entregas: devoluciones, entregas más vistas por destinatarios, rendimiento de las entregas, etc.
[Más información](../../reporting/using/about-dynamic-reports.md)

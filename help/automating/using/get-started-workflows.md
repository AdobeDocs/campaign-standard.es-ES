---
title: Introducción a la administración de datos y procesos
description: Automatice los procesos con flujos de trabajo, administre datos y audiencias, envíe mensajes, y mucho más.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 31f62227736daf4f215fcbe1cf7b0a0a8574cda3
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 30%

---

# Introducción a la administración de datos y procesos {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Actividades de flujo de trabajo</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrado de datos</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar datos</a></p></td></tr>
</table>

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Se puede utilizar un flujo de trabajo, por ejemplo, para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar registros de la base de datos de Adobe Campaign.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Direccionamiento para administrar públicos o enviar mensajes.
* Administración de datos (ETL) para manipular datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

>[!IMPORTANT]
>
> Adobe recomienda a los clientes que no ejecuten más de 20 ejecuciones de flujos de trabajo activos simultáneamente, y que prioricen y extiendan la ejecución del flujo de trabajo a lo largo del tiempo. Para obtener más información, consulte las prácticas recomendadas que se ofrecen en [esta página](../../automating/using/best-practices-workflows.md).

## Actividades de flujo de trabajo {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Hay varias actividades disponibles para ayudarle a diseñar sus flujos de trabajo.

[Actividades de segmentación](../../automating/using/about-targeting-activities.md) permiten crear uno o más objetivos definiendo conjuntos y dividiendo o combinando estos conjuntos mediante operaciones de intersección, unión o exclusión.

Con [Actividades de ejecución](../../automating/using/about-execution-activities.md), coordine el flujo de trabajo y sus actividades, mientras [Actividades de canal](../../automating/using/about-channel-activities.md) permite combinar canales de comunicación de Campaign Standard para crear flujos de trabajo entre canales.

Finalmente, [Actividades de gestión de datos](../../automating/using/about-data-management-activities.md) permite manipular los datos de la base de datos.

Más información:

* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md)
* [Prácticas recomendadas con flujos de trabajo](../../automating/using/best-practices-workflows.md)

## Filtrado de datos {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveche el **editor de consultas** para filtrar datos de la base de datos y crear una población para una mejor segmentación de los destinatarios. El editor de consultas está disponible para realizar varias acciones en Campaign Standard: crear audiencias de tipo Query, definir objetivos de entrega o poblaciones en actividades de flujo de trabajo.

El editor de consultas viene con **filtros predefinidos y reglas** para un filtrado rápido y sencillo. Sin embargo, también puede utilizar **edición avanzada de expresiones** funciones. Esto le permite introducir manualmente condiciones y utilizar funciones para formar sus propias reglas.

Más información:

* [Edición de consultas](../../automating/using/editing-queries.md)
* [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Importar/exportar datos {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

El Campaign Standard viene con varios **funcionalidades de gestión de datos** para importar y exportar datos.

[Actividades de gestión de datos Workflows](../../automating/using/about-data-management-activities.md) permite importar datos, realizar actualizaciones masivas de campos, recibir o enviar archivos, o vincular datos no identificados a recursos existentes.

Con [Importar plantillas](../../automating/using/importing-data-with-import-templates.md), administre ciertos tipos de importación definidos por los administradores a través de funciones de importación simplificadas.

[Exportación de registros](../../automating/using/exporting-logs.md) permite exportar los datos de registro a través de un flujo de trabajo sencillo, que permite analizar los resultados de las campañas de marketing en sus propias herramientas de creación de informes o inteligencia de negocios.

Aprovechamiento [Paquetes](../../automating/using/managing-packages.md) para intercambiar recursos entre diferentes instancias de campaign, por ejemplo, para replicar la configuración de una instancia o para transferir datos de un servidor a otro, incluidos los recursos personalizados.

Finalmente, [Exportación de listas](../../automating/using/exporting-lists.md) permite exportar cualquier lista del Campaign Standard como, por ejemplo, la lista de perfiles de prueba, la lista de direcciones de correo electrónico en cuarentena, etc.

Más información:

* [Importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: Exportación e importación de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionales

* [Tutoriales en vídeo sobre procesos y administración de datos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=es)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Introducción al modelo de datos de Campaign Standard](../../developing/using/get-started-data-model.md)

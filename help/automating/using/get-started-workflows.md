---
title: Introducción a la administración de datos y procesos
description: Automatice los procesos con flujos de trabajo, administre datos y públicos, envíe mensajes, y mucho más.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
TQID: https://experienceleague.adobe.com/iTJyQV-76oRhjJ4vDLKfSMpYTA27UcYt9UmVW-9YVq4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b5f0aaf4-1e48-400d-95ac-6eb3078cf22f
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 22%

---

# Introducción a la administración de datos y procesos {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Actividades de flujo de trabajo</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrado de datos</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar datos</a></p></td></tr>
</table>

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Por ejemplo, puede utilizar un flujo de trabajo para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar sus registros a la base de datos de Adobe Campaign.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Direccionamiento para administrar públicos o enviar mensajes.
* Administración de datos (ETL) para manipular datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

>[!IMPORTANT]
>
> Adobe recomienda a los clientes que no ejecuten más de 20 ejecuciones de flujos de trabajo activos simultáneamente, y que prioricen y extiendan la ejecución del flujo de trabajo a lo largo del tiempo. Para obtener más información, consulte las prácticas recomendadas que se proporcionan en [esta página](../../automating/using/best-practices-workflows.md).

## Actividades de flujo de trabajo {#workflow-activities}

Hay varias actividades disponibles para ayudarle a diseñar sus flujos de trabajo.

[Las actividades de segmentación](../../automating/using/about-targeting-activities.md) le permiten crear uno o más objetivos definiendo conjuntos y dividiendo o combinando estos conjuntos mediante operaciones de intersección, unión o exclusión.

Con [Actividades de ejecución](../../automating/using/about-execution-activities.md), coordine el flujo de trabajo y sus actividades, mientras que las [Actividades de canal](../../automating/using/about-channel-activities.md) le permiten combinar canales de comunicación de Campaign Standard para crear flujos de trabajo multicanal.

Por último, [las actividades de administración de datos](../../automating/using/about-data-management-activities.md) le permiten manipular datos de su base de datos.

Más información:

* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md)
* [Prácticas recomendadas con flujos de trabajo](../../automating/using/best-practices-workflows.md)

## Filtrado de datos {#filter-data}

Aproveche **el editor de consultas** para filtrar datos de su base de datos y crear una población para una mejor segmentación de destinatarios. El editor de consultas está disponible para realizar varias acciones en Campaign Standard: crear audiencias de tipo Query, definir objetivos de entrega o poblaciones en actividades de flujo de trabajo.

El editor de consultas viene con **filtros predefinidos y reglas** para un filtrado rápido y fácil. Sin embargo, también puede utilizar las capacidades de **edición avanzada de expresiones**. Esto le permite introducir manualmente condiciones y utilizar funciones para formar sus propias reglas.

Más información:

* [Edición de consultas](../../automating/using/editing-queries.md)
* [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Importar/exportar datos {#import-export-data}

Campaign Standard incluye **funciones de administración de datos** para importar y exportar datos.

[Las actividades de administración de datos de flujos de trabajo](../../automating/using/about-data-management-activities.md) le permiten importar datos, realizar actualizaciones masivas de campos, recibir o enviar archivos, o vincular datos no identificados a recursos existentes.

Con [Importar plantillas](../../automating/using/importing-data-with-import-templates.md), administre ciertos tipos de importación definidos por los administradores mediante funciones de importación simplificadas.

[La exportación de registros](../../automating/using/exporting-logs.md) le permite exportar los datos de registro a través de un flujo de trabajo sencillo, lo que le permite analizar los resultados de sus campañas de marketing en sus propias herramientas de creación de informes o inteligencia de negocios.

Aproveche [Paquetes](../../automating/using/managing-packages.md) para intercambiar recursos entre diferentes instancias de Campaign, por ejemplo, para replicar la configuración de una instancia o para transferir datos de un servidor a otro, incluidos los recursos personalizados.

Por último, [las listas de exportación](../../automating/using/exporting-lists.md) le permiten exportar cualquier lista de Campaign Standard como, por ejemplo, la lista de perfiles de prueba, la lista de direcciones de correo electrónico en cuarentena, etc.

Más información:

* [Importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: Exportación e importación de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionales

* [Tutoriales en vídeo sobre procesos y administración de datos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=es)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Introducción al modelo de datos de Campaign Standard](../../developing/using/get-started-data-model.md)

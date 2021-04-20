---
solution: Campaign Standard
product: campaign
title: Introducción a la administración de datos y procesos
description: Automatice los procesos con flujos de trabajo, administre datos y audiencias, envíe mensajes, y mucho más.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---


# Introducción a la administración de datos y procesos {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Actividades de flujo de trabajo</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Ejemplos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar datos</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar datos</a></p></td></tr>
</table>

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Por ejemplo, puede utilizar un flujo de trabajo para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar sus registros en la base de datos de Adobe Campaign.

Un flujo de trabajo también puede incluir usuarios asignándoles tareas o haciendo que aprueben tareas realizadas. Esto significa que puede asignar una tarea a uno o varios usuarios para que trabajen en el contenido o especifiquen objetivos, y aprobar pruebas antes de enviar el mensaje.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Segmentación para administrar audiencias o enviar mensajes.
* Gestión de datos (ETL) para manipular los datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

## Actividades de flujo de trabajo {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Hay varias actividades disponibles para ayudarle a diseñar sus flujos de trabajo.

[Las ](../../automating/using/about-targeting-activities.md) actividades de segmentación le permiten crear uno o más destinos definiendo conjuntos y dividiendo o combinando estos conjuntos mediante operaciones de intersección, unión o exclusión.

Con [Execution activities](../../automating/using/about-execution-activities.md), coordine el flujo de trabajo y sus actividades, mientras que [Channel activities](../../automating/using/about-channel-activities.md) permite combinar canales de comunicación de Campaign Standard para crear flujos de trabajo entre canales.

Por último, [Data management activities](../../automating/using/about-data-management-activities.md) permiten manipular los datos de la base de datos.

Más información:

* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md)
* [Prácticas recomendadas del flujo de trabajo](../../automating/using/best-practices-workflows.md)

## Filtrar datos {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveche el **editor de consultas** para filtrar los datos de la base de datos y crear una población para dirigirse mejor a los destinatarios. El editor de consultas está disponible para realizar varias acciones en el Campaign Standard: cree audiencias de tipo Consulta , defina objetivos de envío o poblaciones en actividades de flujo de trabajo.

El editor de consultas viene con **filtros predefinidos y reglas** para un filtrado rápido y fácil. Sin embargo, también puede utilizar las capacidades de **edición avanzada de expresiones**. Esto le permite introducir manualmente condiciones y utilizar funciones para formar sus propias reglas.

Más información:

* [Edición de consultas](../../automating/using/editing-queries.md)
* [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Importar/exportar datos {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

El Campaign Standard viene con varias **funcionalidades de administración de datos** para importar y exportar datos.

[Las ](../../automating/using/about-data-management-activities.md) actividades de gestión de datos de flujos de trabajo permiten importar datos, realizar actualizaciones masivas en los campos, recibir o enviar archivos, o vincular datos no identificados a recursos existentes.

Con [Import templates](../../automating/using/importing-data-with-import-templates.md), administre ciertos tipos de importación definidos por los administradores a través de funciones de importación simplificadas.

[La exportación de ](../../automating/using/exporting-logs.md) registros permite exportar datos de registro a través de un flujo de trabajo sencillo que le permite analizar los resultados de sus campañas de marketing en sus propias herramientas de creación de informes o de BI.

Aproveche [Packages](../../automating/using/managing-packages.md) para intercambiar recursos entre diferentes instancias de campaña, por ejemplo, para replicar la configuración de una instancia o para transferir datos de un servidor a otro, incluidos los recursos personalizados.

Por último, [Exportación de listas](../../automating/using/exporting-lists.md) permite exportar cualquier lista de Campaign Standards como, por ejemplo, la lista de perfiles de prueba, la lista de direcciones de correo electrónico en cuarentena, etc.

Más información:

* [Importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: Exportación e importación de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionales

* [Tutoriales en vídeo sobre procesos y administración de datos](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Introducción al modelo de datos de Campaign Standard](../../developing/using/get-started-data-model.md)

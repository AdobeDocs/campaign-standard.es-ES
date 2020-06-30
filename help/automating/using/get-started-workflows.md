---
title: Introducción a los procesos y la gestión de datos
description: Adobe Campaign oferta un entorno gráfico completo que le permite diseñar y automatizar procesos.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9fbf0479019dfbe2964c517a0370f015d0f380a
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 7%

---


# Introducción a los procesos y la gestión de datos {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">actividades de flujo de trabajo</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Ejemplos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar datos</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar datos</a></p></td></tr>
</table>

Adobe Campaign oferta un entorno gráfico completo que le permite diseñar procesos complejos, incluyendo segmentación, ejecución de campañas, procesamiento de archivos, etc. Por ejemplo, puede utilizar un flujo de trabajo para descargar un archivo de un servidor, descomprimirlo e importar sus registros en la base de datos de Adobe Campaign.

Un flujo de trabajo también puede involucrar a los usuarios asignándoles tareas o haciéndoles aprobar tareas realizadas. Esto significa que puede asignar una tarea a uno o varios usuarios para trabajar en contenido o especificar destinatarios, y aprobar pruebas antes de enviar el mensaje.

Se pueden utilizar Flujos de trabajo en diferentes contextos, como por ejemplo:

* Establecimiento de objetivos para administrar audiencias o enviar mensajes.
* Gestión de datos (ETL) para manipular datos.
* Importación de datos en la base de datos de Campaña.
* Procesos técnicos como limpieza de bases de datos, recuperación de información de seguimiento, etc.

## actividades de flujo de trabajo {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Hay varias actividades disponibles para ayudarle a diseñar sus flujos de trabajo.

[Las actividades](../../automating/using/about-targeting-activities.md) de objetivo le permiten crear uno o varios destinatarios definiendo conjuntos y dividiendo o combinando estos conjuntos mediante operaciones de intersección, unión o exclusión.

Con actividades [de](../../automating/using/about-execution-activities.md)ejecución, coordine el flujo de trabajo y sus actividades, mientras que las actividades [de](../../automating/using/about-channel-activities.md) Canal le permiten combinar canales de comunicación de Campaign Standard para crear flujos de trabajo de canal cruzado.

Por último, las actividades [de](../../automating/using/about-data-management-activities.md) Gestión de datos permiten manipular datos de la base de datos.

Más información:

* [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)
* [Ejecución de un flujo de trabajo](../../automating/using/about-workflow-execution.md)
* [Prácticas recomendadas del flujo de trabajo](../../automating/using/best-practices-workflows.md)

## Filtrar datos {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveche el editor **de** consultas para filtrar datos de la base de datos y crear una población para mejorar el destinatario de sus destinatarios. El editor de consultas está disponible para realizar varias acciones en Campaign Standard: crear audiencias de tipo de Consulta, definir destinatarios de envío o poblaciones en actividades de flujo de trabajo.

El editor de consultas incluye **filtros predefinidos y reglas** para un filtrado rápido y sencillo. Sin embargo, también puede utilizar funciones **avanzadas de edición** de expresiones. Esto le permite introducir manualmente condiciones y utilizar funciones para formar sus propias reglas.

Más información:

* [Edición de consultas](../../automating/using/editing-queries.md)
* [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Import/export data {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard viene con varias funciones **de** gestión de datos para importar y exportar datos.

[Las actividades](../../automating/using/about-data-management-activities.md) de gestión de datos de Flujos de trabajo permiten importar datos, realizar actualizaciones masivas en los campos, recibir o enviar archivos o vincular datos no identificados a recursos existentes.

Con [Plantillas de importación](../../automating/using/importing-data-with-import-templates.md), gestione determinados tipos de importación definidos por los administradores mediante funciones de importación simplificadas.

[La exportación de registros](../../automating/using/exporting-logs.md) le permite exportar datos de registro a través de un flujo de trabajo sencillo, lo que le permite analizar los resultados de sus campañas de marketing en sus propias herramientas de sistema de informes o BI.

Aproveche [los paquetes](../../automating/using/managing-packages.md) para intercambiar recursos entre distintas instancias de campaña, por ejemplo, para replicar la configuración de una instancia o para transferir datos de un servidor a otro, incluidos los recursos personalizados.

Por último, [Exportar listas](../../automating/using/exporting-lists.md) permite exportar cualquier lista de Campaign Standard como, por ejemplo, la lista de perfiles de prueba, la lista de direcciones de correo electrónico de cuarentenas, etc.

Más información:

* [Importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: Exportación e importación de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionales

* [Vídeos de tutoriales sobre procesos y gestión de datos](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Introducción al modelo de datos de Campaign Standard](../../developing/using/get-started-data-model.md)

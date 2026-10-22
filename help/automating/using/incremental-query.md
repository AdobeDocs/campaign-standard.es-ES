---
title: Consulta incremental
description: La actividad consulta incremental permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 18d6ffc0-cfc3-436e-8f0c-ea9c307541e4
TQID: 'https://experienceleague.adobe.com/pU8TR9TKVwM7-YcCHkxrSZ07UkBxE652McpBXxIp-Ik'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 94%
---
# Consulta incremental{#incremental-query}

## Descripción {#description}

![](assets/incremental.png)

La actividad **[!UICONTROL Incremental query]** permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto permite segmentar solo elementos nuevos.

Puede definir los **[!UICONTROL Additional data]** para la población objetivo mediante una pestaña dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta de edición de consultas. Esta herramienta se detalla en una [sección dedicada](../../automating/using/editing-queries.md#about-query-editor).

## Contexto de uso {#context-of-use}

Una **[!UICONTROL Incremental query]** debe estar vinculada a un **[!UICONTROL Scheduler]** para definir la frecuencia de ejecución del flujo de trabajo y, por lo tanto, la consulta.

La pestaña **[!UICONTROL Processed data]**, que es específica de esta actividad, permite realizar vistas de los resultados de las ejecuciones anteriores de la actividad, si es necesario.

La actividad **[!UICONTROL Incremental query]** se puede utilizar para varios tipos de usos:

* Segmentación de personas para definir el destinatario de un mensaje, el público, etc.

* Exportación de datos.

  Puede utilizar una actividad de **[!UICONTROL Incremental query]** para exportar con regularidad nuevos registros en los archivos. Puede resultar útil, por ejemplo, si desea utilizar los datos de registro en herramientas externas de sistema de informes o BI. Puede encontrar un ejemplo completo en la sección [Registros de exportación](../../automating/using/exporting-logs.md).

**Temas relacionados**

* [Caso de uso: Consulta incremental de los suscriptores a un servicio](../../automating/using/incremental-query-on-subscribers.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Incremental query]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Si desea ejecutar una consulta en un recurso que no sea el de perfil, vaya a la pestaña **[!UICONTROL Properties]** de la actividad y seleccione un **[!UICONTROL Resource]** y una **[!UICONTROL Targeting dimension]**.

   El **[!UICONTROL Resource]** permite refinar los filtros mostrados en la paleta, mientras que la **[!UICONTROL Targeting dimension]**, contextual con respecto al recurso seleccionado, corresponde al tipo de población que desea obtener (perfiles identificados, envíos, datos vinculados al recurso seleccionado, etc.).

1. En la pestaña **[!UICONTROL Target]**, ejecute la consulta definiendo y combinando reglas.
1. En la pestaña **[!UICONTROL Processed data]**, seleccione el modo incremental que desee utilizar para las próximas ejecuciones del flujo de trabajo:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: se excluyen los resultados de ejecuciones anteriores para cada nueva ejecución.
   * **[!UICONTROL Use a date field]**: las siguientes ejecuciones solo tienen en cuenta los resultados con un valor del campo de fecha seleccionado superior o igual a la fecha de la última ejecución de la actividad **[!UICONTROL Incremental query]**. Puede seleccionar cualquier campo de fecha que pertenezca al recurso seleccionado en la pestaña **[!UICONTROL Properties]**. Este modo ofrece un mejor rendimiento al consultar recursos de gran tamaño, como datos de registro.

     Después de la primera ejecución del flujo de trabajo, puede ver en esta pestaña la última fecha de ejecución que se utiliza en la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

   >[!NOTE]
   >
   >El modo **[!UICONTROL Use a date field]** permite una mayor flexibilidad en función del campo de fecha seleccionado. Por ejemplo, si el campo seleccionado corresponde a una fecha de modificación, el modo de campo de fecha permite recuperar datos que se han actualizado recientemente, mientras que el otro modo excluye simplemente las grabaciones que ya estaban segmentadas en una ejecución anterior, aunque se hayan modificado desde la última ejecución del flujo de trabajo.

   ![](assets/incremental_query_usedatefield.png)

1. Puede definir los **[!UICONTROL Additional data]** para la población objetivo mediante una pestaña dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En particular, puede añadir datos de las tablas de la base de datos de Adobe Campaign vinculadas a la dimensión de segmentación de la consulta. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data).
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Enriquecimiento de datos {#enriching-data}

Al igual que para una consulta, puede enriquecer los datos de una **[!UICONTROL Incremental query]**. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data).

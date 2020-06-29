---
title: Consulta incremental
description: La actividad de Consulta incremental permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---


# Consulta incremental{#incremental-query}

## Descripción {#description}

![](assets/incremental.png)

La **[!UICONTROL Incremental query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto permite el destinatario de solo elementos nuevos.

Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta de edición de consultas. Esta herramienta se detalla en una sección [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

## Contexto de uso {#context-of-use}

Un **[!UICONTROL Incremental query]** debe estar vinculado a un **[!UICONTROL Scheduler]** para definir la frecuencia de ejecución del flujo de trabajo y, por lo tanto, la consulta.

La **[!UICONTROL Processed data]** ficha, que es específica de esta actividad, permite realizar vistas de los resultados de las ejecuciones anteriores de la actividad, si es necesario.

La **[!UICONTROL Incremental query]** actividad se puede utilizar para varios tipos de usos:

* Segmentación de individuos para definir el destinatario de un mensaje, audiencia, etc.

* Exportación de datos.

   Puede utilizar una **[!UICONTROL Incremental query]** actividad para exportar con regularidad nuevos registros en los archivos. Puede resultar útil, por ejemplo, si desea utilizar los datos de registro en herramientas externas de sistema de informes o BI. Encontrará un ejemplo completo en la sección [Exportar registros](../../automating/using/exporting-logs.md) .

**Temas relacionados**

* [Caso de uso: Consulta incremental sobre los suscriptores de un servicio](../../automating/using/incremental-query-on-subscribers.md)

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Incremental query]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Si desea ejecutar una consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y seleccione una **[!UICONTROL Resource]** y una **[!UICONTROL Targeting dimension]**.

   El **[!UICONTROL Resource]** permite refinar los filtros mostrados en la paleta, mientras que el **[!UICONTROL Targeting dimension]**, contextual con respecto al recurso seleccionado, corresponde al tipo de población que desea obtener (perfiles identificados, envíos, datos vinculados al recurso seleccionado, etc.).

1. En la **[!UICONTROL Target]** ficha, ejecute la consulta definiendo y combinando reglas.
1. En la **[!UICONTROL Processed data]** ficha, seleccione el modo incremental que desee utilizar para las próximas ejecuciones del flujo de trabajo:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:: se excluyen los resultados de ejecuciones anteriores para cada nueva ejecución.
   * **[!UICONTROL Use a date field]**:: las siguientes ejecuciones sólo tienen en cuenta los resultados que tienen bueno el campo de fecha seleccionado o igual a la fecha de la última ejecución de la **[!UICONTROL Incremental query]** actividad. Puede seleccionar cualquier campo de fecha que pertenezca al recurso seleccionado en la **[!UICONTROL Properties]** ficha. Este modo ofrece un mejor rendimiento al consultar recursos de gran tamaño, como datos de registro.

      Después de la primera ejecución del flujo de trabajo, puede ver en esta ficha la última fecha de ejecución que se utilizará para la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.
   >[!NOTE]
   >
   >El **[!UICONTROL Use a date field]** modo permite una mayor flexibilidad en función del campo de fecha seleccionado. Por ejemplo, si el campo seleccionado corresponde a una fecha de modificación, el modo de campo de fecha le permitirá recuperar datos que se actualizaron recientemente, mientras que el otro modo excluirá simplemente las grabaciones que ya estaban segmentadas en una ejecución anterior, aunque se hayan modificado desde la última ejecución del flujo de trabajo.

   ![](assets/incremental_query_usedatefield.png)

1. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En particular, puede agregar datos de las tablas de la base de datos de Adobe Campaign vinculadas a la dimensión de segmentación de la consulta. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data) .
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Enriquecimiento de datos {#enriching-data}

Al igual que para una consulta, puede enriquecer los datos de una **[!UICONTROL Incremental query]**. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data) .

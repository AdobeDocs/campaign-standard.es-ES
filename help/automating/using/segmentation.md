---
title: Segmentación
description: La actividad Segmentación le permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3761ee4a-1ce5-4f9e-b2a5-84388b6b9db8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 92%

---

# Segmentación{#segmentation}

## Descripción {#description}

![](assets/segmentation.png)

La actividad **[!UICONTROL Segmentation]** le permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una sola transición o en transiciones diferentes.

>[!NOTE]
>
>De forma predeterminada, un miembro de la población entrante solo puede pertenecer a un único segmento. Los filtros se aplican según el orden de los segmentos en la actividad.

**Temas relacionados:**
* [Caso de uso: Segmentación en la ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Segmentación según grupos de edad](../../automating/using/segmentation-age-groups.md)

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Segmentation]** se suele colocar después de actividades de segmentación (consulta, intersección, unión, exclusión, etc.) para definir la población estándar basada en la formación de los segmentos.

**Temas relacionados**

* [Caso de uso: Segmentación de perfiles según sus grupos de edad](../../automating/using/segmentation-age-groups.md).

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Segmentation]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. En el **[!UICONTROL General]** , seleccione **[!UICONTROL Resource type]** sobre el que debe llevarse a cabo la segmentación:

   * **[!UICONTROL Database resource]** si la segmentación se realiza con datos que ya existen en la base de datos. Seleccione la **[!UICONTROL Filtering dimension]** en función de los datos que desee segmentar. De forma predeterminada, la segmentación se realiza en los **perfiles**.
   * **[!UICONTROL Temporary resource]** si la segmentación se realiza en los datos temporales del flujo de trabajo: seleccione el **[!UICONTROL Targeted set]** que contiene los datos que se van a segmentar. Este caso de uso se puede encontrar después de importar un archivo o si los datos de la base de datos se enriquecieron.

1. Seleccione el tipo de transición saliente que desee utilizar:

   * **[!UICONTROL Generate one transition per segment]**: se añade una transición saliente a cada segmento configurado al final de la actividad.
   * **[!UICONTROL Generate all segments in one transition]**: todos los segmentos configurados se reagrupan en una sola transición saliente. Especifique la etiqueta de transición. Los miembros de cada segmento mantienen el código de segmento que se les ha asignado.

1. Añada un segmento mediante el botón ![](assets/add_darkgrey-24px.png) o **[!UICONTROL Add an element]** y especifique las propiedades estándar:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: el segmento solo se habilitará si se recuperan datos.
   * **[!UICONTROL Filter initial population (query)]**: le permite filtrar la población de este segmento.
   * **[!UICONTROL Limit segment population]**: le permite limitar el tamaño del segmento.
   * **[!UICONTROL Filter and limit segment population]**: le permite filtrar la población del segmento y limitar su tamaño.
   * **[!UICONTROL Label]**: etiqueta de segmento.
   * **[!UICONTROL Segment code]**: código asignado a la población del segmento. El código de segmento se puede personalizar mediante una expresión estándar y variables de eventos (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclude segment from population]**: le permite excluir el segmento especificado de la población saliente de la actividad. Esta opción solo se puede utilizar si se selecciona la opción **[!UICONTROL Generate all segments in the same transition]**.

   ![](assets/wkf_segment_new_segment.png)

1. Abra la vista de detalles del segmento para acceder a las opciones de configuración de este último. Para ello, marque la casilla correspondiente en la lista de segmentos de la actividad y, a continuación, seleccione ![](assets/wkf_segment_parameters_24px.png).
1. Si la opción para filtrar la población inicial está marcada, abra la pestaña **[!UICONTROL Filter]** y especifique la población del segmento. Los filtros se basan en la dimensión de filtrado seleccionada en el paso 4. Consulte la sección [Edición de consultas](../../automating/using/editing-queries.md) para obtener más información sobre el filtrado de población.

   Si la segmentación se realiza en un recurso temporal, el recuento y la previsualización de la población no estarán disponibles en esta pestaña.

1. Si la opción para limitar el tamaño del segmento está activada, abra la pestaña **[!UICONTROL Limitation]**.

   En primer lugar, seleccione el **[!UICONTROL Type of limit]** que desee usar:

   * **[!UICONTROL Random sampling]**: la población del segmento se selecciona aleatoriamente teniendo en cuenta la configuración de la pestaña **[!UICONTROL Filter]** en caso necesario.
   * **[!UICONTROL Ordered sampling]**: la población del segmento se selecciona de forma ordenada. Por lo tanto, debe especificar las columnas que se deben tener en cuenta y el tipo de clasificación que aplicar. Por ejemplo, si selecciona el campo **Edad** como columna de ordenación al aplicar **[!UICONTROL Descending sort]** y establecer un límite de 100, solo se conservarán los perfiles de las 100 personas más mayores.

   Ahora, especifique el **[!UICONTROL Limit]** del tamaño del segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**: especifique el tamaño del segmento utilizando un porcentaje de la población inicial de la actividad.
   * **[!UICONTROL Maximum size]**: especifique un número máximo de miembros para la población del segmento.
   * **[!UICONTROL By data grouping]**: puede limitar la población del segmento según los valores de un campo específico de la población entrante. Seleccione el campo para la agrupación y, a continuación, especifique los valores que se utilizarán.
   * **[!UICONTROL By data grouping (as a %)]**: puede limitar la población del segmento según los valores de un campo de población entrante específico mediante un porcentaje. Seleccione el campo al que aplicar la agrupación y, a continuación, especifique los valores que se utilizarán.

      >[!NOTE]
      >
      >Se pueden usar distintas limitaciones para cada valor. Por ejemplo, puede especificar una agrupación para el campo **[!UICONTROL Gender]**, y limitar la población con miembros **[!UICONTROL Male]** a 10 personas y la población con miembros **[!UICONTROL Female]** a 30 personas. Si utiliza varios campos de agrupación de datos, todas las agrupaciones deben tener el mismo tamaño.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme la configuración de su segmento.
1. Añada tantos segmentos como sea necesario mediante la repetición de los pasos 6 a 10 de este procedimiento.
1. Si es necesario, edite los parámetros en la pestaña **[!UICONTROL Advanced options]**:

   * Seleccione la opción **[!UICONTROL Enable overlapping of outbound populations]** si desea que un miembro de la población entrante pertenezca a varios segmentos a la vez. La población saliente de la actividad puede superar la población entrante.
   * Marque la opción **[!UICONTROL Concatenate the code of each segment]** si la población entrante ya ha recibido un código de segmento que desee conservar. El código de segmento especificado en la actividad se agregará al código de segmento inicial.
   * Seleccione la opción **[!UICONTROL Generate complement]** si quiere utilizar la población restante. Consulte [Caso de uso: Creación de envíos con un complemento](../../automating/using/workflow-created-query-with-complement.md).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

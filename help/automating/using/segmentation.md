---
title: Segmentación
seo-title: Segmentación
description: Segmentación
seo-description: La actividad de segmentación permite crear uno o varios segmentos a partir de una población calculada por actividades colocadas anteriormente en el flujo de trabajo.
page-status-flag: no activado nunca
uuid: 77796 f 18-cad 5-4 e 7 a -9 d 7 b -4 ed 0 dd 8943 bf
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 0 ccd 9 d 02-772 e -406 b -874 a -5381 dd 0 c 8709
context-tags: segmentación, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

**[!UICONTROL Segmentation]** La actividad permite crear uno o varios segmentos a partir de una población calculada por actividades colocadas anteriormente en el flujo de trabajo. Al finalizar la actividad, pueden procesarse en una sola transición o en distintas transiciones.

>[!NOTE]
>
>De forma predeterminada, un miembro de la población entrante sólo puede pertenecer a un único segmento. Los filtros se aplican según el orden de los segmentos de la actividad.

## Context of use {#context-of-use}

The **[!UICONTROL Segmentation]** activity is generally placed after targeting activities (query, intersection, union, exclusion, etc.) para definir la población estándar en base a la cual se forman los segmentos.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Segmentation]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** si la segmentación se realiza en los datos que ya existen en la base de datos. Select the **[!UICONTROL Filtering dimension]** depending on the data that you want to segment. By default, segmentation is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** si la segmentación se realiza en los datos temporales del flujo de trabajo: seleccione la **[!UICONTROL Targeted set]** que contiene los datos al segmento. Este caso de uso se puede encontrar después de importar un archivo o si se han enriquecido los datos de la base de datos.

1. Seleccione el tipo de transición saliente que desee utilizar:

   * **[!UICONTROL Generate one transition per segment]**: Se agrega una transición saliente para cada segmento configurado al final de la actividad.
   * **[!UICONTROL Generate all segments in one transition]**: todos los segmentos configurados se regeneran en una única transición saliente. Especifique la etiqueta de transición. Los miembros de cada segmento mantienen el código de segmento asignado a ellos.

1. Add a segment by using the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button and specify the standard properties:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: El segmento solo se habilitará si se recuperan los datos.
   * **[!UICONTROL Filter initial population (query)]**: permite filtrar la población de este segmento.
   * **[!UICONTROL Limit segment population]**: permite limitar el tamaño del segmento.
   * **[!UICONTROL Filter and limit segment population]**: permite filtrar la población de segmentos y limitar su tamaño.
   * **[!UICONTROL Label]**: etiqueta de segmento.
   * **[!UICONTROL Segment code]**: código asignado a la población de segmentos. El código de segmento se puede personalizar usando variables estándar de expresión y eventos (consulte [Personalización de actividades con variables de eventos](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).
   * **[!UICONTROL Exclude segment from population]**: permite excluir el segmento especificado de la población saliente de la actividad. This option can only be used if the **[!UICONTROL Generate all segments in the same transition]** option is selected.
   ![](assets/wkf_segment_new_segment.png)

1. Abra la vista de detalles del segmento para acceder a las opciones de configuración de esta última. To do this, check the relevant box in the activity's segment list, then select ![](assets/wkf_segment_parameters_24px.png).
1. If the option to filter the initial population is checked, open the **[!UICONTROL Filter]** tab and specify your segment's population. Los filtros se basan en la dimensión de filtrado seleccionada en el paso 4. Consult the [Query editing](../../automating/using/editing-queries.md) section for further information on population filtering.

   Si la segmentación se realiza en un recurso temporal, el recuento y la vista previa de la población no están disponibles en esta ficha.

1. If the option to limit the segment size is checked, open the **[!UICONTROL Limitation]** tab.

   First, select the **[!UICONTROL Type of limit]** that you would like to use:

   * **[!UICONTROL Random sampling]**: La población de segmentos está seleccionada aleatoriamente teniendo en cuenta la configuración de **[!UICONTROL Filter]** la ficha, si es necesario.
   * **[!UICONTROL Ordered sampling]**: la población de segmentos está seleccionada de forma ordenada. En consecuencia, debe especificar las columnas que se deben tener en cuenta y el tipo de ordenación que se aplicará. For example, if you select the **Age** field as the sort column while applying a **[!UICONTROL Descending sort]** and setting a limit of 100, only the profiles of the top 100 oldest people will be kept.
   Now specify the size **[!UICONTROL Limit]** of the segment:

   * **[!UICONTROL Size (as a % of the initial population)]**: especifique el tamaño del segmento utilizando un porcentaje de la población inicial de la actividad.
   * **[!UICONTROL Maximum size]**: especifique un número máximo de miembros para la población de segmentos.
   * **[!UICONTROL By data grouping]**: puede limitar la población de segmentos según los valores de un campo específico de la población entrante. Seleccione el campo para agrupar y, a continuación, especifique los valores que se utilizarán.
   * **[!UICONTROL By data grouping (as a %)]**: puede limitar la población de segmentos según los valores de un campo de población entrante específico empleando un porcentaje. Seleccione el campo para aplicar la agrupación y, a continuación, especifique los valores que se utilizarán.

      >[!NOTE]
      >
      >Se pueden usar diferentes limitaciones para cada valor. For example, you can specify a grouping for the **[!UICONTROL Gender]** field and limit the population with **[!UICONTROL Male]** members to 10 and the population with **[!UICONTROL Female]** members to 30 people. Si utiliza varios campos de agrupación de datos, todas las agrupaciones tienen que tener el mismo tamaño.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme la configuración del segmento.
1. Agregue tantos segmentos como sea necesario siguiendo los pasos del 6 al 10 de este procedimiento.
1. If necessary, edit the parameters in the **[!UICONTROL Advanced options]** tab:

   * Check the **[!UICONTROL Enable overlapping of outbound populations]** option if you want a member of the inbound population to belong to several segments at the same time. La población saliente de la actividad puede superar la población entrante.
   * Check the **[!UICONTROL Concatenate the code of each segment]** option if the inbound population has already been assigned a segment code that you want to keep. El código de segmento especificado en la actividad se agregará al código de segmento inicial.
   * Check the **[!UICONTROL Generate complement]** option if you would like to exploit the remaining population.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

El siguiente ejemplo muestra una segmentación de perfiles de base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico para cada grupo de edad. Dado que este flujo de trabajo forma parte de una campaña de prueba, cada segmento solo puede contener un máximo de 100 perfiles seleccionados aleatoriamente para usar audiencias limitadas y representativas al mismo tiempo.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo consta de los siguientes elementos:

* **[!UICONTROL Scheduler]** Una actividad para especificar la fecha de ejecución del flujo de trabajo. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* **[!UICONTROL Query]** Actividad que segmenta perfiles de personas cuyo cumpleaños y dirección de correo electrónico han sido ingresados. Refer to the [Query](../../automating/using/query.md) section.
* **[!UICONTROL Segmentation]** Una actividad para crear 3 segmentos divididos en transiciones salientes diferentes: 18 a 25 años, 26 a 32 años anterior y perfiles anteriores a 32 años. Los segmentos se definen según los parámetros siguientes:

   ![](assets/wkf_segment_example_3.png)

   * Filtro de edad para definir el grupo de edad del segmento

      ![](assets/wkf_segment_new_segment.png)

   * A **[!UICONTROL Random sampling]** type limit that is linked to a **[!UICONTROL Maximum size]** limit of 100

      ![](assets/wkf_segment_example_1.png)

* **[!UICONTROL Email delivery]** Una actividad por segmento. Refer to the [Email delivery](../../automating/using/email-delivery.md) section.


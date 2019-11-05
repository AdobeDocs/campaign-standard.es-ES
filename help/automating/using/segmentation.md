---
title: Segmentación
description: La actividad Segmentación permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo.
page-status-flag: nunca activado
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentación,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Segmentación{#segmentation}

## Descripción {#description}

![](assets/segmentation.png)

La **[!UICONTROL Segmentation]** actividad permite crear uno o varios segmentos a partir de una población calculada por actividades ubicadas anteriormente en el flujo de trabajo. Al final de la actividad, se pueden procesar en una única transición o en distintas transiciones.

>[!NOTE]
>
>De forma predeterminada, un miembro de la población entrante solo puede pertenecer a un solo segmento. Los filtros se aplican según el orden de los segmentos en la actividad.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Segmentation]** actividad generalmente se coloca después de las actividades de segmentación (consulta, intersección, unión, exclusión, etc.) para definir la población estándar basada en la forma de los segmentos.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Segmentation]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione el **[!UICONTROL Resource type]** modo en que se debe realizar la segmentación:

   * **[!UICONTROL Database resource]** si la segmentación se realiza con datos que ya existen en la base de datos. Seleccione el **[!UICONTROL Filtering dimension]** informe en función de los datos que desee segmentar. De forma predeterminada, la segmentación se realiza en los **perfiles**.
   * **[!UICONTROL Temporary resource]** si la segmentación se realiza en los datos temporales del flujo de trabajo: seleccione el **[!UICONTROL Targeted set]** que contiene los datos que se van a segmentar. Este caso de uso se puede encontrar después de importar un archivo o si los datos de la base de datos se enriquecieron.

1. Seleccione el tipo de transición de salida que desee utilizar:

   * **[!UICONTROL Generate one transition per segment]**:: se agrega una transición de salida para cada segmento configurado al final de la actividad.
   * **[!UICONTROL Generate all segments in one transition]**:: todos los segmentos configurados se reagrupan en una única transición saliente. Especifique la etiqueta de transición. Los miembros de cada segmento mantienen el código de segmento que se les ha asignado.

1. Agregue un segmento mediante el botón ![](assets/add_darkgrey-24px.png) o **[!UICONTROL Add an element]** y especifique las propiedades estándar:

   * **[!UICONTROL Do not activate the transition if the population is empty]**:: el segmento solo se habilitará si se recuperan datos.
   * **[!UICONTROL Filter initial population (query)]**:: permite filtrar la población de este segmento.
   * **[!UICONTROL Limit segment population]**:: permite limitar el tamaño del segmento.
   * **[!UICONTROL Filter and limit segment population]**:: permite filtrar la población de segmentos y limitar su tamaño.
   * **[!UICONTROL Label]**:: etiqueta de segmento.
   * **[!UICONTROL Segment code]**:: código asignado a la población de segmentos.El código de segmento se puede personalizar mediante una expresión estándar y variables de eventos (consulte [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)de eventos).
   * **[!UICONTROL Exclude segment from population]**:: permite excluir el segmento especificado de la población saliente de la actividad. Esta opción solo se puede utilizar si se selecciona la **[!UICONTROL Generate all segments in the same transition]** opción.
   ![](assets/wkf_segment_new_segment.png)

1. Abra la vista de detalles del segmento para acceder a las opciones de configuración de este último. Para ello, marque la casilla correspondiente en la lista de segmentos de la actividad y, a continuación, seleccione ![](assets/wkf_segment_parameters_24px.png).
1. Si la opción para filtrar la población inicial está marcada, abra la **[!UICONTROL Filter]** ficha y especifique la población del segmento. Los filtros se basan en la dimensión de filtrado seleccionada en el paso 4. Consulte la sección de edición [de](../../automating/using/editing-queries.md) consultas para obtener más información sobre el filtrado de población.

   Si la segmentación se realiza en un recurso temporal, el recuento y la vista previa de la población no estarán disponibles en esta ficha.

1. Si la opción para limitar el tamaño del segmento está activada, abra la **[!UICONTROL Limitation]** ficha.

   En primer lugar, seleccione el **[!UICONTROL Type of limit]** que desee utilizar:

   * **[!UICONTROL Random sampling]**:: la población de segmentos se selecciona al azar teniendo en cuenta la configuración de la **[!UICONTROL Filter]** ficha, si es necesario.
   * **[!UICONTROL Ordered sampling]**:: la población de segmentos se selecciona de forma ordenada. Por lo tanto, debe especificar las columnas que se deben tener en cuenta y el tipo de clasificación que se debe aplicar. Por ejemplo, si selecciona el campo **Edad** como columna de clasificación al aplicar un **[!UICONTROL Descending sort]** y establecer un límite de 100, solo se conservarán los perfiles de las 100 personas más antiguas que más se encuentren.
   Ahora especifique el tamaño **[!UICONTROL Limit]** del segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**:: especifique el tamaño del segmento utilizando un porcentaje de la población inicial de la actividad.
   * **[!UICONTROL Maximum size]**:: especifique un número máximo de miembros para la población de segmentos.
   * **[!UICONTROL By data grouping]**:: puede limitar la población de segmentos según los valores de un campo específico de la población entrante. Seleccione el campo para la agrupación y, a continuación, especifique los valores que se utilizarán.
   * **[!UICONTROL By data grouping (as a %)]**:: puede limitar la población de segmentos según los valores de un campo de población entrante específico mediante un porcentaje. Seleccione el campo para aplicar la agrupación y, a continuación, especifique los valores que se utilizarán.

      >[!NOTE]
      >
      >Se pueden usar distintas limitaciones para cada valor. Por ejemplo, puede especificar una agrupación para el **[!UICONTROL Gender]** campo y limitar la población con **[!UICONTROL Male]** miembros a 10 y la población con **[!UICONTROL Female]** miembros a 30 personas. Si utiliza varios campos de agrupación de datos, todas las agrupaciones deben tener el mismo tamaño.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme la configuración del segmento.
1. Agregue tantos segmentos como sea necesario repitiendo los pasos 6 a 10 de este procedimiento.
1. Si es necesario, edite los parámetros en la **[!UICONTROL Advanced options]** ficha:

   * Seleccione la **[!UICONTROL Enable overlapping of outbound populations]** opción si desea que un miembro de la población entrante pertenezca a varios segmentos al mismo tiempo. La población saliente de la actividad puede superar la población entrante.
   * Marque la **[!UICONTROL Concatenate the code of each segment]** opción si ya se ha asignado a la población entrante un código de segmento que desee conservar. El código de segmento especificado en la actividad se agregará al código de segmento inicial.
   * Seleccione la **[!UICONTROL Generate complement]** opción si desea explotar la población restante.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra una segmentación de los perfiles de base de datos según su grupo de edad. El objetivo del flujo de trabajo es enviar un correo electrónico específico para cada grupo de edad. Teniendo en cuenta que este flujo de trabajo es parte de una campaña de prueba, cada segmento solo puede contener un máximo de 100 perfiles seleccionados al azar para usar audiencias limitadas y representativas al mismo tiempo.

![](assets/wkf_segment_example_4.png)

El flujo de trabajo se compone de los siguientes elementos:

* Una **[!UICONTROL Scheduler]** actividad para especificar la fecha de ejecución del flujo de trabajo. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* Una **[!UICONTROL Query]** actividad para segmentar perfiles de personas cuyo cumpleaños y dirección de correo electrónico se han introducido. Refer to the [Query](../../automating/using/query.md) section.
* Una **[!UICONTROL Segmentation]** actividad para crear 3 segmentos divididos en distintas transiciones de salida: De 18 a 25 años, de 26 a 32 años y perfiles de más de 32 años. Los segmentos se definen según los siguientes parámetros:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro en la edad para definir el grupo de edad del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Límite de **[!UICONTROL Random sampling]** tipo vinculado a un **[!UICONTROL Maximum size]** límite de 100

      ![](assets/wkf_segment_example_1.png)

* Una **[!UICONTROL Email delivery]** actividad por segmento. Consulte la sección Envío [de](../../automating/using/email-delivery.md) correo electrónico.


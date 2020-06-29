---
title: Consulta
description: La actividad de Consulta permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 1%

---


# Consulta{#query}

## Descripción {#description}

![](assets/query.png)

La **[!UICONTROL Query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta de edición de consultas. Esta herramienta se detalla en una sección [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

**Temas relacionados:**

* [Ejemplos de consultas](../../automating/using/query-samples.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía un nuevo envío a los no abridores](../../automating/using/workflow-cross-channel-retargeting.md)

## Contexto de uso {#context-of-use}

La **[!UICONTROL Query]** actividad se puede utilizar para varios tipos de usos:

* Segmentación de individuos para definir el destinatario de un mensaje, audiencia, etc.
* Enriquecimiento de datos de toda la tabla de la base de datos de Adobe Campaign.
* Exportación de datos.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Query]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen. De forma predeterminada, la actividad está preconfigurada para buscar perfiles.
1. Si desea ejecutar una consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y seleccione una **[!UICONTROL Resource]** y una **[!UICONTROL Targeting dimension]**.

   El **[!UICONTROL Resource]** permite refinar los filtros mostrados en la paleta, mientras que el **[!UICONTROL Targeting dimension]**, contextual con respecto al recurso seleccionado, corresponde al tipo de población que desea obtener (perfiles identificados, envíos, datos vinculados al recurso seleccionado, etc.).

   Para obtener más información sobre esto, consulte [Dimensiones de segmentación y recursos](#targeting-dimensions-and-resources).

1. En la **[!UICONTROL Target]** ficha, ejecute la consulta definiendo y combinando reglas.
1. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En particular, puede agregar datos de las tablas de la base de datos de Adobe Campaign vinculadas a la dimensión de segmentación de la consulta. Consulte la sección [Enriquecimiento de datos](#enriching-data) .

   >[!NOTE]
   >
   >De forma predeterminada, la **[!UICONTROL Remove duplicate rows (DISTINCT)]** opción está marcada en la **[!UICONTROL Advanced options]** ficha **[!UICONTROL Additional data]** de la consulta. Si la **[!UICONTROL Query]** actividad contiene muchos (de 100) datos adicionales definidos, se recomienda desactivar esta opción por motivos de rendimiento. Tenga en cuenta que desmarcar esta opción puede resultar en duplicados, según los datos consultados.

1. En la **[!UICONTROL Transition]** ficha, la **[!UICONTROL Enable an outbound transition]** opción le permite agregar una transición saliente después de la actividad de consulta, aunque no recupere datos.

   El código de segmento de la transición saliente se puede personalizar mediante una expresión estándar y variables de eventos (consulte [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)de eventos).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Dimensiones de segmentación y recursos {#targeting-dimensions-and-resources}

Las Dimensiones de segmentación y los recursos permiten definir en qué elementos se basará una consulta para determinar el destinatario de un envío.

Las Dimensiones de segmentación se definen en asignaciones de destino. Para obtener más información, consulte [esta sección](../../administration/using/target-mappings-in-campaign.md).

La Dimensión de segmentación y los recursos se definen al crear un flujo de trabajo, en la **[!UICONTROL Properties]** ficha de una actividad de Consulta.

>[!NOTE]
>
>La dimensión de segmentación también se puede definir al crear una audiencia (consulte [esta sección](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Las Dimensiones de segmentación y los recursos están vinculados. Por lo tanto, las dimensiones de segmentación disponibles dependen del recurso seleccionado.

Por ejemplo, para el recurso **[!UICONTROL Profiles (profile)]**, estarán disponibles las siguientes dimensiones de segmentación:

![](assets/targeting_dimension2.png)

Mientras que para **[!UICONTROL Deliveries (delivery)]**, la lista contendrá las siguientes dimensiones de segmentación:

![](assets/targeting_dimension3.png)

Una vez que se han especificado la dimensión de segmentación y el recurso, hay disponibles diferentes filtros en la consulta.

Ejemplo de filtros disponibles para el **[!UICONTROL Profiles (profile)]** recurso:

![](assets/targeting_dimension4.png)

Ejemplo de filtros disponibles para el **[!UICONTROL Deliveries (delivery)]** recurso:

![](assets/targeting_dimension5.png)

De forma predeterminada, la dimensión de segmentación y el recurso se configuran en perfiles de destinatario. Sin embargo, puede resultar útil utilizar un recurso diferente de la dimensión de segmentación si desea buscar un registro específico en una tabla distante.

Para obtener más información sobre este caso de uso: [Uso de recursos diferentes de dimensiones de segmentación](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Enriquecimiento de datos {#enriching-data}

La **[!UICONTROL Additional data]** ficha de las actividades **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** y **[!UICONTROL Enrichment]** permite enriquecer los datos dirigidos y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se pueden utilizar. En particular, puede agregar:

* Datos simples
* Acumulados
* Colecciones

En el caso de los agregados y las colecciones, **[!UICONTROL Alias]** se define automáticamente una variable para proporcionar un ID técnico a una expresión compleja. Este alias, que debe ser único, permite que los agregados y las colecciones se encuentren fácilmente posteriormente. Puede modificarla para darle un nombre fácilmente reconocible.

>[!NOTE]
>
>Los alias deben respetar las siguientes reglas de sintaxis: Sólo se autorizan los caracteres alfanuméricos y los caracteres &quot;_&quot;. Los alias distinguen entre mayúsculas y minúsculas. El alias debe tener un inicio con el carácter &quot;@&quot;. El carácter que sigue inmediatamente a &quot;@&quot; no debe ser numérico. Por ejemplo: @myAlias_1 y @_1Alias son correctos; mientras que @myAlias#1 y @1Alias son incorrectos.

Después de agregar cualquier dato adicional, puede aplicar un nivel de filtro adicional a los datos objetivo inicial creando condiciones basadas en los datos adicionales definidos.

>[!NOTE]
>
>De forma predeterminada, la **[!UICONTROL Remove duplicate rows (DISTINCT)]** opción está marcada en la **[!UICONTROL Advanced options]** ficha **[!UICONTROL Additional data]** de la consulta. Si la **[!UICONTROL Query]** actividad contiene muchos (de 100) datos adicionales definidos, se recomienda desactivar esta opción por motivos de rendimiento. Tenga en cuenta que desmarcar esta opción puede resultar en duplicados, según los datos consultados.

En [esta sección](../../automating/using/personalizing-email-with-additional-data.md)se presenta un caso de uso sobre cómo personalizar un correo electrónico con datos adicionales.

### Añadir un campo simple {#adding-a-simple-field}

Al agregar un campo simple como datos adicionales, ese campo se vuelve directamente visible en la transición de salida de la actividad. Esto permite al usuario comprobar, por ejemplo, que los datos de la consulta son los datos deseados.

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, en el **[!UICONTROL Expression]** campo, seleccione uno de los campos disponibles directamente en la dimensión de segmentación o en una de las dimensiones vinculadas. Puede editar expresiones y utilizar funciones o cálculos simples (excepto agregados) desde los campos de dimensión.

   Se **[!UICONTROL Alias]** crea automáticamente si edita una expresión que no es una ruta XPATH simple (por ejemplo: &quot;Year(&lt;@bornDate>)&quot;). Si lo desea, puede modificarlo. Si sólo selecciona un campo (por ejemplo: &quot;@age&quot;), no necesita definir un **[!UICONTROL Alias]**.

1. Seleccione **[!UICONTROL Add]** para confirmar la adición del campo a los datos adicionales. Cuando se ejecute la consulta, una columna adicional correspondiente al campo agregado estará presente en la transición saliente de la actividad.

![](assets/enrichment_add_simple_field.png)

### Añadir un acumulado {#adding-an-aggregate}

Los agregados permiten calcular valores a partir de los campos de la dimensión de segmentación o de los campos de dimensiones vinculados a la dimensión de segmentación. Por ejemplo: la cantidad promedio comprada por un perfil.
Cuando se utiliza acumulado con consulta, su función puede volver a cero, lo que se considera como NULA. Utilice la **[!UICONTROL Output filtering]** ficha de la consulta para filtrar el valor agregado:

* si desea valores cero, debe filtrar **[!UICONTROL is null]**.
* si no desea que los valores cero se filtren en **[!UICONTROL is not null]**.

Tenga en cuenta que si necesita aplicar la ordenación en el acumulado, debe filtrar los valores cero o bien el valor NULL aparecerá como el número bueno.

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, seleccione la colección que desee utilizar para crear el acumulado en el **[!UICONTROL Expression]** campo.

   Se **[!UICONTROL Alias]** crea automáticamente un archivo. Si lo desea, puede modificarlo volviendo a la ficha de la consulta **[!UICONTROL Additional data]** .

   Se abre la ventana de definición acumulada.

1. Defina un acumulado desde la **[!UICONTROL Data]** ficha. Según el tipo de acumulado seleccionado, solo los elementos cuyos datos son compatibles están disponibles en el **[!UICONTROL Expression]** campo. Por ejemplo, una suma solo se puede calcular con datos numéricos.

   ![](assets/enrichment_add_aggregate.png)

   Puede agregar varios agregados para los campos de la colección seleccionada. Asegúrese de definir etiquetas explícitas para distinguir las distintas columnas en los detalles de los datos salientes de la actividad.

   También puede cambiar los alias que se definen automáticamente para cada acumulado.

   ![](assets/enrichment_add_aggregate2.png)

1. Si es necesario, puede agregar un filtro para limitar los datos que se tienen en cuenta.

   Consulte la sección [Filtrado de datos](#filtering-added-data) agregados.

1. Seleccione **[!UICONTROL Confirm]** para agregar agregados.

>[!NOTE]
>
>No se puede crear una expresión que contenga un acumulado directamente desde el **[!UICONTROL Expression]** campo de la **[!UICONTROL New additional data]** ventana.

### Añadir una colección {#adding-a-collection}

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, seleccione la colección que desee agregar al **[!UICONTROL Expression]** campo. Se **[!UICONTROL Alias]** crea automáticamente un archivo. Si lo desea, puede modificarlo volviendo a la ficha de la consulta **[!UICONTROL Additional data]** .
1. Seleccione **[!UICONTROL Add]**. Se abre una nueva ventana, que le permite refinar los datos de recopilación que desea mostrar.
1. En la **[!UICONTROL Parameters]** ficha, seleccione **[!UICONTROL Collection]** y defina el número de líneas de la colección que desea agregar. Por ejemplo, si desea obtener las tres compras más recientes realizadas por cada perfil, introduzca &quot;3&quot; en el **[!UICONTROL Number of lines to return]** campo.

   >[!NOTE]
   >
   >Debe especificar un número mayor o igual que 1.

1. En la **[!UICONTROL Data]** ficha, defina los campos de la colección que desea mostrar para cada línea.

   ![](assets/enrichment_add_collection.png)

1. Si lo desea, puede agregar un filtro para limitar las líneas de recopilación que se tienen en cuenta.

   Consulte la sección [Filtrado de datos](#filtering-added-data) agregados.

1. Si lo desea, puede definir una clasificación de datos.

   Por ejemplo, si ha seleccionado 3 líneas para que se devuelvan en la **[!UICONTROL Parameters]** ficha y desea determinar las tres compras más recientes, puede definir un orden descendente en el campo &quot;fecha&quot; de la colección que corresponde a las transacciones.

1. Refer to the [Sorting additional data](#sorting-additional-data) section.
1. Seleccione **[!UICONTROL Confirm]** para agregar la colección.

### Filtrado de datos agregados {#filtering-added-data}

Cuando se agrega una colección acumulada o una colección, puede especificar un filtro adicional para limitar los datos que desea mostrar.

Por ejemplo, si sólo desea procesar las líneas de recopilación de transacciones con importes de 50 dólares o más, puede agregar una condición en el campo correspondiente al importe de la transacción desde la **[!UICONTROL Filter]** ficha.

![](assets/enrichment_filter_data.png)

### Ordenar datos adicionales {#sorting-additional-data}

Al agregar un acumulado o una colección a los datos de una consulta, puede especificar si desea aplicar una ordenación (ya sea ascendente o descendente) en función del valor del campo o de la expresión definida.

Por ejemplo, si desea guardar únicamente la transacción que un perfil realizó más recientemente, introduzca &quot;1&quot; en el **[!UICONTROL Number of lines to return]** campo de la **[!UICONTROL Parameters]** ficha y aplique un orden descendente en el campo correspondiente a la fecha de transacción mediante la **[!UICONTROL Sort]** ficha.

![](assets/enrichment_sort_data.png)

### Filtrado de datos objetivo según datos adicionales {#filtering-the-targeted-data-according-to-additional-data}

Una vez que haya agregado datos adicionales, aparecerá una nueva **[!UICONTROL Output filtering]** ficha en la **[!UICONTROL Query]**. Esta ficha le permite aplicar un filtro adicional a los datos que inicialmente están en la **[!UICONTROL Target]** ficha, teniendo en cuenta los datos agregados.

Por ejemplo, si ha segmentado todos los perfiles que han realizado al menos una transacción y se ha agregado al cálculo acumulado el importe de transacción promedio realizado para cada perfil, puede refinar la población calculada inicialmente con esta media. **[!UICONTROL Additional data]**

Para ello, en la **[!UICONTROL Output filtering]** ficha, simplemente agregue una condición a estos datos adicionales.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)

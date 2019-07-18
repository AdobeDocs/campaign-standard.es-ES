---
title: Consulta
seo-title: Consulta
description: Consulta
seo-description: La actividad Consulta permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
page-status-flag: no activado nunca
uuid: b 3 c 629 fa -370 e -481 c-b 347-fcf 9 f 5 a 5 e 847
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 8 d 46 ce 28-0101-4 f 13-865 a -2208 ed 6 d 6139
context-tags: query, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Query{#query}

## Description {#description}

![](assets/query.png)

The **[!UICONTROL Query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta Editor de consultas. This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

The **[!UICONTROL Query]** activity can be used for various types of uses:

* Segmentar a personas para definir el objetivo de un mensaje, audiencia, etc.
* Enriquecimiento de datos de toda la tabla de base de datos de Adobe Campaign.
* Exportación de datos.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear. De forma predeterminada, la actividad está preconfigurada para buscar perfiles.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

   For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)

1. In the **[!UICONTROL Target]** tab, run your query by defining and combining rules.
1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En concreto, puede agregar datos de las tablas de base de datos de Adobe Campaign vinculadas a la dimensión de segmentación de la consulta. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. If the **[!UICONTROL Query]** activity contains many (from 100) additional data defined, it is recommended to uncheck this option, for performance reasons. Tenga en cuenta que si desactiva esta opción, obtendrá duplicados en función de la consulta de datos.

1. In the **[!UICONTROL Transition]** tab, the **[!UICONTROL Enable an outbound transition]** option lets you add an outbound transition after the query activity, even if it retrieves no data.

   The outbound transition's segment code can be personalized using a standard expression and events variables (see [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Targeting dimensions and resources {#targeting-dimensions-and-resources}

Las dimensiones y los recursos de objetivos le permiten definir en qué elementos se basará una consulta para determinar el objetivo de una entrega.

Las dimensiones de objetivo se definen en asignaciones de destino. For more on this, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

### Defining the targeting dimension and resource of a query {#defining-the-targeting-dimension-and-resource-of-a-query}

Targeting dimension and resources are defined when creating a workflow, in the **[!UICONTROL Properties]** tab of a Query activity.

>[!NOTE]
>
>The targeting dimension can also be defined when creating an audience (see [this section](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Las dimensiones y los recursos de objetivos están vinculados. Por lo tanto, las dimensiones de objetivo disponibles dependen del recurso seleccionado.

For example, for the Resource **[!UICONTROL Profiles (profile)]**, the following targeting dimensions will be available:

![](assets/targeting_dimension2.png)

While for **[!UICONTROL Deliveries (delivery)]**, the list will contain the following targeting dimensions:

![](assets/targeting_dimension3.png)

Una vez especificado los medios y la dimensión de segmentación, en la consulta se encuentran disponibles diferentes filtros.

Example of available filters for the **[!UICONTROL Profiles (profile)]** resource:

![](assets/targeting_dimension4.png)

Example of available filters for the **[!UICONTROL Deliveries (delivery)]** resource:

![](assets/targeting_dimension5.png)

### Using resources different from targeting dimensions {#using-resources-different-from-targeting-dimensions}

De forma predeterminada, la dimensión y el recurso de segmentación se definen para destinar los perfiles.

Sin embargo, puede resultar útil utilizar otro recurso de la dimensión de segmentación si desea buscar un registro específico en una tabla distante.

**Ejemplo 1: identificar los perfiles objetivo de la entrega con la etiqueta "Bienvenido atrás! »**.

* En este caso, queremos segmentar perfiles. We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de entrega. We will therefore set the resource to **[!UICONTROL Delivery logs]**. De este modo, se filtran directamente en la tabla de registro de entrega, lo que ofrece mejores resultados.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Ejemplo 2: identificar perfiles que no fueron dirigidos por la entrega con la etiqueta «Bienvenido hacia atrás! »»**

En el ejemplo anterior, usamos un recurso diferente de la dimensión de objetivo. This operation is only possible if you want to find a record that **is present** in the distant table (delivery logs in our example).

If we want to find a record that **is not present** in the distant table (for example, profiles who were not targeted by a specific delivery), you must use the same resource and targeting dimension, as the record will not be present in the distant table (delivery logs).

* En este caso, queremos segmentar perfiles. We will set the targeting dimension to **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de entrega. No es posible filtrar directamente en los registros de entrega, ya que estamos buscando un registro no presente en la tabla Registros de entrega. We will therefore set the resource to **[!UICONTROL Profile (profile)]** and build our query on the profiles table.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

## Enriching data {#enriching-data}

**[!UICONTROL Additional data]** La ficha y **[!UICONTROL Query]****[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** las actividades permiten enriquecer los datos dirigidos y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se puede utilizar. En particular, puede agregar:

* Datos simples
* Agrega
* Colecciones

For aggregates and collections, an **[!UICONTROL Alias]** is automatically defined to give a technical ID to a complex expression. Este alias, que debe ser único, permite que los agregados y las colecciones se encuentren fácilmente después. Puede modificarlo para darle un nombre reconocible.

>[!NOTE]
>
>Los alias deben respetar las siguientes reglas de sintaxis: Solo se autorizan los caracteres alfanuméricos y los caracteres "_". Los alias distinguen entre mayúsculas y minúsculas. El alias debe comenzar con el carácter " @". El carácter inmediatamente posterior al " @" no debe ser numérico. Por ejemplo: @ Myalias_ 1 y @_ 1 Alias son correctos; mientras @ myalias # 1 y @ 1 Alias son incorrectos.

Después de agregar datos adicionales, puede aplicar un nivel de filtro adicional a los datos inicialmente dirigidos creando condiciones basadas en los datos adicionales definidos.

>[!NOTE]
>
>By default, the **[!UICONTROL Remove duplicate rows (DISTINCT)]** option is checked in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Additional data]** tab of the query. If the **[!UICONTROL Query]** activity contains many (from 100) additional data defined, it is recommended to uncheck this option, for performance reasons. Tenga en cuenta que si desactiva esta opción, obtendrá duplicados en función de la consulta de datos.

### Adding a simple field {#adding-a-simple-field}

Al agregar un campo simple como datos adicionales, ese campo queda directamente visible en la transición saliente de la actividad. Esto permite al usuario comprobar, por ejemplo, que los datos de la consulta son los datos deseados.

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, in the **[!UICONTROL Expression]** field, select one of the fields available directly in the targeting dimension or in one of the linked dimensions. Puede editar expresiones y utilizar funciones o cálculos simples (excepto agregados) de los campos de dimensión.

   An **[!UICONTROL Alias]** is automatically created if you edit an expression that is not a simple XPATH path (for example: "Year(&lt;@birthDate&gt;)"). Si lo desea, puede modificarlo. If you only select one field (for example: "@age"), you do not need to define an **[!UICONTROL Alias]**.

1. Select **[!UICONTROL Add]** to confirm adding the field to the additional data. Cuando se ejecute la consulta, se mostrará una columna adicional correspondiente al campo agregada en la transición saliente de la actividad.

![](assets/enrichment_add_simple_field.png)

### Adding an aggregate {#adding-an-aggregate}

Los agregados permiten calcular los valores a partir de los campos de la dimensión de objetivo o de los campos de dimensiones vinculados a la dimensión de objetivo. Por ejemplo: la cantidad media comprada por un perfil.

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, select the collection that you want to use to create your aggregate in the **[!UICONTROL Expression]** field.

   An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.

   Se abre la ventana de definición agregada.

1. Define an aggregate from the **[!UICONTROL Data]** tab. Depending on the type of aggregate selected, only the elements whose data is compatible are available in the **[!UICONTROL Expression]** field. Por ejemplo, una suma solo se puede calcular con datos numéricos.

   ![](assets/enrichment_add_aggregate.png)

   Puede agregar varios agregados para los campos de la colección seleccionada. Asegúrese de definir etiquetas explícitas para distinguir las distintas columnas en los detalles de los datos salientes de la actividad.

   También puede cambiar los alias que se definen automáticamente para cada conjunto.

   ![](assets/enrichment_add_aggregate2.png)

1. Si es necesario, puede agregar un filtro para limitar los datos tomados en cuenta.

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. Select **[!UICONTROL Confirm]** to add aggregates.

>[!NOTE]
>
>You cannot create an expression containing an aggregate directly from the **[!UICONTROL Expression]** field of the **[!UICONTROL New additional data]** window.

### Adding a collection {#adding-a-collection}

1. From the **[!UICONTROL Additional data]** tab, add a new element.
1. In the window that opens, select the collection that you want to add in the **[!UICONTROL Expression]** field. An **[!UICONTROL Alias]** is created automatically. If you like, you can modify it by going back to the query's **[!UICONTROL Additional data]** tab.
1. Select **[!UICONTROL Add]**. Se abre una ventana nueva que permite refinar los datos de la colección que desee mostrar.
1. In the **[!UICONTROL Parameters]** tab, select **[!UICONTROL Collection]** and define the number of lines of the collection that you want to add. For example, if you want to get the three most recent purchases carried out by each profile, enter "3" in the **[!UICONTROL Number of lines to return]** field.

   >[!NOTE]
   >
   >Debe especificar un número mayor o igual que 1.

1. From the **[!UICONTROL Data]** tab, define the fields of the collection that you want to display for each line.

   ![](assets/enrichment_add_collection.png)

1. Si lo desea, puede agregar un filtro para limitar las líneas de la colección teniendo en cuenta.

   Refer to the [Filtering added data](../../automating/using/query.md#filtering-added-data) section.

1. Si lo desea, puede definir una ordenación de datos.

   For example, if you have selected 3 lines to return in the **[!UICONTROL Parameters]** tab, and you want to determine the three most recent purchases, you can define a descending sort on the "date" field of the collection that corresponds to the transactions.

1. Refer to the [Sorting additional data](../../automating/using/query.md#sorting-additional-data) section.
1. Select **[!UICONTROL Confirm]** to add the collection.

### Filtering added data {#filtering-added-data}

Al agregar un conjunto o una colección, puede especificar un filtro adicional para limitar los datos que desee mostrar.

For example, if you want to only process the collection lines of transactions with amounts of 50 dollars and above, you can add a condition on the field corresponding to the transaction amount from the **[!UICONTROL Filter]** tab.

![](assets/enrichment_filter_data.png)

### Sorting additional data {#sorting-additional-data}

Cuando agrega un conjunto o una colección a los datos de una consulta, puede especificar si desea aplicar una ordenación (ya sea ascendente o descendente) según el valor del campo o la expresión definida.

For example, if you want to save only the transaction that was carried out most recently by a profile, enter "1" in the **[!UICONTROL Number of lines to return]** field of the **[!UICONTROL Parameters]** tab, and apply a descending sort on the field corresponding to the transaction date via the **[!UICONTROL Sort]** tab.

![](assets/enrichment_sort_data.png)

### Filtering the targeted data according to additional data {#filtering-the-targeted-data-according-to-additional-data}

Once you have added additional data, a new **[!UICONTROL Output filtering]** tab appears in the **[!UICONTROL Query]**. This tab allows you to apply an additional filter on the data initially targeted in the **[!UICONTROL Target]** tab, by taking into account the added data.

For example, if you have targeted all of the profiles that carried out at least one transaction and an aggregate calculating the average transaction amount carried out for each profile was added to the **[!UICONTROL Additional data]**, you can refine the population initially calculated using this average.

To do this, in the **[!UICONTROL Output filtering]** tab, simply add a condition on this additional data.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)

### Example: personalizing an email with additional data {#example--personalizing-an-email-with-additional-data}

El siguiente ejemplo ilustra la adición de distintos tipos de datos adicionales a una consulta y su uso como campo de personalización en un mensaje de correo electrónico.

For this example, [custom resources](../../developing/using/data-model-concepts.md) are used:

* The **profile** resource was extended in order to add a field which allows each profile's loyalty points to be saved.
* A **transactions** resource was created and identifies all purchases carried out by the profiles in the database. La fecha, el precio y el producto comprado se guardan para cada transacción.
* A **products** resource was created and references the products available for purchase.

El objetivo es enviar un correo electrónico a los perfiles para los que se haya guardado al menos una transacción. A través de este mensaje de correo electrónico, los clientes recibirán un recordatorio de la última transacción realizada, así como una descripción general de todas sus transacciones: la cantidad de productos comprados, el total invertido, un recordatorio del número total de puntos de lealtad que han acumulado.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/enrichment_example1.png)

1. Add a **[!UICONTROL Query]** activity, which allows you to target the profiles that have carried out at least one transaction.

   ![](assets/enrichment_example2.png)

   From the query's **[!UICONTROL Additional data]** tab, define the different data to be displayed in the final email:

   * The simple field of the **profile** dimension corresponding to the loyalty points. Refer to the [Adding a simple field](../../automating/using/query.md#adding-a-simple-field) section.
   * Dos agregados en función de la colección de transacciones: la cantidad de productos comprados y la cantidad total gastada. You can add them from the **[!UICONTROL Data]** tab of the aggregate configuration window, using the **Count** and **Sum** aggregates. Refer to the [Adding an aggregate](../../automating/using/query.md#adding-an-aggregate) section.
   * Una colección que devuelve la cantidad gastada, la fecha y el producto de la última transacción realizada.

      To do this, you have to add the different fields that you want to display from the **[!UICONTROL Data]** tab of the collection configuration window.

      To return only the most recent transaction, you have to enter "1" for the **[!UICONTROL Number of lines to return]** and apply a descending sort on the **Date** field of the collection from the **[!UICONTROL Sort]** tab.

      Refer to the [Adding a collection](../../automating/using/query.md#adding-a-collection) and [Sorting additional data](../../automating/using/query.md#sorting-additional-data) sections.
   ![](assets/enrichment_example4.png)

   If you would like to check that the data is correctly transferred by the activity's outbound transition, start the workflow for the first time (without the **[!UICONTROL Email delivery]** activity) and open the query's outbound transition.

   ![](assets/enrichment_example5.png)

1. Add an **[!UICONTROL Email delivery]** activity. En el contenido de correo electrónico, inserte los campos de personalización correspondientes a los datos calculados en la consulta. You can find it via the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer.

   ![](assets/enrichment_example3.png)

El flujo de trabajo ya está listo para ejecutarse. Los perfiles objetivo de la consulta recibirán un correo electrónico personalizado con los datos calculados a partir de sus transacciones.

## Query samples {#query-samples}

### Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para dirigirse a hombres entre 18 y 30 años, viviendo en Londres.

![](assets/query_sample_1.png)

### Targeting on email attributes {#targeting-on-email-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para segmentar perfiles con el dominio de dirección de correo electrónico "orange.co.uk".

![](assets/query_sample_emaildomain.png)

El siguiente ejemplo muestra una actividad de consulta configurada para segmentar perfiles cuya dirección de correo electrónico se ha proporcionado.

![](assets/query_sample_emailnotempty.png)

### Targeting profiles whose birthday is today {#targeting-profiles-whose-birthday-is-today}

El siguiente ejemplo muestra una actividad de consulta configurada para segmentar perfiles cuyo cumpleaños es hoy.

1. Drag the **[!UICONTROL Birthday]** filter in your query.

   ![](assets/query_sample_birthday.png)

1. Set the **[!UICONTROL Filter type]** to **[!UICONTROL Relative]** and select **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

### Targeting profiles who opened a specific delivery {#targeting-profiles-who-opened-a-specific-delivery}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles que abrieron la entrega con la etiqueta "Hora de verano".

1. Drag the **[!UICONTROL Opened]** filter in your query.

   ![](assets/query_sample_opened.png)

1. Select the delivery then click **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

### Targeting profiles for whom deliveries failed for a specific reason {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles para los que las entregas fallaron porque su buzón de correo estaba lleno. This query is only available for users with administration rights and belonging to the **[!UICONTROL All (all)]** organizational units (see [this section](../../administration/using/organizational-units.md)).

1. Select the **[!UICONTROL Delivery logs]** resource in order to filter directly in the delivery log table (see [Using resources different from targeting dimensions](../../automating/using/query.md#using-resources-different-from-targeting-dimensions)).

   ![](assets/query_sample_failure1.png)

1. Drag the **[!UICONTROL Nature of failure]** filter in your query.

   ![](assets/query_sample_failure2.png)

1. Seleccione el tipo de error que desea establecer como objetivo. In our case **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

### Targeting profiles not contacted during the last 7 days {#targeting-profiles-not-contacted-during-the-last-7-days}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles que no se han contestado durante los últimos 7 días.

1. Drag the **[!UICONTROL Delivery logs (logs)]** filter in your query.

   ![](assets/query_sample_7days.png)

   Select **[!UICONTROL Does not exist]** in the drop-down list, then drag the **[!UICONTROL Delivery]** filter.

   ![](assets/query_sample_7days1.png)

1. Configure el filtro como se muestra a continuación.

   ![](assets/query_sample_7days2.png)

### Targeting profiles who clicked a specific link {#targeting-profiles-who-clicked-a-specific-link-}

1. Drag the **[!UICONTROL Tracking logs (tracking)]** filter in your query.

   ![](assets/query_sample_trackinglogs.png)

1. Drag the **[!UICONTROL Label (urlLabel)]** filter.

   ![](assets/query_sample_trackinglogs2.png)

1. In the **[!UICONTROL Value]** field, type the label that was defined when inserting the link in the delivery, then confirm.

   ![](assets/query_sample_trackinglogs3.png)


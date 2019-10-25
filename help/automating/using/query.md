---
title: Consulta
seo-title: Consulta
description: Consulta
seo-description: La actividad Consulta le permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
page-status-flag: nunca activado
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: consulta,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Consulta{#query}

## Descripción {#description}

![](assets/query.png)

La **[!UICONTROL Query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta de edición de consultas. Esta herramienta se detalla en una sección [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Query]** actividad se puede utilizar para varios tipos de usos:

* Segmentación de individuos para definir el destino de un mensaje, una audiencia, etc.
* Enriquecimiento de datos de toda la tabla de base de datos de Adobe Campaign.
* Exportación de datos.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Query]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen. De forma predeterminada, la actividad está preconfigurada para buscar perfiles.
1. Si desea ejecutar una consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y seleccione un **[!UICONTROL Resource]** y un **[!UICONTROL Targeting dimension]**.

   El **[!UICONTROL Resource]** permite refinar los filtros mostrados en la paleta, mientras que el **[!UICONTROL Targeting dimension]**, contextual con respecto al recurso seleccionado, corresponde al tipo de población que desea obtener (perfiles identificados, entregas, datos vinculados al recurso seleccionado, etc.).

   Para obtener más información sobre esto, consulte [Segmentación de dimensiones y recursos](#targeting-dimensions-and-resources).

1. En la **[!UICONTROL Target]** ficha, ejecute la consulta definiendo y combinando reglas.
1. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En particular, puede agregar datos de las tablas de base de datos de Adobe Campaign vinculadas a la dimensión de objetivo de la consulta. Consulte la sección [Enriquecimiento de datos](#enriching-data) .

   >[!NOTE]
   >
   >De forma predeterminada, la **[!UICONTROL Remove duplicate rows (DISTINCT)]** opción está marcada en la **[!UICONTROL Advanced options]** ficha **[!UICONTROL Additional data]** de la consulta. Si la **[!UICONTROL Query]** actividad contiene muchos (de 100) datos adicionales definidos, se recomienda desactivar esta opción por motivos de rendimiento. Tenga en cuenta que, al desmarcar esta opción, se pueden obtener duplicados, según los datos consultados.

1. En la **[!UICONTROL Transition]** ficha, la **[!UICONTROL Enable an outbound transition]** opción le permite agregar una transición de salida después de la actividad de consulta, incluso si no recupera ningún dato.

   El código de segmento de la transición de salida se puede personalizar mediante una expresión estándar y variables de eventos (consulte [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)de eventos).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Dimensiones y recursos de objetivo {#targeting-dimensions-and-resources}

Las dimensiones y los recursos de objetivo permiten definir en qué elementos se basará una consulta para determinar el objetivo de una entrega.

Las dimensiones de objetivo se definen en las asignaciones de objetivo. Para obtener más información, consulte [esta sección](../../administration/using/target-mappings-in-campaign.md).

### Definición de la dimensión de objetivo y el recurso de una consulta {#defining-the-targeting-dimension-and-resource-of-a-query}

La dimensión y los recursos de objetivo se definen al crear un flujo de trabajo, en la **[!UICONTROL Properties]** ficha de una actividad de consulta.

>[!NOTE]
>
>La dimensión de objetivo también se puede definir al crear una audiencia (consulte [esta sección](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Las dimensiones y los recursos de objetivos están vinculados. Por lo tanto, las dimensiones de objetivo disponibles dependen del recurso seleccionado.

Por ejemplo, para el recurso **[!UICONTROL Profiles (profile)]**, estarán disponibles las siguientes dimensiones de objetivo:

![](assets/targeting_dimension2.png)

While for **[!UICONTROL Deliveries (delivery)]**, the list will contain the following targeting dimensions:

![](assets/targeting_dimension3.png)

Una vez que se han especificado la dimensión y el recurso de objetivo, hay diferentes filtros disponibles en la consulta.

Ejemplo de filtros disponibles para el **[!UICONTROL Profiles (profile)]** recurso:

![](assets/targeting_dimension4.png)

Ejemplo de filtros disponibles para el **[!UICONTROL Deliveries (delivery)]** recurso:

![](assets/targeting_dimension5.png)

### Uso de recursos diferentes de dimensiones de objetivo {#using-resources-different-from-targeting-dimensions}

De forma predeterminada, la dimensión de objetivo y el recurso se establecen para dirigirse a los perfiles.

Sin embargo, puede resultar útil utilizar un recurso diferente de la dimensión de objetivo si desea buscar un registro específico en una tabla distante.

**Ejemplo 1: identificando perfiles dirigidos por la entrega con la etiqueta "Welcome back !"**.

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de objetivo en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de entrega. Por lo tanto, estableceremos el recurso en **[!UICONTROL Delivery logs]**. De esta manera, estamos filtrando directamente en la tabla del registro de entrega, lo que ofrece mejores resultados.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Ejemplo 2: identificando perfiles que no fueron objetivo de la entrega con la etiqueta "Bienvenido de nuevo!"**

En el ejemplo anterior, se utilizaba un recurso distinto de la dimensión de objetivo. Esta operación solo es posible si desea encontrar un registro que **esté presente** en la tabla distante (en nuestro ejemplo, registros de entrega).

Si queremos encontrar un registro que no **está presente** en la tabla distante (por ejemplo, perfiles que no están segmentados por una entrega específica), debe utilizar la misma dimensión de objetivo y recurso, ya que el registro no estará presente en la tabla distante (registros de entrega).

* En este caso, queremos segmentar perfiles. Estableceremos la dimensión de objetivo en **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar los perfiles seleccionados según la etiqueta de entrega. No es posible filtrar directamente los registros de entrega, ya que estamos buscando un registro que no esté presente en la tabla de registros de entrega. Por lo tanto, estableceremos el recurso **[!UICONTROL Profile (profile)]** y construiremos nuestra consulta en la tabla de perfiles.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)

## Enriquecimiento de datos {#enriching-data}

La **[!UICONTROL Additional data]** ficha de las actividades **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** y **[!UICONTROL Enrichment]** le permite enriquecer los datos dirigidos y transferir estos datos a las siguientes actividades de flujo de trabajo, donde se pueden utilizar. En particular, puede agregar:

* Datos simples
* Acumulados
* Colecciones

En el caso de los agregados y las colecciones, **[!UICONTROL Alias]** se define automáticamente un identificador técnico para proporcionar una expresión compleja. Este alias, que debe ser único, permite que los agregados y las colecciones se encuentren fácilmente posteriormente. Puede modificarla para darle un nombre fácilmente reconocible.

>[!NOTE]
>
>Los alias deben respetar las siguientes reglas de sintaxis: Sólo se autorizan los caracteres alfanuméricos y los caracteres "_". Los alias distinguen entre mayúsculas y minúsculas. El alias debe comenzar con el carácter "@". El carácter que sigue inmediatamente a "@" no debe ser numérico.  Por ejemplo: @myAlias_1 y @_1Alias son correctos; mientras que @myAlias#1 y @1Alias son incorrectos.

Después de agregar cualquier dato adicional, puede aplicar un nivel de filtro adicional a los datos objetivo inicial creando condiciones basadas en los datos adicionales definidos.

>[!NOTE]
>
>De forma predeterminada, la **[!UICONTROL Remove duplicate rows (DISTINCT)]** opción está marcada en la **[!UICONTROL Advanced options]** ficha **[!UICONTROL Additional data]** de la consulta. Si la **[!UICONTROL Query]** actividad contiene muchos (de 100) datos adicionales definidos, se recomienda desactivar esta opción por motivos de rendimiento. Tenga en cuenta que, al desmarcar esta opción, se pueden obtener duplicados, según los datos consultados.

### Adición de un campo simple {#adding-a-simple-field}

Al agregar un campo simple como datos adicionales, ese campo se vuelve directamente visible en la transición de salida de la actividad. Esto permite al usuario comprobar, por ejemplo, que los datos de la consulta son los datos deseados.

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, en el **[!UICONTROL Expression]** campo, seleccione uno de los campos disponibles directamente en la dimensión de objetivo o en una de las dimensiones vinculadas. Puede editar expresiones y utilizar funciones o cálculos simples (excepto agregados) desde los campos de dimensión.

   Se **[!UICONTROL Alias]** crea automáticamente si edita una expresión que no es una ruta XPATH simple (por ejemplo: "Year(&lt;@bornDate&gt;)"). Si lo desea, puede modificarlo. Si sólo selecciona un campo (por ejemplo: "@age"), no necesita definir un **[!UICONTROL Alias]**.

1. Seleccione **[!UICONTROL Add]** para confirmar la adición del campo a los datos adicionales. Cuando se ejecuta la consulta, una columna adicional correspondiente al campo agregado estará presente en la transición de salida de la actividad.

![](assets/enrichment_add_simple_field.png)

### Adición de un agregado {#adding-an-aggregate}

Los agregados permiten calcular valores a partir de campos de la dimensión de objetivo o de campos de dimensiones vinculados a la dimensión de objetivo.  Por ejemplo: la cantidad promedio comprada por un perfil.

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, seleccione la colección que desee utilizar para crear el agregado en el **[!UICONTROL Expression]** campo.

   Se **[!UICONTROL Alias]** crea automáticamente un archivo. Si lo desea, puede modificarla volviendo a la **[!UICONTROL Additional data]** ficha de la consulta.

   Se abre la ventana de definición de agregado.

1. Defina un agregado desde la **[!UICONTROL Data]** ficha. Según el tipo de agregado seleccionado, solo los elementos cuyos datos son compatibles están disponibles en el **[!UICONTROL Expression]** campo. Por ejemplo, una suma solo se puede calcular con datos numéricos.

   ![](assets/enrichment_add_aggregate.png)

   Puede agregar varios agregados para los campos de la colección seleccionada. Asegúrese de definir etiquetas explícitas para distinguir las diferentes columnas en los detalles de los datos de salida de la actividad.

   También puede cambiar los alias que se definen automáticamente para cada agregado.

   ![](assets/enrichment_add_aggregate2.png)

1. Si es necesario, puede agregar un filtro para limitar los datos tomados en cuenta.

   Consulte la sección [Filtrado de datos](#filtering-added-data) agregados.

1. Seleccione **[!UICONTROL Confirm]** para agregar agregados.

>[!NOTE]
>
>No se puede crear una expresión que contenga un agregado directamente desde el **[!UICONTROL Expression]** campo de la **[!UICONTROL New additional data]** ventana.

### Adición de una colección {#adding-a-collection}

1. En la **[!UICONTROL Additional data]** ficha, agregue un nuevo elemento.
1. En la ventana que se abre, seleccione la colección que desee agregar al **[!UICONTROL Expression]** campo. Se **[!UICONTROL Alias]** crea automáticamente un archivo. Si lo desea, puede modificarla volviendo a la **[!UICONTROL Additional data]** ficha de la consulta.
1. Select **[!UICONTROL Add]**. Se abre una nueva ventana, que permite refinar los datos de recopilación que desea mostrar.
1. En la **[!UICONTROL Parameters]** ficha, seleccione **[!UICONTROL Collection]** y defina el número de líneas de la colección que desea agregar. Por ejemplo, si desea que las tres compras más recientes realizadas por cada perfil se realicen, introduzca "3" en el **[!UICONTROL Number of lines to return]** campo.

   >[!NOTE]
   >
   >Debe especificar un número mayor o igual que 1.

1. En la **[!UICONTROL Data]** ficha, defina los campos de la colección que desea mostrar para cada línea.

   ![](assets/enrichment_add_collection.png)

1. Si lo desea, puede agregar un filtro para limitar las líneas de recopilación que se tienen en cuenta.

   Consulte la sección [Filtrado de datos](#filtering-added-data) agregados.

1. Si lo desea, puede definir una clasificación de datos.

   Por ejemplo, si ha seleccionado 3 líneas para que se devuelvan en la **[!UICONTROL Parameters]** ficha y desea determinar las tres compras más recientes, puede definir un orden descendente en el campo "fecha" de la colección que corresponde a las transacciones.

1. Consulte la sección [Ordenar datos](#sorting-additional-data) adicionales.
1. Seleccione **[!UICONTROL Confirm]** para agregar la colección.

### Filtrado de datos agregados {#filtering-added-data}

Al agregar un agregado o una colección, puede especificar un filtro adicional para limitar los datos que desea mostrar.

Por ejemplo, si sólo desea procesar las líneas de recopilación de transacciones con importes de 50 dólares o más, puede agregar una condición en el campo correspondiente al importe de la transacción desde la **[!UICONTROL Filter]** ficha.

![](assets/enrichment_filter_data.png)

### Ordenar datos adicionales {#sorting-additional-data}

Al agregar un agregado o una colección a los datos de una consulta, puede especificar si desea aplicar una ordenación (ya sea ascendente o descendente) basada en el valor del campo o en la expresión definida.

Por ejemplo, si desea guardar únicamente la transacción que un perfil realizó más recientemente, introduzca "1" en el **[!UICONTROL Number of lines to return]** campo de la **[!UICONTROL Parameters]** ficha y aplique un orden descendente en el campo correspondiente a la fecha de transacción mediante la **[!UICONTROL Sort]** ficha.

![](assets/enrichment_sort_data.png)

### Filtrado de datos objetivo según datos adicionales {#filtering-the-targeted-data-according-to-additional-data}

Una vez que haya agregado datos adicionales, aparecerá una nueva **[!UICONTROL Output filtering]** ficha en la **[!UICONTROL Query]**. Esta ficha le permite aplicar un filtro adicional a los datos que inicialmente están en la **[!UICONTROL Target]** ficha, teniendo en cuenta los datos agregados.

Por ejemplo, si se han segmentado todos los perfiles que han realizado al menos una transacción y se ha añadido al perfil un cálculo global del importe de transacción promedio realizado para cada perfil, puede refinar la población calculada inicialmente con este promedio. **[!UICONTROL Additional data]**

Para ello, en la **[!UICONTROL Output filtering]** ficha, simplemente agregue una condición a estos datos adicionales.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)

### Ejemplo: personalización de un correo electrónico con datos adicionales {#example--personalizing-an-email-with-additional-data}

El siguiente ejemplo ilustra la adición de diferentes tipos de datos adicionales a una consulta y su uso como campo de personalización en un correo electrónico.

Para este ejemplo, se utilizan recursos [](../../developing/using/data-model-concepts.md) personalizados:

* El recurso de **perfil** se amplió para agregar un campo que permite guardar los puntos de lealtad de cada perfil.
* Se creó un recurso de **transacciones** que identifica todas las compras realizadas por los perfiles de la base de datos. La fecha, el precio y el producto comprados se guardan para cada transacción.
* Se creó un recurso de **productos** que hace referencia a los productos disponibles para la compra.

El objetivo es enviar un correo electrónico a los perfiles para los que se ha guardado al menos una transacción. A través de este correo electrónico, los clientes recibirán un recordatorio de la última transacción realizada, así como una visión general de todas sus transacciones: el número de productos comprados, el total gastado, un recordatorio del número total de puntos de lealtad que han acumulado.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/enrichment_example1.png)

1. Agregue una **[!UICONTROL Query]** actividad que le permita dirigirse a los perfiles que han realizado al menos una transacción.

   ![](assets/enrichment_example2.png)

   En la **[!UICONTROL Additional data]** ficha de la consulta, defina los diferentes datos que se mostrarán en el correo electrónico final:

   * Campo simple de la dimensión de **perfil** correspondiente a los puntos de lealtad. Consulte la sección [Adición de un campo](#adding-a-simple-field) sencillo.
   * Dos agregados basados en la recopilación de transacciones: el número de productos comprados y la cantidad total gastada. Puede agregarlos desde la **[!UICONTROL Data]** ficha de la ventana de configuración agregada, utilizando los agregados **Recuento** y **Suma** . Consulte la sección [Adición de un agregado](#adding-an-aggregate) .
   * Recopilación que devuelve el importe gastado, la fecha y el producto de la última transacción realizada.

      Para ello, debe agregar los diferentes campos que desea mostrar desde la ficha de la ventana de configuración de la colección **[!UICONTROL Data]** .

      Para devolver solo la transacción más reciente, debe introducir "1" para la **[!UICONTROL Number of lines to return]** y aplicar un orden descendente en el campo **Fecha** de la colección desde la **[!UICONTROL Sort]** ficha.

      Consulte las secciones [Adición de una colección](#adding-a-collection) y [Clasificación de datos](#sorting-additional-data) adicionales.
   ![](assets/enrichment_example4.png)

   Si desea comprobar que la transición de salida de la actividad transfiere correctamente los datos, inicie el flujo de trabajo por primera vez (sin la actividad) y abra la transición de salida de la consulta. **[!UICONTROL Email delivery]**

   ![](assets/enrichment_example5.png)

1. Agregue una **[!UICONTROL Email delivery]** actividad. En el contenido del correo electrónico, inserte los campos de personalización correspondientes a los datos calculados en la consulta. Puede encontrarlo a través del **[!UICONTROL Additional data (targetData)]** vínculo del explorador de campos de personalización.

   ![](assets/enrichment_example3.png)

El flujo de trabajo ya está listo para ejecutarse. Los perfiles dirigidos en la consulta recibirán un correo electrónico personalizado que contiene los datos calculados a partir de sus transacciones.

## Ejemplos de consultas {#query-samples}

### Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para dirigirse a hombres de entre 18 y 30 años que viven en Londres.

![](assets/query_sample_1.png)

### Objetivo en atributos de correo electrónico {#targeting-on-email-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destino con el dominio de dirección de correo electrónico "orange.co.uk".

![](assets/query_sample_emaildomain.png)

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destino cuya dirección de correo electrónico se ha proporcionado.

![](assets/query_sample_emailnotempty.png)

### Perfiles de objetivo cuyo cumpleaños es hoy {#targeting-profiles-whose-birthday-is-today}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destino cuyo cumpleaños es hoy.

1. Arrastre el **[!UICONTROL Birthday]** filtro en la consulta.

   ![](assets/query_sample_birthday.png)

1. Configure el **[!UICONTROL Filter type]** en **[!UICONTROL Relative]** y seleccione **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

### Perfiles de objetivo que abrieron una entrega específica {#targeting-profiles-who-opened-a-specific-delivery}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles que abrieron la entrega con la etiqueta "Hora de verano".

1. Arrastre el **[!UICONTROL Opened]** filtro en la consulta.

   ![](assets/query_sample_opened.png)

1. Seleccione el envío y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

### Perfiles de objetivo para los que fallaron las entregas por un motivo específico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles para los que las entregas fallaron porque su buzón estaba lleno. Esta consulta sólo está disponible para usuarios con derechos de administración y pertenecientes a las **[!UICONTROL All (all)]** unidades organizativas (ver [esta sección](../../administration/using/organizational-units.md)).

1. Seleccione el **[!UICONTROL Delivery logs]** recurso para filtrar directamente en la tabla del registro de entrega (consulte [Uso de recursos diferentes de las dimensiones](#using-resources-different-from-targeting-dimensions)de objetivo).

   ![](assets/query_sample_failure1.png)

1. Arrastre el **[!UICONTROL Nature of failure]** filtro en la consulta.

   ![](assets/query_sample_failure2.png)

1. Seleccione el tipo de error al que desea dirigirse. En nuestro caso **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

### Perfiles de objetivo no contactados durante los últimos 7 días {#targeting-profiles-not-contacted-during-the-last-7-days}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles con los que no se ha contactado durante los últimos 7 días.

1. Arrastre el **[!UICONTROL Delivery logs (logs)]** filtro en la consulta.

   ![](assets/query_sample_7days.png)

   Seleccione **[!UICONTROL Does not exist]** en la lista desplegable y arrastre el **[!UICONTROL Delivery]** filtro.

   ![](assets/query_sample_7days1.png)

1. Configure el filtro como se muestra a continuación.

   ![](assets/query_sample_7days2.png)

### Perfiles de objetivo que hicieron clic en un vínculo específico {#targeting-profiles-who-clicked-a-specific-link-}

1. Arrastre el **[!UICONTROL Tracking logs (tracking)]** filtro en la consulta.

   ![](assets/query_sample_trackinglogs.png)

1. Arrastre el **[!UICONTROL Label (urlLabel)]** filtro.

   ![](assets/query_sample_trackinglogs2.png)

1. En el **[!UICONTROL Value]** campo, escriba la etiqueta que se definió al insertar el vínculo en el envío y confirme.

   ![](assets/query_sample_trackinglogs3.png)


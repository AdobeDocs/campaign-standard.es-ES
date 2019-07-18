---
title: Anulación de duplicación
seo-title: Anulación de duplicación
description: Anulación de duplicación
seo-description: La actividad de anulación de duplicación permite eliminar duplicados en los resultados de las actividades de entrada.
page-status-flag: no activado nunca
uuid: 11 a 22 a 9 c -3 bfe -4953-8 a 52-2 f 4 e 93 c 128 fb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: e 7 a 5 e 1 e 7-4680-46 c 7-98 b 8-0 a 47 bb 7 be 2 b 8
context-tags: dedup, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

The **[!UICONTROL Deduplication]** activity allows you to delete duplicates in the result(s) of the inbound activities.

## Context of use {#context-of-use}

The **[!UICONTROL Deduplication]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

Durante la anulación de duplicación, las transiciones entrantes se procesan por separado. Por ejemplo, si el perfil'A'está presente en el resultado de la consulta 1 y también en el resultado de la consulta 2, no se anulará la duplicación.

Por lo tanto, se recomienda que una anulación de duplicación solo tenga una transición de entrada. Para ello, puede combinar sus diferentes consultas utilizando actividades que se correspondan con sus necesidades de segmentación, como una actividad de unión, una actividad de intersección, etc. Por ejemplo:

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

Para configurar una actividad de anulación de duplicación, debe especificar una etiqueta, el método y los criterios de anulación de duplicación, así como las opciones relacionadas con el resultado.

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** si la anulación de duplicación se realiza en los datos que ya existen en la base de datos. Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** si la anulación de duplicación se realiza en los datos temporales del flujo de trabajo: seleccione la **[!UICONTROL Targeted set]** que contenga los datos para anular la duplicación. Este caso de uso se puede encontrar después de importar un archivo o si se han enriquecido los datos de la base de datos (por ejemplo, con un código de segmento).

1. Select the **[!UICONTROL Number of unique records to keep]**. El valor predeterminado de este campo es 1. El valor 0 permite mantener todos los duplicados.

   Por ejemplo, si los registros A y B se consideran duplicados de registro Y, y un registro C se considera como duplicado del registro Z:

   * Si el valor del campo es 1: Solo se conservan los registros Y y Z.
   * Si el valor del campo es 0: se conservan todos los registros.
   * Si el valor del campo es 2: los registros C y Z se conservan y se conservan dos registros de A, B e Y por casualidad o según el método de anulación seleccionado posteriormente.

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. Especifique los campos y/o expresiones para los que los valores idénticos permiten identificar los duplicados: dirección de correo electrónico, nombre, apellido, etc. El orden de las condiciones permite especificar los que se deben procesar primero.
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**: selecciona al azar el registro para que se mantenga fuera de los duplicados.
   * **[!UICONTROL Following a list of values]**: permite definir una prioridad de valor para uno o más campos. Para definir los valores, seleccione un campo o cree una expresión y, a continuación, agregue los valores a la tabla adecuada. To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: esto permite mantener registros sobre los que el valor de la expresión seleccionada no está vacío como prioridad.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: esto permite mantener los registros en los que el valor de la expresión ingresada es el más pequeño o el más grande.

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

El siguiente ejemplo ilustra una anulación de duplicación que permite excluir los duplicados de un objetivo antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.

El flujo de trabajo consta de:

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. En este caso, el flujo de trabajo se dirige a todos los perfiles comprendidos entre 18 y 25 que han estado en la base de datos cliente durante más de un año.

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** Una actividad que permite identificar los duplicados procedentes de la consulta anterior. En este ejemplo, solo se guarda un registro para cada duplicado. Los duplicados se identifican usando la dirección de correo electrónico. Esto significa que la entrega por correo electrónico solo se puede enviar una vez para que cada dirección de correo electrónico esté presente en la segmentación.

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. Esto hará que sea más coherente si se utiliza el nombre en los campos de personalización del contenido de correo electrónico.

   Además, se agrega una transición adicional para conservar los duplicados y poder enumerarlos.

   ![](assets/deduplication_example_dedup.png)

* An **[!UICONTROL Email delivery]** placed after the main outbound transition of the deduplication. The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* **[!UICONTROL Save audience]** Actividad colocada después de la transición adicional de la anulación de duplicación para guardar los duplicados en una **audiencia Duplicates** . Esta audiencia se puede reutilizar para excluir directamente a sus miembros de cada envío de correo electrónico.

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

Este ejemplo muestra cómo anular la duplicación de datos de un archivo importado antes de cargar los datos en la base de datos. Este procedimiento mejora la calidad de los datos cargados en la base de datos.

El flujo de trabajo consta de:

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. En este ejemplo, el archivo importado está en formato. csv y contiene 10 perfiles:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Este archivo también se puede utilizar como archivo de muestra para detectar y definir el formato de las columnas. From the **[!UICONTROL Column definition]** tab, make sure that each column of the imported file is configured correctly.

   ![](assets/deduplication_example2_fileloading.png)

* A **[!UICONTROL Deduplication]** activity. La anulación de la duplicación se realiza directamente después de importar el archivo y antes de insertar los datos en la base de datos. It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   Para este ejemplo, queremos mantener una sola entrada por dirección de correo electrónico única contenida en el archivo. Duplicate identification is therefore carried out on the **email** column of the temporary resource. Sin embargo, dos direcciones de correo electrónico aparecen dos veces en el archivo. Por lo tanto, dos líneas se considerarán duplicados.

   ![](assets/deduplication_example2_dedup.png)

* An **[!UICONTROL Update data]** activity allows you to insert the data kept from the deduplication process into the database. Solo se produce cuando se han actualizado los datos que se identifican como pertenecientes a la dimensión de perfil.

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

A continuación, inicie el flujo de trabajo. Los registros guardados a partir del proceso de anulación de duplicación se agregan a los perfiles de la base de datos.

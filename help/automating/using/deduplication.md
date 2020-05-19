---
title: Deduplicación
description: La actividad de Deduplicación permite eliminar duplicados en los resultados de las actividades entrantes.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 5%

---


# Deduplicación{#deduplication}

## Descripción {#description}

![](assets/deduplication.png)

La **[!UICONTROL Deduplication]** actividad permite eliminar duplicados en los resultados de las actividades entrantes.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Deduplication]** actividad se utiliza generalmente después de actividades de objetivo o después de importar un archivo y antes de actividades que permiten el uso de datos de objetivo.

Durante la deduplicación, las transiciones entrantes se procesan por separado. Por ejemplo, si el perfil &quot;A&quot; está presente como resultado de la consulta 1 y también como resultado de la consulta 2, no se eliminará la duplicación.

Por lo tanto, se aconseja que una deduplicación sólo tenga una transición de entrada. Para ello, puede combinar sus diferentes consultas mediante actividades que se correspondan con sus necesidades de segmentación, como una actividad de unión, una actividad de intersección, etc. Por ejemplo:

![](assets/dedup_bonnepratique.png)

## Configuración {#configuration}

Para configurar una actividad de deduplicación, debe introducir una etiqueta, el método y los criterios de deduplicación, así como las opciones relacionadas con el resultado.

1. Arrastre y suelte una **[!UICONTROL Deduplication]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   ![](assets/deduplication_1.png)

1. Seleccione la **[!UICONTROL Resource type]** forma en que debe llevarse a cabo la deduplicación:

   * **[!UICONTROL Database resource]** si la deduplicación se realiza sobre datos que ya existen en la base de datos. Seleccione el **[!UICONTROL Filtering dimension]** y el **[!UICONTROL Targeting dimension]**, en función de los datos que desee desduplicar. De forma predeterminada, la deduplicación se realiza en los **perfiles**.
   * **[!UICONTROL Temporary resource]** si la deduplicación se realiza en los datos temporales del flujo de trabajo: seleccione el **[!UICONTROL Targeted set]** que contiene los datos que desea anular la duplicación. Este caso de uso se puede encontrar después de importar un archivo o si los datos de la base de datos se enriquecieron (por ejemplo, con un código de segmento).

1. Seleccione el **[!UICONTROL Number of unique records to keep]**. El valor predeterminado de este campo es 1. El valor 0 le permite mantener todos los duplicados.

   Por ejemplo, si los registros A y B se consideran duplicados del registro Y y un registro C se considera un duplicado del registro Z:

   * Si el valor del campo es 1: sólo se guardan los registros Y y Z.
   * Si el valor del campo es 0: se guardan todos los registros.
   * Si el valor del campo es 2: se conservan los registros C y Z y se conservan dos registros de A, B e Y, por casualidad o en función del método de deduplicación seleccionado posteriormente.

1. Defina los **[!UICONTROL Duplicate identification]** criterios agregando condiciones en la lista proporcionada. Especifique los campos o expresiones para los que los valores idénticos permiten identificar los duplicados: dirección de correo electrónico, nombre, apellidos, etc. El orden de las condiciones permite especificar las que se procesarán en primer lugar.
1. En la lista desplegable, seleccione la opción **[!UICONTROL Deduplication method]** que desee utilizar:

   * **[!UICONTROL Choose for me]**:: selecciona aleatoriamente el registro que se va a mantener fuera de los duplicados.
   * **[!UICONTROL Following a list of values]**:: permite definir una prioridad de valor para uno o varios campos. Para definir los valores, seleccione un campo o cree una expresión y, a continuación, añada los valores a la tabla adecuada. Para definir un nuevo campo, haga clic en el botón **[!UICONTROL Add]** situado sobre la lista de valores.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: esto permite mantener registros para los que el valor de la expresión seleccionada no está vacío como prioridad.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**:: esto le permite mantener los registros en los que el valor de la expresión ingresada es el más pequeño o el más grande.

      ![](assets/deduplication_4.png)

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo 1: Identificación de duplicados antes de un envío {#example-1--identifying-duplicates-before-a-delivery}

El siguiente ejemplo ilustra una deduplicación que permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.

El flujo de trabajo se compone de:

![](assets/deduplication_example_workflow.png)

* Un **[!UICONTROL Query]** que permite definir el destinatario del correo electrónico. Aquí, el flujo de trabajo destinatario todos los perfiles de entre 18 y 25 años que han estado en la base de datos del cliente durante más de un año.

   ![](assets/deduplication_example_query.png)

* Una **[!UICONTROL Deduplication]** actividad que permite identificar los duplicados que provienen de la consulta anterior. En este ejemplo, solo se guarda un registro por cada duplicado. Los duplicados se identifican mediante la dirección de correo electrónico. Esto significa que el envío de correo electrónico solo se puede enviar una vez para que cada dirección de correo electrónico esté presente en el objetivo.

   El método de deduplicación seleccionado es **[!UICONTROL Non-empty value]**. Esto le permite asegurarse de que entre los registros guardados en caso de duplicados, se da prioridad a aquellos en los que se ha proporcionado el **Nombre** . Esto hará que sea más coherente si el nombre se utiliza en los campos de personalización del contenido del correo electrónico.

   Además, se añade una transición adicional para mantener los duplicados y poder listas.

   ![](assets/deduplication_example_dedup.png)

* Una **[!UICONTROL Email delivery]** posición después de la principal transición de salida de la deduplicación. La configuración de los envíos de correo electrónico se detalla en la sección envío [de](../../automating/using/email-delivery.md) correo electrónico.
* actividad **[!UICONTROL Save audience]** colocada después de la transición adicional de la deduplicación para guardar los duplicados en una audiencia de **Duplicados** . Esta audiencia se puede reutilizar para excluir directamente a sus miembros de cada envío de correo electrónico.

## Ejemplo 2: Desduplicación de datos de un archivo importado {#example-2--deduplicating-the-data-from-an-imported-file}

En este ejemplo se muestra cómo anular la duplicación de datos de un archivo importado antes de cargar los datos en la base de datos. Este procedimiento mejora la calidad de los datos cargados en la base de datos.

El flujo de trabajo se compone de:

![](assets/deduplication_example2_workflow.png)

* Un archivo que contiene una lista de perfiles se importa mediante una **[!UICONTROL Load file]** actividad. En este ejemplo, el archivo importado tiene formato .csv y contiene 10 perfiles:

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

   Este archivo también puede utilizarse como archivo de muestra para detectar y definir el formato de las columnas. Desde la **[!UICONTROL Column definition]** ficha, asegúrese de que cada columna del archivo importado está configurada correctamente.

   ![](assets/deduplication_example2_fileloading.png)

* A **[!UICONTROL Deduplication]** activity. La Deduplicación se realiza directamente después de importar el archivo y antes de insertar los datos en la base de datos. Por lo tanto, debe basarse en la **[!UICONTROL Temporary resource]** información de la **[!UICONTROL Load file]** actividad.

   Para este ejemplo, queremos mantener una sola entrada por dirección de correo electrónico única contenida en el archivo. Por lo tanto, la identificación del Duplicado se lleva a cabo en la columna de **correo electrónico** del recurso temporal. Sin embargo, dos direcciones de correo electrónico aparecen dos veces en el archivo. Por consiguiente, se considerarán duplicados dos líneas.

   ![](assets/deduplication_example2_dedup.png)

* Una **[!UICONTROL Update data]** actividad permite insertar los datos guardados desde el proceso de deduplicación en la base de datos. Sólo cuando se actualizan los datos se identifican los datos importados como pertenecientes a la dimensión de perfil.

   En este caso, nos gustaría conocer **[!UICONTROL Insert only]** los perfiles que no existen en la base de datos. Vamos a hacer esto utilizando la columna de correo electrónico del archivo y el campo de correo electrónico de la dimensión de **Perfil** como clave de reconciliación.

   ![](assets/deduplication_example2_writer1.png)

   Especifique las asignaciones entre las columnas del archivo desde las que desea insertar los datos y los campos de la base de datos desde la **[!UICONTROL Fields to update]** ficha.

   ![](assets/deduplication_example2_writer2.png)

A continuación, inicio el flujo de trabajo. Los registros guardados desde el proceso de deduplicación se agregan a los perfiles de la base de datos.

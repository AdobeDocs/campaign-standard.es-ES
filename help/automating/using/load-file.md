---
title: Cargar archivo
seo-title: Cargar archivo
description: Cargar archivo
seo-description: La actividad de carga de archivos permite importar datos en un formulario estructurado para utilizar estos datos en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 69 af 12 cc -6 f 82-4977-9 f 53-aa 7 bc 26 f 5 d 7 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584 ff 893-9 b 1 b -46 c 9-9628-714 ab 349 ab 88
context-tags: Fileimport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc3c687328c5a460b442b8b2497965ccab3be50b

---


# Cargar archivo{#load-file}

## Descripción {#description}

![](assets/data_loading.png)

La **[!UICONTROL Load file]** actividad permite importar datos en un formulario estructurado para utilizar estos datos en Adobe Campaign. Los datos se importan temporalmente y es necesario otra actividad para integrarlos de forma definitiva en la base de datos de Adobe Campaign.

## Contexto de uso {#context-of-use}

La manera en que se extraerán los datos se define cuando se configura la actividad. El archivo que se carga puede ser una lista de contactos, por ejemplo.

>[!CAUTION]
>
>Solo se tienen en cuenta los archivos de estructura "planos", como los archivos.txt. csv, etc., por ejemplo.

Puede:

* Utilice la estructura de archivos para aplicarla a los datos de otro archivo (recuperados con **[!UICONTROL Transfer file]** la actividad) o,
* Utilice la estructura y los datos del archivo para importarlos a Adobe Campaign.

## Configuración {#configuration}

La configuración de la actividad implica dos pasos. Primero, debe definir la estructura de archivos esperada cargando un archivo de ejemplo. Una vez realizada esta acción, puede especificar el origen del archivo cuyos datos se importarán.

>[!NOTE]
>
>Los datos del archivo de ejemplo se utilizan para configurar la actividad pero no se importan. Recomendamos utilizar un archivo de muestra con pocos datos.

1. Arrastre y suelte una **[!UICONTROL Load file]** actividad en el flujo de trabajo.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.
1. Cargue el archivo de ejemplo que le permitirá definir la estructura esperada al importar el archivo final.

   ![](assets/wkf_file_loading.png)

   Una vez cargado el archivo de datos, aparecen dos nuevas fichas en la actividad: **[!UICONTROL File structure]** y **[!UICONTROL Column definition]**.

1. Vaya a **[!UICONTROL File structure]** la ficha para ver la estructura que se detecta automáticamente desde el archivo de muestra.

   Si la estructura de archivos se detectó incorrectamente, tiene varias opciones para corregir los posibles errores:

   * Puede elegir utilizar la estructura de otro archivo seleccionando la **[!UICONTROL Detect structure from a new file]** opción.
   * Puede modificar los parámetros de detección predeterminados para adaptarlos al archivo. El **[!UICONTROL File type]** campo permite especificar si el archivo que desea importar está formado por columnas con longitud fija. En ese caso, también debe especificar el número máximo de caracteres para cada columna de la **[!UICONTROL Column definition]** ficha.

      Todas las opciones de detección necesarias para recuperar correctamente los datos del archivo se regroupan en **[!UICONTROL File format]**. Puede modificarlas y volver a detectar la estructura del último archivo cargado en la actividad teniendo en cuenta estos nuevos ajustes. Para ello, utilice **[!UICONTROL Apply configuration]** el botón. Por ejemplo, puede especificar un separador de columnas diferente.

      >[!NOTE]
      >
      >Esta operación tiene en cuenta el último archivo que se cargó en la actividad. Si el archivo detectado es grande, la vista previa de datos solo mostrará las primeras 30 líneas.

      ![](assets/wkf_file_loading3.png)

      En **[!UICONTROL File format]** la sección, la **[!UICONTROL Check columns from file against column definitions]** opción le permite comprobar que las columnas del archivo que está cargando corresponden a la definición de columna.

      Si el número y/o el nombre de las columnas no coinciden con la definición de columna, aparecerá un mensaje de error al ejecutar el flujo de trabajo. Si la opción no está activada, se mostrarán advertencias en el archivo de registro.

      ![](assets/wkf_file_loading_check.png)

1. Vaya a **[!UICONTROL Column definition]** la ficha para comprobar el formato de los datos de cada columna y ajustar los parámetros si es necesario.

   La **[!UICONTROL Column definition]** ficha permite especificar con precisión la estructura de datos de cada columna para importar datos que no contengan errores (por ejemplo, utilizar administración nula) y hacer que coincida con los tipos que ya están presentes en la base de datos de Adobe Campaign para futuras operaciones.

   Por ejemplo, puede cambiar la etiqueta de una columna, seleccionar su tipo (cadena, entero, fecha, etc.) o incluso especificar el procesamiento de errores.

   Para obtener más información, consulte [la sección Formato](../../automating/using/load-file.md#column-format) de columna.

   ![](assets/wkf_file_loading4.png)

1. En **[!UICONTROL Execution]** la ficha, especifique si el archivo se procesará para cargar datos:

   * Proviene de una transición entrante en el flujo de trabajo.
   * Es la que cargó durante el paso anterior.
   * Es un nuevo archivo que se carga desde el equipo local. La **[!UICONTROL Upload a new file from local machine]** opción aparece si la carga de un primer archivo ya se ha definido en el flujo de trabajo. Esto le permite cargar otro archivo para procesarlo si el archivo actual no se adapta a sus necesidades.

      ![](assets/wkf_file_loading1.png)

1. Si el archivo desde el que desea cargar los datos se comprime en un archivo GZIP (.gz), seleccione **[!UICONTROL Decompression]** la opción en **[!UICONTROL Add a pre-processing step]** el campo. Esto le permite descomprimir el archivo antes de cargar los datos. Esta opción solo está disponible si el archivo proviene de la transición de entrada de la actividad.
1. La **[!UICONTROL Keep the rejects in a file]** opción le permite descargar un archivo que contiene errores producidos durante la importación y aplicarle una etapa posterior al procesamiento.

   >[!NOTE]
   >
   >La **[!UICONTROL Add date and time to the file name]** opción permite agregar una marca de hora al nombre del archivo que contiene los rechazos.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Formato de columna {#column-format}

Cuando carga un archivo de ejemplo, el formato de columna se detecta automáticamente con los parámetros predeterminados para cada tipo de datos. Puede modificar estos parámetros predeterminados para especificar los procesos particulares que se deben aplicar a los datos, especialmente cuando hay un error o un valor vacío.

Para ello, seleccione **[!UICONTROL Edit properties]** entre las acciones rápidas de la columna cuyo formato desee definir. Se abrirá la ventana de detalles de formato de columna.

![](assets/wkf_file_loading4.png)

Puede modificar el formato de cada columna.

El formato de columna permite definir el procesamiento de valores de cada columna:

* **[!UICONTROL Ignore column]**: no procesa esta columna durante la carga de datos.
* **[!UICONTROL Data type]**: especifica el tipo de datos esperado para cada columna.
* **[!UICONTROL Format and separators]**, **Propiedades**: especifique las propiedades de un texto, la hora, la fecha y el formato numérico, así como el separador especificado por el contexto de la columna.

   * **[!UICONTROL Maximum number of characters]**: especifica el número máximo de caracteres para las columnas de tipo de cadena.

      Este campo debe rellenarse al cargar archivos conformados por columnas con longitud fija.

   * **[!UICONTROL Letter case management]**: define si un proceso de caracteres de caracteres debe aplicarse a los datos **de texto** .
   * **[!UICONTROL White space management]**: especifica si hay que ignorar ciertos espacios en una cadena para los datos **de texto** .
   * **[!UICONTROL Time format]****[!UICONTROL Date format]**: especifique el formato de **Fecha**, **Hora** y **Datos de fecha y hora** .
   * **[!UICONTROL Format]**: permite definir el formato de valores numéricos para los datos numéricos **de número entero** y **flotante** .
   * **[!UICONTROL Separator]**: define el separador especificado por el contexto de columna (separador decimal o separador decimal para valores numéricos, separador para fechas y hora) para **Fecha**, **Hora**, **Fecha y hora**, **Entero** y **Datos numéricos** flotantes.

* **[!UICONTROL Remapping of values]**: este campo solo está disponible en la configuración de detalles de columna. Permite transformar ciertos valores cuando se importan. Por ejemplo, puede transformar "tres" en "3".
* **[!UICONTROL Error processing]**: define el comportamiento si se encuentra un error.

   * **[!UICONTROL Ignore the value]**: el valor se ignora. Se genera una advertencia en el registro de ejecución del flujo de trabajo.
   * **[!UICONTROL Reject the line]**: no se procesa la línea completa.
   * **[!UICONTROL Use a default value]**: reemplaza el valor que provoca el error por un valor predeterminado definido en **[!UICONTROL Default value]** el campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: reemplaza el valor que provoca el error con un valor predeterminado, definido en **[!UICONTROL Default value]** el campo, a menos que se haya definido una asignación para el valor erróneo (consulte **[!UICONTROL Remapping of values]** la opción anterior).
   * **[!UICONTROL Reject the line when there is no remapping value]**: toda la línea no se procesa a menos que se haya definido una asignación para el valor erróneo (consulte **[!UICONTROL Remapping of values]** la opción anterior).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** hace referencia a errores relacionados con valores del archivo importado. Por ejemplo, se ha encontrado un tipo de datos erróneo ("cuatro" en letras para una columna "Integer"), una cadena que contiene más caracteres que el número máximo autorizado, una fecha con separadores defectuosos, etc. Sin embargo, esta opción no concierne a errores generados por administración de valores vacíos.

* **[!UICONTROL Default value]**: especifica el valor predeterminado según el procesamiento de errores elegido.
* **[!UICONTROL Empty value management]**: especifica cómo administrar valores en blanco durante la carga de datos.

   * **[!UICONTROL Generate an error for numerical fields]**: genera un error solo para los campos numéricos; de lo contrario, inserta un valor NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autoriza valores vacíos. Por lo tanto, se inserta el valor NULL.
   * **[!UICONTROL Generate an error]**: genera un error si un valor está vacío.

## Ejemplo 1: Actualización de la base de datos {#example-1-update-the-database}

La actividad de archivos de carga principalmente estructura los datos de una actividad de archivo de transferencia para integrarlos en los datos existentes.

El siguiente ejemplo muestra el resultado de una actividad de archivo de carga descargada automáticamente a través de una actividad de archivo de transferencia, seguida de una actividad de actualización de datos. Este flujo de trabajo pretende enriquecer la base de datos de Adobe Campaign con nuevos perfiles o actualizar los perfiles existentes utilizando los datos recuperados del archivo importado.

![](assets/load_file_workflow_ex1.png)

1. Arrastre y suelte una **[!UICONTROL Transfer file]** actividad en el flujo de trabajo y configúrela de forma que recupere el archivo que desea.
1. Arrastre y suelte una **[!UICONTROL Load file]** actividad en el flujo de trabajo y colóquela después de la **[!UICONTROL Transfer file]** actividad.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.
1. En **[!UICONTROL File to load]** la sección de **[!UICONTROL Execution]** la ficha, marque la **[!UICONTROL Use the file specified in the inbound transition]** opción.

   ![](assets/wkf_file_loading8.png)

1. Configure la actividad como se especifica anteriormente.
1. Arrastre y suelte una **[!UICONTROL Update data]** actividad en el flujo de trabajo y colóquela después de la **[!UICONTROL Load file]** actividad, luego configúrela. Consulte [Actualizar datos](../../automating/using/update-data.md).

Una vez que se ha iniciado el flujo de trabajo, se extraen los datos del archivo cargado y se utilizan para enriquecer la base de datos de Adobe Campaign.

## Ejemplo 2: Envío de un correo electrónico con campos enriquecidos {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](../../automating/using/load-file.md#example-2-email-with-enriched-fields)-->

La actividad de carga de archivos también permite enviar un correo electrónico enriquecido con datos adicionales de un archivo externo en el mismo flujo de trabajo.

El ejemplo siguiente muestra cómo enviar un correo electrónico utilizando datos adicionales recuperados de un archivo externo a través de la actividad de archivo de carga. En este ejemplo, el archivo externo contiene una lista de perfiles con su número de cuenta asociado. Desea importar estos datos para enviar un correo electrónico a cada perfil con su número de cuenta.

![](assets/load_file_workflow_ex2.png)

1. Arrastre y suelte una **[!UICONTROL Query]** actividad en el flujo de trabajo y ábrala para definir el objetivo principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arrastre y suelte una **[!UICONTROL Load file]** actividad para asignar algunos datos a un perfil. En este ejemplo, cargue un archivo que contenga números de cuenta correspondientes a algunos perfiles de la base de datos.

   ![](assets/load_file_activity.png)

1. Arrastre y suelte una **[!UICONTROL Enrichment]** actividad en el flujo de trabajo y vincule el archivo de carga y las actividades de consulta a él.

1. En **[!UICONTROL Advanced relations]** la ficha de la actividad de enriquecimiento, seleccione **[!UICONTROL 0 or 1 cardinality simple link]** y defina los campos que se utilizarán para la reconciliación. Aquí utilizamos el apellido para reconciliar los datos con los perfiles de la base de datos.

   ![](assets/load_file_enrichment_relation.png)

1. En **[!UICONTROL Additional data]** la ficha, seleccione los elementos que desee utilizar en su correo electrónico. Aquí seleccione Número de cuenta (columna del archivo que recuperó a través de la actividad de archivo de carga).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Para obtener más información, consulte la sección [Enriquecimiento](../../automating/using/enrichment.md) .

1. Arrastre y suelte una **[!UICONTROL Segmentation]** actividad en el flujo de trabajo y ábrala para refinar el objetivo principal.

   ![](assets/load_file_segmentation.png)

   Para obtener más información, consulte la sección [Segmentación](../../automating/using/segmentation.md) .

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad en el flujo de trabajo y ábrala.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Agregue un campo de personalización y seleccione los datos adicionales definidos en la actividad de enriquecimiento (aquí Número de cuenta) del **[!UICONTROL Additional data (targetData)]** nodo. Esto permite recuperar dinámicamente el número de cuenta de cada perfil en el contenido de correo electrónico.

   ![](assets/load_file_perso_field.png)

1. Guarde el correo electrónico e inicie el flujo de trabajo.

El correo electrónico se envía al objetivo. Cada perfil recibe el correo electrónico con su correspondiente número de cuenta.

![](assets/load_file_email.png)

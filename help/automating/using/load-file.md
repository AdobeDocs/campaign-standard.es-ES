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
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Load file{#load-file}

## Description {#description}

![](assets/data_loading.png)

The **[!UICONTROL Load file]** activity allows you to import data in one structured form to use this data in Adobe Campaign. Los datos se importan temporalmente y es necesario otra actividad para integrarlos de forma definitiva en la base de datos de Adobe Campaign.

## Context of use {#context-of-use}

La manera en que se extraerán los datos se define cuando se configura la actividad. El archivo que se carga puede ser una lista de contactos, por ejemplo.

>[!CAUTION]
>
>Solo se tienen en cuenta los archivos de estructura "planos", como los archivos.txt. csv, etc., por ejemplo.

Puede:

* Use the file structure to apply it to another file's data (recovered using the **[!UICONTROL Transfer file]** activity) or,
* Utilice la estructura y los datos del archivo para importarlos a Adobe Campaign.

## Configuration {#configuration}

La configuración de la actividad implica dos pasos. Primero, debe definir la estructura de archivos esperada cargando un archivo de ejemplo. Una vez realizada esta acción, puede especificar el origen del archivo cuyos datos se importarán.

>[!NOTE]
>
>Los datos del archivo de ejemplo se utilizan para configurar la actividad pero no se importan. Recomendamos utilizar un archivo de muestra con pocos datos.

1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Cargue el archivo de ejemplo que le permitirá definir la estructura esperada al importar el archivo final.

   ![](assets/wkf_file_loading.png)

   Once the data file is uploaded, two new tabs appear in the activity: **[!UICONTROL File structure]** and **[!UICONTROL Column definition]**.

1. Go to the **[!UICONTROL File structure]** tab to view the structure that is automatically detected from the sample file.

   Si la estructura de archivos se detectó incorrectamente, tiene varias opciones para corregir los posibles errores:

   * You can choose to use the structure of another file by selecting the **[!UICONTROL Detect structure from a new file]** option.
   * Puede modificar los parámetros de detección predeterminados para adaptarlos al archivo. The **[!UICONTROL File type]** field lets you specify if the file you want to import is made up of columns with fixed length. In that case, you must also specify the maximum number of characters for each column in the **[!UICONTROL Column definition]** tab.

      All of the detection options necessary to correctly recover the data from the file are regrouped in **[!UICONTROL File format]**. Puede modificarlas y volver a detectar la estructura del último archivo cargado en la actividad teniendo en cuenta estos nuevos ajustes. To do this, use the **[!UICONTROL Apply configuration]** button. Por ejemplo, puede especificar un separador de columnas diferente.

      >[!NOTE]
      >
      >Esta operación tiene en cuenta el último archivo que se cargó en la actividad. Si el archivo detectado es grande, la vista previa de datos solo mostrará las primeras 30 líneas.

      ![](assets/wkf_file_loading3.png)

      In the **[!UICONTROL File format]** section, the **[!UICONTROL Check columns from file against column definitions]** option lets you verify that the columns of the file you are uploading correspond to the column definition.

      Si el número y/o el nombre de las columnas no coinciden con la definición de columna, aparecerá un mensaje de error al ejecutar el flujo de trabajo. Si la opción no está activada, se mostrarán advertencias en el archivo de registro.

      ![](assets/wkf_file_loading_check.png)

1. Go to the **[!UICONTROL Column definition]** tab to check the data format for each column and adjust the parameters if necessary.

   The **[!UICONTROL Column definition]** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors (for example, using null management) and make it match the types that are already present in the Adobe Campaign database for future operations.

   Por ejemplo, puede cambiar la etiqueta de una columna, seleccionar su tipo (cadena, entero, fecha, etc.) o incluso especificar el procesamiento de errores.

   For more information, refer to the [Column format](../../automating/using/load-file.md#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. In the **[!UICONTROL Execution]** tab, specify whether the file is to be processed for loading data:

   * Proviene de una transición entrante en el flujo de trabajo.
   * Es la que cargó durante el paso anterior.
   * Es un nuevo archivo que se carga desde el equipo local. The **[!UICONTROL Upload a new file from local machine]** option appears if uploading a first file was already defined in the workflow. Esto le permite cargar otro archivo para procesarlo si el archivo actual no se adapta a sus necesidades.

      ![](assets/wkf_file_loading1.png)

1. If the file that you want to load the data from is compressed into a GZIP file (.gz), select the **[!UICONTROL Decompression]** option in the **[!UICONTROL Add a pre-processing step]** field. Esto le permite descomprimir el archivo antes de cargar los datos. Esta opción solo está disponible si el archivo proviene de la transición de entrada de la actividad.
1. The **[!UICONTROL Keep the rejects in a file]** option enables you to download a file containing errors that occurred during the import, and to apply to it a post-processing stage.

   >[!NOTE]
   >
   >The **[!UICONTROL Add date and time to the file name]** option lets you add a timestamp the name of the file containing the rejects.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Column format {#column-format}

Cuando carga un archivo de ejemplo, el formato de columna se detecta automáticamente con los parámetros predeterminados para cada tipo de datos. Puede modificar estos parámetros predeterminados para especificar los procesos particulares que se deben aplicar a los datos, especialmente cuando hay un error o un valor vacío.

To do this, select **[!UICONTROL Edit properties]** from the quick actions of the column whose format you would like to define. Se abrirá la ventana de detalles de formato de columna.

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

## Example {#example}

La actividad de archivos de carga principalmente estructura los datos de una actividad de archivo de transferencia para integrarlos en los datos existentes.

El siguiente ejemplo muestra el resultado de una actividad de archivo de carga descargada automáticamente a través de una actividad de archivo de transferencia, seguida de una actividad de actualización de datos. Este flujo de trabajo pretende enriquecer la base de datos de Adobe Campaign con nuevos perfiles o actualizar los perfiles existentes utilizando los datos recuperados del archivo importado.

1. Drag and drop a **[!UICONTROL Transfer file]** activity into your workflow and configure it in a way so that it recovers the file you would like.
1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL File to load]** section of the **[!UICONTROL Execution]** tab, check the **[!UICONTROL Use the file specified in the inbound transition]** option.

   ![](assets/wkf_file_loading8.png)

1. Configure la actividad como se especifica anteriormente.
1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it. Refer to [Update data](../../automating/using/update-data.md).

Una vez que se ha iniciado el flujo de trabajo, se extraen los datos del archivo cargado y se utilizan para enriquecer la base de datos de Adobe Campaign.

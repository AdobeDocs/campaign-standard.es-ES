---
title: Cargar archivo
description: La actividad Cargar archivo le permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 373e4012-9daf-4da7-aad6-54726d991544
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 93%

---

# Carga de archivo {#load-file}

## Descripción {#description}

>[!CAUTION]
>
>Tenga en cuenta los límites de almacenamiento SFTP, almacenamiento de bases de datos y perfil activo según el contrato de Adobe Campaign mientras utiliza esta funcionalidad.

![](assets/data_loading.png)

La actividad de **[!UICONTROL Load file]** le permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign. Los datos se importan temporalmente y se necesita otra actividad para integrarlos definitivamente en la base de datos de Adobe Campaign.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad. El archivo que se va a cargar puede ser una lista de contactos, por ejemplo.

Se puede:

* Utilizar la estructura de archivos para aplicarla a los datos de otro archivo (recuperados mediante la actividad de **[!UICONTROL Transfer file]**) o
* Utilizar la estructura y los datos del archivo para importarlos a Adobe Campaign.

>[!IMPORTANT]
>
>Solo se tienen en cuenta los archivos de estructura “planos”, como los archivos .txt, .csv, etc.

**Temas relacionados:**

* [Caso de uso: Actualización de la base de datos con datos externos](../../automating/using/update-database-file.md)
* [Caso de uso: Actualización de datos en función de una descarga automática de archivos](../../automating/using/update-data-automatic-download.md)
* [Caso de uso: Envío de un correo electrónico con campos enriquecidos](../../automating/using/sending-email-enriched-fields.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

La configuración de actividad incluye dos pasos. En primer lugar, debe definir la estructura de archivos esperada cargando un archivo de muestra. Una vez hecho esto, puede especificar el origen del archivo cuyos datos se importarán.

>[!NOTE]
>
>Los datos del archivo de muestra se utilizan para configurar la actividad, pero no se importan. Se recomienda utilizar un archivo de muestra que contenga pocos datos.

1. Arrastre y suelte una actividad de **[!UICONTROL Load file]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Cargue el archivo de muestra que le permitirá definir la estructura esperada al importar el archivo final.

   ![](assets/wkf_file_loading.png)

   Una vez cargado el archivo de datos, aparecen dos pestañas nuevas en la actividad: **[!UICONTROL File structure]** y **[!UICONTROL Column definition]**.

1. Vaya a la pestaña **[!UICONTROL File structure]** para ver la estructura que se detecta automáticamente desde el archivo de muestra.

   Si la estructura de archivos se detecta incorrectamente, tiene varias opciones para corregir los posibles errores:

   * Puede elegir utilizar la estructura de otro archivo seleccionando la opción **[!UICONTROL Detect structure from a new file]**.
   * Puede modificar los parámetros de detección predeterminados para adaptarlos al archivo. El campo **[!UICONTROL File type]** le permite especificar si el archivo que desea importar está compuesto por columnas de longitud fija. En ese caso, también debe especificar el número máximo de caracteres para cada columna en la pestaña **[!UICONTROL Column definition]**.

      Todas las opciones de detección necesarias para recuperar correctamente los datos del archivo se reagrupan en **[!UICONTROL File format]**. Puede modificarlas y, a continuación, volver a detectar la estructura del último archivo cargado en la actividad teniendo en cuenta estas nuevas configuraciones. Para ello, utilice el botón **[!UICONTROL Apply configuration]**. Por ejemplo, puede especificar un separador de columnas diferente.

      >[!NOTE]
      >
      >Esta operación tiene en cuenta el último archivo que se cargó en la actividad. Si el archivo detectado es grande, la previsualización de datos solo mostrará las primeras 30 líneas.

      ![](assets/wkf_file_loading3.png)

      En la sección **[!UICONTROL File format]**, la opción **[!UICONTROL Check columns from file against column definitions]** le permite verificar que las columnas del archivo que está cargando corresponden a la definición de la columna.

      Si el número o el nombre de las columnas no coinciden con la definición de la columna, aparecerá un mensaje de error al ejecutar el flujo de trabajo. Si la opción no está activada, se mostrarán advertencias en el archivo de registro.

      ![](assets/wkf_file_loading_check.png)

1. Vaya a la pestaña **[!UICONTROL Column definition]** para comprobar el formato de los datos de cada columna y ajustar los parámetros si es necesario.

   La pestaña **[!UICONTROL Column definition]** le permite especificar con precisión la estructura de datos de cada columna para importar datos que no contengan errores (por ejemplo, mediante el uso de la administración nula) y hacer que coincida con los tipos que ya están presentes en la base de datos de Adobe Campaign para futuras operaciones.

   Por ejemplo, puede cambiar la etiqueta de una columna y seleccionar su tipo (cadena, entero, fecha, etc.) o incluso especificar el procesamiento de errores.

   Para obtener más información, consulte la sección [Formato de columna](#column-format).

   ![](assets/wkf_file_loading4.png)

1. En la pestaña **[!UICONTROL Execution]**, especifique si el archivo se va a procesar para cargar datos:

   * Proviene de una transición entrante en el flujo de trabajo.
   * Es el que cargó durante el paso anterior.
   * Es un nuevo archivo que se carga desde el equipo local. La opción **[!UICONTROL Upload a new file from local machine]** aparece si la carga de un primer archivo ya estaba definida en el flujo de trabajo. Esto le permite cargar otro archivo para procesarlo si el archivo actual no se ajusta a sus necesidades.

      ![](assets/wkf_file_loading1.png)

1. Si el archivo desde el que desea cargar los datos está comprimido en un archivo GZIP (.gz), seleccione la opción **[!UICONTROL Decompression]** en el campo **[!UICONTROL Add a pre-processing stage]**. Esto le permite descomprimir el archivo antes de cargar los datos. Esta opción solo está disponible si el archivo procede de la transición entrante de la actividad.

   El campo **[!UICONTROL Add a pre-processing stage]** también permite descifrar un archivo antes de importarlo a la base de datos. Para obtener más información sobre cómo trabajar con archivos cifrados, consulte [esta sección](../../automating/using/managing-encrypted-data.md)

1. La opción **[!UICONTROL Keep the rejects in a file]** le permite descargar un archivo que contenga errores producidos durante la importación y aplicarle una fase de procesamiento posterior. Cuando se activa la opción, se cambia el nombre de la transición saliente a “Rechazos”.

   >[!NOTE]
   >
   >La opción **[!UICONTROL Add date and time to the file name]** le permite agregar una marca de tiempo al nombre del archivo que contiene los rechazos.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Si se produce algún error con la actividad después de ejecutar el flujo de trabajo, consulte los registros para obtener más detalles sobre los valores incorrectos en el archivo. Para obtener más información sobre los registros del flujos de trabajo, consulte [esta sección](../../automating/using/monitoring-workflow-execution.md).

## Formato de columna {#column-format}

Al cargar un archivo de muestra, el formato de columna se detecta automáticamente con los parámetros predeterminados para cada tipo de datos. Puede modificar estos parámetros predeterminados para especificar los procesos concretos que se aplican a los datos, especialmente cuando hay un error o un valor vacío.

Para ello, seleccione **[!UICONTROL Edit properties]** entre las acciones rápidas de la columna cuyo formato desee definir. Se abrirá la ventana de detalles de formato de columna.

![](assets/wkf_file_loading4.png)

A continuación, podrá modificar el formato de cada columna.

El formato de columna permite definir el valor de procesamiento de cada columna:

* **[!UICONTROL Ignore column]**: no se procesa esta columna durante la carga de datos.
* **[!UICONTROL Data type]**: especifica el tipo de datos esperados para cada columna.
* **[!UICONTROL Format and separators]**, **Propiedades**: especifique las propiedades de un texto, el formato de hora, fecha y valor numérico, así como el separador especificado por el contexto de columna.

   * **[!UICONTROL Maximum number of characters]**: especifica el número máximo de caracteres para las columnas de tipo de cadena.

      Este campo debe rellenarse al cargar archivos formados por columnas de longitud fija.

   * **[!UICONTROL Letter case management]**: define si es necesario aplicar un proceso de mayúsculas y minúsculas de caracteres a los datos de **texto**.
   * **[!UICONTROL White space management]**: especifica si determinados espacios deben ignorarse en una cadena para datos de **texto**.
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: especifica el formato para los datos de **fecha**, **hora** y **fecha y hora**.
   * **[!UICONTROL Format]**: le permite definir el formato de los valores numéricos para los datos de **números enteros** y **números flotantes**.
   * **[!UICONTROL Separator]**: define el separador especificado por el contexto de columna (separador de miles o decimales para valores numéricos, separador de fechas y hora) para datos de **fecha**, **hora**, **fecha y hora**, **números enteros** y **números flotantes**.

* **[!UICONTROL Remapping of values]**: este campo solo está disponible en la configuración de detalles de la columna. Permite transformar determinados valores al importarlos. Por ejemplo, se puede transformar “tres” en “3”.
* **[!UICONTROL Error processing]**: define el comportamiento si se produce un error.

   * **[!UICONTROL Ignore the value]**: se ignora el valor. Se genera una advertencia en el registro de ejecución del flujo de trabajo.
   * **[!UICONTROL Reject the line]**: no se procesa la línea completa.
   * **[!UICONTROL Use a default value]**: reemplaza el valor que provoca el error con un valor predeterminado definido en el campo **[!UICONTROL Default value]**.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: reemplaza el valor que causa el error por un valor predeterminado, definido en el campo **[!UICONTROL Default value]**, a menos que se haya definido una asignación para el valor erróneo (consulte la opción **[!UICONTROL Remapping of values]** anterior).
   * **[!UICONTROL Reject the line when there is no remapping value]**: la línea completa no se procesa a menos que se haya definido una asignación para el valor erróneo (consulte la opción **[!UICONTROL Remapping of values]** anterior).

   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** se refiere a errores relacionados con los valores del archivo importado. Por ejemplo, se encontró un tipo de datos erróneo (“cuatro” en letras para una columna “entero”), una cadena que contiene más caracteres que el número máximo autorizado, una fecha con separadores erróneos, etc. Sin embargo, esta opción no afecta a los errores generados por la administración de valores vacía.

* **[!UICONTROL Default value]**: especifica el valor predeterminado de acuerdo con el procesamiento de error seleccionado.
* **[!UICONTROL Empty value management]**: especifica cómo administrar valores vacíos durante la carga de datos.

   * **[!UICONTROL Generate an error for numerical fields]**: genera un error solo para los campos numéricos; en caso contrario, inserta un valor NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autoriza los valores vacíos. Por lo tanto, se inserta el valor NULL.
   * **[!UICONTROL Generate an error]**: genera un error si un valor está vacío.

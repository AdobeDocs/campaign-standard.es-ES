---
title: Transferir archivo
description: La actividad Transferir archivo permite recibir o enviar archivos, comprobar si hay archivos presentes o archivos de lista en Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileTransfer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 736bf3dc-96c4-4518-96f8-d9aaa46d7f84
source-git-commit: 53852538ac1e092dc9376119f29d969ed4b02952
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 83%

---

# Transferencia de archivo{#transfer-file}

## Descripción {#description}

![](assets/file_transfer.png)

La actividad **[!UICONTROL Transfer file]** le permite recibir o enviar archivos, comprobar si hay archivos presentes o archivos de lista en Adobe Campaign.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad. El archivo que se va a cargar puede ser una lista de contactos, por ejemplo.

Puede utilizar esta actividad para recuperar datos que luego se estructuran con la actividad **[!UICONTROL Load file]**.

**Temas relacionados:**

* [Caso de uso: Actualización de datos en función de una descarga automática de archivos](../../automating/using/update-data-automatic-download.md)

## Configuración {#configuration}

1. Coloque una actividad **[!UICONTROL Transfer file]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Utilice la lista desplegable del campo **[!UICONTROL Action]** para seleccionar una de las siguientes acciones de actividad:

   ![](assets/wkf_file_transfer_01.png)

   * **Descargar archivo**: permite descargar un archivo.
   * **Cargar archivo**: permite cargar un archivo. Al cargar un archivo desde un archivo de Adobe Campaign, se genera una entrada de registro en el menú **[!UICONTROL Export audits]**. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md).
   * **Comprobar si existe un archivo**: permite comprobar si hay un archivo.
   * **Lista de archivos**: permite enumerar los archivos presentes en el servidor definido en la pestaña **[!UICONTROL Protocol]**. Esta acción se utiliza principalmente con fines de depuración, para comprobar si la actividad está configurada según sus necesidades antes de descargar los archivos del servidor remoto.

1. Seleccione el protocolo que desee utilizar:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [almacenamiento de blob de Microsoft Azure](#azure-blob-configuration-wf)
   * [Archivos presentes en el servidor de Adobe Campaign](#files-server-configuration-wf)

1. La sección **[!UICONTROL Additional options]**, disponible en función del protocolo seleccionado, le permite añadir parámetros al protocolo.

   Puede hacer lo siguiente:

   * **[!UICONTROL Delete the source files after transfer]**: borra los archivos del servidor remoto. Si deja esta opción sin marcar, asegúrese de supervisar manualmente el tamaño del contenido archivado en el directorio SFTP.

   * **[!UICONTROL Sorting files]**: permite ordenar archivos de forma alfanumérica. Esta opción está desactivada de forma predeterminada.

      <!--**[!UICONTROL Disable passive mode]**: allows you to specify the connection port to be used for data transfer.-->

   * **[!UICONTROL List all files]**: esta opción está disponible al seleccionar la variable **[!UICONTROL File listing]** en la variable **[!UICONTROL General]** pestaña . Permite indexar todos los archivos presentes en el servidor en la variable de evento **vars.filenames** en la que los nombres de archivo están separados por los caracteres **&#39;n&#39;**.

1. La sección **[!UICONTROL If no files are found]** de la pestaña **[!UICONTROL Advanced options]** permite configurar acciones específicas si se detectan errores o archivos inexistentes al iniciar la actividad.

   También puede definir reintentos. Los diferentes reintentos aparecen en el registro de ejecución del flujo de trabajo.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

### Configuración con HTTP {#HTTP-configuration-wf}

El protocolo HTTP permite iniciar la descarga de un archivo desde una cuenta externa o desde una dirección URL.

Con este protocolo, puede elegir **[!UICONTROL Use connection parameters defined in an external account]** . En este caso, seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.

![](assets/wkf_file_transfer_03.png)

También puede elegir la opción **[!UICONTROL Quick configuration]**. Solo es necesario introducir la dirección URL en el campo URL.
![](assets/wkf_file_transfer_04.png)

**[!UICONTROL Follow redirections]**, **[!UICONTROL Ignore the HTTP return code]** y **[!UICONTROL Add received HTTP headers to the file]** son las opciones adicionales disponibles al seleccionar el protocolo HTTP.

### Configuración con SFTP {#SFTP-configuration-wf}

El protocolo SFTP permite iniciar la descarga de un archivo desde una dirección URL o una cuenta externa.

Con este protocolo, puede elegir **[!UICONTROL Use connection parameters defined in an external account]** , seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Se admiten caracteres comodín.

También puede elegir la opción **[!UICONTROL Quick configuration]**. Solo es necesario introducir la dirección URL en el campo URL.

### Configuración con Amazon S3 {#S3-configuration-wf}

El protocolo Amazon S3 permite iniciar la descarga de un archivo desde una URL o una cuenta externa a través de Amazon Simple Storage Service (S3).

1. Seleccione una cuenta externa de Amazon S3. Para obtener más información, consulte [esta página](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

3. Especifique la ruta del archivo que desea descargar.

   ![](assets/wkf_file_transfer_08.png)

   >[!CAUTION]
   >
   > Los comodines no son compatibles con Amazon S3.
   >
   > Para dirigir varios archivos, como `my_file_02` y `my _file_3433`, puede utilizar la siguiente sintaxis: `acs-myawsbucket.s3.amazonaws.com/object-path/my_file_`.

4. Si desea eliminar los archivos de origen cuando la transferencia se haya completado, marque **[!UICONTROL Delete the source files after transfer]**.

### Configuración con Microsoft Azure Blob Storage {#azure-blob-configuration-wf}

El protocolo de Microsoft Azure Blob permite acceder al blob ubicado en una cuenta de Microsoft Azure Blob Storage.

1. Seleccione la cuenta externa de **[!UICONTROL Microsoft Azure Blob]**. Para obtener más información, consulte [esta página](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Especifique la ruta del archivo que desea descargar. Puede coincidir con varios blobs. En ese caso, la actividad **[!UICONTROL File transfer]** activa la transición de salida una vez por cada blob detectado. Luego se procesan en orden alfabético.

   >[!CAUTION]
   >
   >Los caracteres comodín no son compatibles con varios nombres de archivo. En su lugar, debe introducir un prefijo. Se admiten todos los nombres de blob que coincidan con ese prefijo.

   Aquí tiene una lista de ejemplos de rutas de archivos:

   * **“campaign/”**: coincide con todos los blobs de la carpeta Campaign ubicada en la raíz del contenedor.
   * **“campaign/new-”**: coincide con todos los blobs con un nombre de archivo que empieza por “new-” y se encuentra en la carpeta Campaign.
   * **“”**: introducir una ruta vacía permite hacer coincidir todas las etiquetas disponibles en el contenedor.

### Configuración con archivos presentes en el servidor de Adobe Campaign {#files-server-configuration-wf}

El protocolo de **[!UICONTROL File(s) present on the Adobe Campaign server]** corresponde al repositorio que contiene los archivos que se van a recuperar.
Se pueden usar metacaracteres o caracteres comodín (por ejemplo, * o ?) para filtrar archivos.

Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**
La opción **[!UICONTROL Use a dynamic file path]** permite utilizar una expresión estándar y variables de eventos para personalizar el nombre del archivo que desea transferir. Para obtener más información, consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

Tenga en cuenta que la ruta debe estar relacionada con el directorio de espacio de almacenamiento del servidor de Adobe Campaign. Los archivos se encuentran en el directorio **sftp&lt;yourinstancename>/** . Tampoco puede examinar los directorios situados encima del espacio de almacenamiento.

Por ejemplo:

`user&lt;yourinstancename>/my_recipients.csv` es correcto.

`../hello/my_recipients.csv` es incorrecto.

`//myserver/hello/myrecipients.csv` es incorrecto.

## Configuración de la histórica {#historization-settings}

Cada vez que se ejecuta una actividad de **[!UICONTROL Transfer file]**, almacena los archivos cargados o descargados en una carpeta dedicada. Se crea una carpeta para cada actividad de **[!UICONTROL Transfer file]** de un flujo de trabajo. Por lo tanto, es importante poder limitar el tamaño de esta carpeta para conservar el espacio físico en el servidor.

Para ello, puede definir la **[!UICONTROL Historization settings]** en las **[!UICONTROL Advanced options]** de la actividad **[!UICONTROL Transfer File]**.

**[!UICONTROL Historization settings]** permite definir un número máximo de archivos o un tamaño total para la carpeta de la actividad. De forma predeterminada, se autorizan 100 archivos y 50 MB.

Cada vez que se ejecuta la actividad, la carpeta se marca de la siguiente manera:

* Solo se tienen en cuenta los archivos creados más de 24 horas antes de la ejecución de la actividad.
* Si el número de archivos que se tiene en cuenta es mayor que el valor del parámetro **[!UICONTROL Maximum number of files]**, se eliminan los archivos más antiguos hasta que se alcance el valor de **[!UICONTROL Maximum number of files]** permitido.
* Si el tamaño total de los archivos que se tienen en cuenta es mayor que el valor del parámetro **[!UICONTROL Maximum size (in MB)]**, se eliminan los archivos más antiguos hasta que se alcance el valor de **[!UICONTROL Maximum size (in MB)]** permitido.

>[!NOTE]
>
>Si la actividad no se vuelve a ejecutar, no se comprueba ni depura la carpeta. Tenga esto en cuenta a la hora de transferir archivos de gran tamaño.

## Variables de salida {#output-variables}

La variable **[!UICONTROL Transfer file]** la actividad genera variables de evento como salida, que puede aprovechar en otras actividades, por ejemplo para comprobar el número de archivos descargados mediante un [Prueba](../../automating/using/test.md) actividad.

Tenga en cuenta que las variables de eventos también se pueden pasar a otro flujo de trabajo mediante una señal externa (consulte [Personalización de un flujo de trabajo con parámetros externos](../../automating/using/customizing-workflow-external-parameters.md)).

Las variables de salida disponibles son:

* **[!UICONTROL fileName]**: nombre de los archivos transferidos.
* **[!UICONTROL filesCount]**: número de archivos transferidos.

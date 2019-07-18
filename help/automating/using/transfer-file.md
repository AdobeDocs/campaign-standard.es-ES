---
title: Transferir archivo
seo-title: Transferir archivo
description: Transferir archivo
seo-description: La actividad de archivos de transferencia permite recibir o enviar archivos, comprobar si existen archivos presentes o mostrar archivos en Adobe Campaign.
page-status-flag: no activado nunca
uuid: a 2 f 18118-b 681-4310-aee 0-9 e 82179 d 2032
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752 f 2 aed-f 897-485 e-b 329-f 3 cc 1756 ee 8 e
context-tags: Filetransfer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

The **[!UICONTROL Transfer file]** activity allows you to receive or send files, test whether there are files present, or list files in Adobe Campaign.

## Context of use {#context-of-use}

La manera en que se extraerán los datos se define cuando se configura la actividad. El archivo que se carga puede ser una lista de contactos, por ejemplo.

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Use the drop-down list in the **[!UICONTROL Action]** field to select one of the following activity actions:

   ![](assets/wkf_file_transfer_01.png)

   * **Descarga de archivo**: permite descargar un archivo.
   * **Carga de archivos**: permite cargar un archivo. Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **Pruebe si existe el archivo**: le permite comprobar si hay un archivo.
   * **Listado de archivos**: permite enumerar los archivos presentes en Adobe Campaign.
   Según la acción seleccionada, hay disponibles uno o varios protocolos:

   * **HTTP**: este protocolo permite descargar un archivo desde una cuenta externa o desde una dirección URL.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_03.png)

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.

         ![](assets/wkf_file_transfer_04.png)
   * **S 3**: este protocolo le permite empezar a descargar un archivo desde una URL o una cuenta externa mediante Amazon Simple Storage Service (S 3).

      * Seleccione la cuenta externa y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: este protocolo le permite empezar a descargar un archivo desde una dirección URL o una cuenta externa.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Se admiten comodines.

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. Los archivos se procesarán en orden secuencial.

         ![](assets/wkf_file_transfer_sort.png)
   * **Archivos presentes en el servidor de Adobe Campaign**: este protocolo corresponde al repositorio que contiene los archivos que se deben recuperar.

      Metacaracteres o comodines (por ejemplo, * o?) puede utilizarse para filtrar archivos.

      Complete este campo y confirme su actividad para utilizar este protocolo.

      >[!NOTE]
      >
      >La ruta debe ser relativa al directorio de espacio de almacenamiento del servidor de Adobe Campaign. Los archivos se encuentran en el directorio** sftp &lt; yourinstancename &gt;/**. Tampoco puede examinar los directorios por encima del espacio de almacenamiento. For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** es incorrecto. **//myserver/hello/myrecipients.csv** es incorrecto.
   Seleccione el protocolo y complete los campos asociados.

   The **[!UICONTROL Use a dynamic file path]** option, available for each protocol, lets you use a standard expression and events variables to personalize the name of the file to transfer. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. The **[!UICONTROL Additional options]** section, available depending on the protocol selected, allows you to add parameters to your protocol. Puede:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: esta opción está disponible al seleccionar **[!UICONTROL File listing]** la acción. It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   También puede definir reintentos. Los diferentes reintentos aparecen en el registro de ejecución del flujo de trabajo.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Historization settings {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. Por lo tanto, es importante poder limitar el tamaño de esta carpeta para conservar el espacio físico en el servidor.

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** permitir definir un número máximo de archivos o el tamaño total de la carpeta de la actividad. De forma predeterminada, se autorizan 100 archivos y 50 MB.

Cada vez que se ejecuta la actividad, la carpeta se comprueba de la siguiente manera:

* Solo se tienen en cuenta los archivos creados más de 24 horas antes de la ejecución de la actividad.
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
Si la actividad no vuelve a ejecutarse, su carpeta no se revisará ni se purgará. Tenga en cuenta esto, tenga cuidado al transferir archivos de gran tamaño.

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. El objetivo de este flujo de trabajo es agregar o actualizar los perfiles de base de datos de Adobe Campaign con los datos recuperados por el flujo de trabajo.

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Select the **Use connection parameters defined in an external account** option.
1. Introduzca el nombre de la cuenta externa.
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme su actividad y guarde el flujo de trabajo.


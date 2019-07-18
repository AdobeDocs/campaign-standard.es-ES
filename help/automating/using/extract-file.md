---
title: Extraer archivo
seo-title: Extraer archivo
description: Extraer archivo
seo-description: La actividad de extracción de archivos permite exportar datos desde Adobe Campaign en forma de archivo externo.
page-status-flag: no activado nunca
uuid: 631 f 0 fbd -9 e 8 d -4 f 77-a 338-fcb 7 f 4 fc 1774
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: a 06509 f 9-4731-4187-b 43 d -3 bfa 361284 d 3
context-tags: Fileexport, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## Description {#description}

![](assets/export.png)

The **[!UICONTROL Extract file]** activity allows you to export data from Adobe Campaign in the form of an external file.

## Context of use {#context-of-use}

La manera en que se extraerán los datos se define al configurar la actividad.

>[!CAUTION]
>
>**[!UICONTROL Extract file]** La actividad debe colocarse después de una **[!UICONTROL Query]** actividad para usarla.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Enter the label of the **Output file**. La etiqueta del archivo se completará automáticamente con la fecha y la hora en que se creó para que sea único. Por ejemplo: recipients_20150815_081532.txt para un archivo generado el 15 de agosto de 2015 a las 8:15:32.

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. El archivo de salida se comprime en un archivo GZIP (.gz).
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   Se abrirá una nueva ventana.

   ![](assets/wkf_data_export3.png)

1. Introduzca una expresión. To do this, you can select an existing expression or create a new one using the **expression editor**.
1. Confirme su expresión.

   La expresión se agrega a las columnas de salida.

1. Cree tantas columnas como necesite. Puede editar columnas haciendo clic en sus expresiones y etiquetas.

   Si exporta perfiles y desea utilizarlos en una herramienta externa, asegúrese de exportar un identificador único. De forma predeterminada, no todos los perfiles tienen un identificador único, dependiendo de cómo se agregan a la base de datos. For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Esta opción permite recuperar etiquetas más cortas fáciles de entender en lugar de ID.

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos se puedan utilizar fuera de Adobe Campaign.

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   En este ejemplo, la consulta se realiza en todos los perfiles de 18 a 30.

1. Abra la actividad Extraer archivo para editarla.
1. Asigne un nombre al archivo de salida.
1. Agregue columnas de salida.

   En este ejemplo, el correo electrónico, la edad, la fecha de nacimiento, el nombre y el apellido de los perfiles se agregan como columnas de salida.

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * Formato de salida CSV

      ![](assets/wkf_data_export7.png)

   * Formato de fecha

      ![](assets/wkf_data_export9.png)

1. Confirme su actividad.
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme su actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se ha ejecutado correctamente, el archivo extraído está disponible en la cuenta externa.


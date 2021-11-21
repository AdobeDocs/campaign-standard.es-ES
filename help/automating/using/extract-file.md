---
title: Extraer archivo
description: La actividad Extraer archivo permite exportar datos desde Adobe Campaign en forma de archivo externo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ccf73563-f0f8-4397-ba96-7c5727562acd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 86%

---

# Extracción de archivos{#extract-file}

## Descripción {#description}

![](assets/export.png)

La actividad **[!UICONTROL Extract file]** permite exportar datos desde Adobe Campaign en forma de archivo externo.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad.

>[!CAUTION]
>
>La actividad **[!UICONTROL Extract file]** debe colocarse después de una actividad **[!UICONTROL Query]** para poder utilizarse.

**Temas relacionados:**

* [Caso de uso: Exportación de perfiles en un archivo externo](../../automating/using/exporting-profiles-in-file.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Extract file]** en el flujo de trabajo.

   ![](assets/wkf_data_export1.png)

1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Introduzca la etiqueta del **archivo de salida**. La etiqueta del archivo se completará automáticamente con la fecha y hora en que se creó para que sea única. Por ejemplo: recipients_20150815_081532.txt para un archivo generado el 15 de agosto de 2015 a las 08.08 horas:15:32.

   >[!NOTE]
   >
   >Es posible utilizar la función **[!UICONTROL formatDate]** en este campo para especificar el nombre del archivo.

1. Si lo desea, puede comprimir el archivo de salida seleccionando **[!UICONTROL Compression]** en el campo **[!UICONTROL Add a post-processing stage]**. El archivo de salida se comprimirá en un archivo GZIP (.gz).

   La variable **[!UICONTROL Add a post-processing stage]** también permite cifrar un archivo antes de extraerlo. Para obtener más información sobre cómo trabajar con archivos cifrados, consulte [esta sección](../../automating/using/managing-encrypted-data.md)

1. Haga clic en el **[!UICONTROL Create element]** para añadir una columna de salida.

   ![](assets/wkf_data_export2.png)

   Se abrirá una nueva ventana.

   ![](assets/wkf_data_export3.png)

1. Introduzca una expresión. Para ello, puede seleccionar una expresión existente o crear una nueva mediante el **editor de expresiones**.
1. Confirme su expresión.

   La expresión se agrega a las columnas de salida.

1. Cree tantas columnas como necesite. Puede editar las columnas haciendo clic en sus expresiones y etiquetas.

   Si va a exportar perfiles y desea utilizarlos en una herramienta externa, asegúrese de exportar un identificador único. De forma predeterminada, no todos los perfiles tienen un identificador único, según la forma en que se agreguen a la base de datos. Para obtener más información, consulte la sección [Generación de un ID único para perfiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

1. Haga clic en la pestaña **[!UICONTROL File structure]** para configurar los formatos de salida, fecha y número del archivo que se exportará.

   Marque la opción **[!UICONTROL Export labels instead of internal values of enumerations]** en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas, que son fáciles de entender, en lugar de identificadores.

1. En la pestaña **[!UICONTROL Properties]**, seleccione la opción **[!UICONTROL Do not generate a file if the inbound transition is empty]** para evitar la creación y carga de archivos vacíos en los servidores SFTP si la transición de entrada está vacía.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

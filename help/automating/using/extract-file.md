---
title: Extraer archivo
description: La actividad de extracción de archivos permite exportar datos de Adobe Campaign en forma de archivo externo.
page-status-flag: nunca activado
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: gestión de datos-actividades
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Extraer archivo{#extract-file}

## Descripción {#description}

![](assets/export.png)

La **[!UICONTROL Extract file]** actividad le permite exportar datos de Adobe Campaign en forma de archivo externo.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad.

>[!CAUTION]
>
>La **[!UICONTROL Extract file]** actividad debe colocarse después de una **[!UICONTROL Query]** actividad para poder utilizarse.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Extract file]** actividad en el flujo de trabajo.

   ![](assets/wkf_data_export1.png)

1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Introduzca la etiqueta del archivo **** Output. La etiqueta del archivo se completará automáticamente con la fecha y hora en que se creó para que sea única.  Por ejemplo: destinatarios_20150815_081532.txt para un archivo generado el 15 de agosto de 2015 a las 08:15:32.

   >[!NOTE]
   >
   >Es posible utilizar la **[!UICONTROL formatDate]** función de este campo para especificar el nombre del archivo.

1. Si lo desea, puede comprimir el archivo de salida seleccionando **[!UICONTROL Compression]** en el **[!UICONTROL Add a pre-processing step]** campo. El archivo de salida se comprimirá en un archivo GZIP (.gz).
1. Haga clic en el botón ![](assets/add_darkgrey-24px.png) o **[!UICONTROL Add an element]** para agregar una columna de salida.

   ![](assets/wkf_data_export2.png)

   Se abrirá una nueva ventana.

   ![](assets/wkf_data_export3.png)

1. Introduzca una expresión. Para ello, puede seleccionar una expresión existente o crear una nueva mediante el editor **de** expresiones.
1. Confirme la expresión.

   La expresión se agrega a las columnas de salida.

1. Cree tantas columnas como necesite. Puede editar las columnas haciendo clic en sus expresiones y etiquetas.

   Si va a exportar perfiles y desea utilizarlos en una herramienta externa, asegúrese de exportar un identificador único. De forma predeterminada, no todos los perfiles tienen un identificador único, según la forma en que se agreguen a la base de datos. Para obtener más información, consulte la sección [Generación de un ID único para perfiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) .

1. Haga clic en la **[!UICONTROL File structure]** ficha para configurar los formatos de salida, fecha y número del archivo que se exportará.

   Marque la **[!UICONTROL Export labels instead of internal values of enumerations]** opción en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas que son fáciles de entender en lugar de identificadores.

1. En la **[!UICONTROL Properties]** ficha, seleccione la **[!UICONTROL Do not generate a file if the inbound transition is empty]** opción para evitar la creación y carga de archivos vacíos en servidores SFTP si la transición de entrada está vacía.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo ilustra cómo configurar una **[!UICONTROL Extract file]** actividad después de una **[!UICONTROL Query]** actividad.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos se puedan utilizar fuera de Adobe Campaign.

1. Arrastre y suelte una **[!UICONTROL Extract file]** actividad en el flujo de trabajo y colóquela después de la **[!UICONTROL Query]** actividad.

   En este ejemplo, la consulta se realiza en todos los perfiles de edades comprendidas entre 18 y 30 años.

1. Abra la actividad del archivo Extraer para editarlo.
1. Asigne un nombre al archivo de salida.
1. Agregue columnas de salida.

   En este ejemplo, el correo electrónico, la edad, la fecha de nacimiento, el nombre y los apellidos de los perfiles se agregan como columnas de salida.

   ![](assets/wkf_data_export6.png)

1. Haga clic en la **[!UICONTROL File structure]** ficha para definir:

   * Formato de salida CSV

      ![](assets/wkf_data_export7.png)

   * Formato de fecha

      ![](assets/wkf_data_export9.png)

1. Confirme la actividad.
1. Arrastre y suelte una **[!UICONTROL Transfer file]** actividad después de la **[!UICONTROL Extract file]** actividad para recuperar el archivo de extracción en una cuenta externa.
1. Abra la actividad y elija la **[!UICONTROL File upload]** acción.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.


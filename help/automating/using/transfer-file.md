---
title: Transferir archivo
description: La actividad Transferir archivo le permite recibir o enviar archivos, probar si hay archivos presentes o enumerar archivos en Adobe Campaign.
page-status-flag: nunca activado
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: gestión de datos-actividades
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Transferir archivo{#transfer-file}

## Descripción {#description}

![](assets/file_transfer.png)

La **[!UICONTROL Transfer file]** actividad le permite recibir o enviar archivos, probar si hay archivos presentes o mostrar archivos en Adobe Campaign.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad. El archivo que se va a cargar puede ser una lista de contactos, por ejemplo.

Puede utilizar esta actividad para recuperar datos que luego se estructurarán con la **[!UICONTROL Load file]** actividad.

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Transfer file]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Utilice la lista desplegable del **[!UICONTROL Action]** campo para seleccionar una de las siguientes acciones de actividad:

   ![](assets/wkf_file_transfer_01.png)

   * **Descarga** de archivos: permite descargar un archivo.
   * **Carga** de archivos: permite cargar un archivo. Al cargar un archivo desde el archivo de Adobe Campaign, se genera una entrada de registro en el **[!UICONTROL Export audits]** menú. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md) .
   * **Compruebe si existe** un archivo: permite comprobar si hay un archivo.
   * **Lista** de archivos: le permite enumerar los archivos presentes en Adobe Campaign.
   Según la acción seleccionada, hay uno o varios protocolos disponibles:

   * **HTTP**: este protocolo le permite empezar a descargar un archivo desde una cuenta externa o desde una dirección URL.

      * Haga clic en la **[!UICONTROL Use connection parameters defined in an external account]** opción, luego seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_03.png)

      * Haga clic en la **[!UICONTROL Quick configuration]** opción y, a continuación, introduzca la URL en el campo que aparece.

         ![](assets/wkf_file_transfer_04.png)
   * **S3**: este protocolo le permite empezar a descargar un archivo desde una dirección URL o una cuenta externa a través de Amazon Simple Storage Service (S3).

      * Seleccione la cuenta externa y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: este protocolo le permite empezar a descargar un archivo desde una dirección URL o una cuenta externa.

      * Haga clic en la **[!UICONTROL Use connection parameters defined in an external account]** opción, luego seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Se admiten comodines.

      * Haga clic en la **[!UICONTROL Quick configuration]** opción y, a continuación, introduzca la URL en el campo que aparece.
      * Si desea ordenar los archivos importados, seleccione la **[!UICONTROL Sort alphanumerically]** opción en la **[!UICONTROL Additional options]** sección . Los archivos se procesarán en orden secuencial.

         ![](assets/wkf_file_transfer_sort.png)
   * **Archivos presentes en el servidor** de Adobe Campaign: este protocolo corresponde al repositorio que contiene los archivos que se van a recuperar.

      Metacaracteres o comodines (por ejemplo, * o ?) puede utilizarse para filtrar archivos.

      Rellene este campo y confirme su actividad para utilizar este protocolo.

      >[!NOTE]
      >
      >La ruta debe ser relativa al directorio de espacio de almacenamiento del servidor de Adobe Campaign. Los archivos se encuentran en el directorio **sftp&lt;yourinstancename&gt;/** . Tampoco puede examinar los directorios situados encima del espacio de almacenamiento.  Por ejemplo: **user&lt;yourinstancename&gt;/my_recipients.csv** es correcto. **../hello/my_recipients.csv** no es correcto. **/myserver/hello/myrecipients.csv** no es correcto.
   Seleccione el protocolo y complete los campos asociados.

   La **[!UICONTROL Use a dynamic file path]** opción, disponible para cada protocolo, permite utilizar una expresión estándar y variables de eventos para personalizar el nombre del archivo que se va a transferir. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

1. La **[!UICONTROL Additional options]** sección, disponible en función del protocolo seleccionado, le permite agregar parámetros al protocolo. Se puede:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:: esta opción está disponible al seleccionar la **[!UICONTROL File listing]** acción. Permite indexar todos los archivos presentes en el servidor en la variable de evento **vars.filenames** en la que los nombres de archivo están separados por los caracteres **'n'** .

1. La **[!UICONTROL If no files are found]** sección de la **[!UICONTROL Advanced options]** ficha permite configurar acciones específicas si se detectan errores o archivos inexistentes al iniciar la actividad.

   También puede definir reintentos. Los distintos reintentos aparecen en el registro de ejecución del flujo de trabajo.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Configuración de la histórica {#historization-settings}

Cada vez que se ejecuta una **[!UICONTROL Transfer file]** actividad, almacena los archivos cargados o descargados en una carpeta dedicada. Se crea una carpeta para cada actividad **[!UICONTROL Transfer file]** de un flujo de trabajo. Por lo tanto, es importante poder limitar el tamaño de esta carpeta para conservar el espacio físico en el servidor.

Para ello, puede definir **[!UICONTROL Historization settings]** en el **[!UICONTROL Advanced options]** de la **[!UICONTROL Transfer File]** actividad.

**[!UICONTROL Historization settings]** permite definir un número máximo de archivos o un tamaño total para la carpeta de la actividad. De forma predeterminada, se autorizan 100 archivos y 50 MB.

Cada vez que se ejecuta la actividad, la carpeta se comprueba de la siguiente manera:

* Solo se tienen en cuenta los archivos creados más de 24 horas antes de la ejecución de la actividad.
* Si el número de archivos que se tiene en cuenta es mayor que el valor del **[!UICONTROL Maximum number of files]** parámetro, se eliminarán los archivos más antiguos hasta que se alcance el valor **[!UICONTROL Maximum number of files]** permitido.
* Si el tamaño total de los archivos que se tienen en cuenta es mayor que el valor del **[!UICONTROL Maximum size (in MB)]** parámetro, se eliminarán los archivos más antiguos hasta que se alcance el valor **[!UICONTROL Maximum size (in MB)]** permitido.

>[!NOTE]
Si la actividad no se vuelve a ejecutar, su carpeta no se comprobará ni depurará. Con esto en mente, tenga cuidado al transferir archivos grandes.

## Ejemplo {#example}

En el siguiente ejemplo se muestra la configuración de una actividad de transferencia **de** archivos que luego irá seguida de una actividad de archivo **de** carga y luego de una actividad de **actualización de datos** . El objetivo de este flujo de trabajo es agregar o actualizar los perfiles de base de datos de Adobe Campaign con los datos recuperados por el flujo de trabajo.

1. Arrastre y suelte una actividad de archivo **** Transferir en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. En la **[!UICONTROL Protocol]** ficha, seleccione **SFTP**.
1. Seleccione la opción **Usar parámetros de conexión definidos en una cuenta** externa.
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la ruta **de archivo en el servidor** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme la actividad y guarde el flujo de trabajo.


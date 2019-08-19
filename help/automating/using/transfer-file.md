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
source-git-commit: 4fe36a1747aca69e8857cf415593086781947a47

---


# Transferir archivo{#transfer-file}

## Descripción {#description}

![](assets/file_transfer.png)

La **[!UICONTROL Transfer file]** actividad le permite recibir o enviar archivos, comprobar si existen archivos presentes o de lista en Adobe Campaign.

## Contexto de uso {#context-of-use}

La manera en que se extraerán los datos se define cuando se configura la actividad. El archivo que se carga puede ser una lista de contactos, por ejemplo.

Puede utilizar esta actividad para recuperar datos que luego estarán estructurados con **[!UICONTROL Load file]** la actividad.

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Transfer file]** actividad en el flujo de trabajo.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.
1. Utilice la lista desplegable del **[!UICONTROL Action]** campo para seleccionar una de las siguientes acciones de actividad:

   ![](assets/wkf_file_transfer_01.png)

   * **Descarga de archivo**: permite descargar un archivo.
   * **Carga de archivos**: permite cargar un archivo. Al cargar un archivo desde un archivo de Adobe Campaign, se genera una entrada de registro en **[!UICONTROL Export audits]** el menú. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditar exportaciones](../../administration/using/auditing-export-logs.md) .
   * **Pruebe si existe el archivo**: le permite comprobar si hay un archivo.
   * **Listado de archivos**: permite enumerar los archivos presentes en Adobe Campaign.
   Según la acción seleccionada, hay disponibles uno o varios protocolos:

   * **HTTP**: este protocolo permite descargar un archivo desde una cuenta externa o desde una dirección URL.

      * Haga clic en **[!UICONTROL Use connection parameters defined in an external account]** la opción y, a continuación, seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_03.png)

      * Haga clic en la **[!UICONTROL Quick configuration]** opción y, a continuación, introduzca la URL en el campo que aparece.

         ![](assets/wkf_file_transfer_04.png)
   * **S 3**: este protocolo le permite empezar a descargar un archivo desde una URL o una cuenta externa mediante Amazon Simple Storage Service (S 3).

      * Seleccione la cuenta externa y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: este protocolo le permite empezar a descargar un archivo desde una dirección URL o una cuenta externa.

      * Haga clic en **[!UICONTROL Use connection parameters defined in an external account]** la opción y, a continuación, seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Se admiten comodines.

      * Haga clic en la **[!UICONTROL Quick configuration]** opción y, a continuación, introduzca la URL en el campo que aparece.
      * Si desea ordenar los archivos importados, seleccione **[!UICONTROL Sort alphanumerically]** la opción de **[!UICONTROL Additional options]** la sección. Los archivos se procesarán en orden secuencial.

         ![](assets/wkf_file_transfer_sort.png)
   * **Archivos presentes en el servidor de Adobe Campaign**: este protocolo corresponde al repositorio que contiene los archivos que se deben recuperar.

      Metacaracteres o comodines (por ejemplo, * o?) puede utilizarse para filtrar archivos.

      Complete este campo y confirme su actividad para utilizar este protocolo.

      >[!NOTE]
      >
      >La ruta debe ser relativa al directorio de espacio de almacenamiento del servidor de Adobe Campaign. Los archivos se encuentran en **sftp &lt; yourinstancename &gt;/** directory. Tampoco puede examinar los directorios por encima del espacio de almacenamiento. Por ejemplo: **user &lt; yourinstancename &gt;/my_ recipients. csv** es correcto. **../hello/my_recipients.csv** es incorrecto. **//myserver/hello/myrecipients.csv** es incorrecto.
   Seleccione el protocolo y complete los campos asociados.

   La **[!UICONTROL Use a dynamic file path]** opción, disponible para cada protocolo, permite utilizar variables estándar de expresión y eventos para personalizar el nombre del archivo que se va a transferir. Para obtener más información, consulte la [sección Personalización de actividades con](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) variables de eventos.

1. La **[!UICONTROL Additional options]** sección, disponible según el protocolo seleccionado, permite agregar parámetros al protocolo. Puede:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: esta opción está disponible al seleccionar **[!UICONTROL File listing]** la acción. Permite indexar todos los archivos presentes en el servidor en la variable de evento **vars. filennames** en la que los nombres de los archivos están separados **por** los caracteres'n '.

1. La **[!UICONTROL If no files are found]** sección de **[!UICONTROL Advanced options]** la ficha permite configurar acciones específicas si se detectan errores o archivos inexistentes cuando se inicia la actividad.

   También puede definir reintentos. Los diferentes reintentos aparecen en el registro de ejecución del flujo de trabajo.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Configuración de la historización {#historization-settings}

Cada vez que se ejecuta una **[!UICONTROL Transfer file]** actividad, almacena los archivos cargados o descargados en una carpeta dedicada. Se crea una carpeta para cada **[!UICONTROL Transfer file]** actividad de un flujo de trabajo. Por lo tanto, es importante poder limitar el tamaño de esta carpeta para conservar el espacio físico en el servidor.

Para ello, puede definir **[!UICONTROL Historization settings]** en la **[!UICONTROL Advanced options]****[!UICONTROL Transfer File]** actividad.

**[!UICONTROL Historization settings]** permitir definir un número máximo de archivos o el tamaño total de la carpeta de la actividad. De forma predeterminada, se autorizan 100 archivos y 50 MB.

Cada vez que se ejecuta la actividad, la carpeta se comprueba de la siguiente manera:

* Solo se tienen en cuenta los archivos creados más de 24 horas antes de la ejecución de la actividad.
* Si el número de archivos teniendo en cuenta el valor es mayor que el valor del **[!UICONTROL Maximum number of files]** parámetro, los archivos más antiguos se eliminarán hasta que se llegue al **[!UICONTROL Maximum number of files]** permitido.
* Si el tamaño total de los archivos teniendo en cuenta el valor es mayor que el valor del **[!UICONTROL Maximum size (in MB)]** parámetro, los archivos más antiguos se eliminarán hasta que se llegue al **[!UICONTROL Maximum size (in MB)]** permitido.

>[!NOTE]
Si la actividad no vuelve a ejecutarse, su carpeta no se revisará ni se purgará. Tenga en cuenta esto, tenga cuidado al transferir archivos de gran tamaño.

## Ejemplo {#example}

El siguiente ejemplo muestra la configuración de una **actividad de transferencia** de archivos que después estará seguida por una actividad **de archivo** Load, luego una actividad **de actualización de datos** . El objetivo de este flujo de trabajo es agregar o actualizar los perfiles de base de datos de Adobe Campaign con los datos recuperados por el flujo de trabajo.

1. Arrastre y suelte una **actividad de transferencia** de archivos en el flujo de trabajo.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.
1. En la **[!UICONTROL Protocol]** ficha, seleccione **SFTP**.
1. Seleccione los **parámetros de conexión definidos en una opción de cuenta** externa.
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la ruta **File en el servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme su actividad y guarde el flujo de trabajo.


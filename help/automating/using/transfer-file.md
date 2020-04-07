---
title: Transferir archivo
description: La actividad Transferir archivo permite recibir o enviar archivos, probar si hay archivos presentes o archivos de lista en Adobe Campaign.
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7f203ff0e635faf802a5577f761dc308dae4ab66

---


# Transferir archivo{#transfer-file}

## Descripción {#description}

![](assets/file_transfer.png)

La **[!UICONTROL Transfer file]** actividad le permite recibir o enviar archivos, probar si hay archivos presentes o archivos de lista en Adobe Campaign.

## Contexto de uso {#context-of-use}

La forma en que se extraerán los datos se define al configurar la actividad. El archivo que se va a cargar puede ser una lista de contactos, por ejemplo.

Puede utilizar esta actividad para recuperar datos que luego se estructurarán con la **[!UICONTROL Load file]** actividad.

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Transfer file]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Utilice la lista desplegable del **[!UICONTROL Action]** campo para seleccionar una de las siguientes acciones de actividad:

   ![](assets/wkf_file_transfer_01.png)

   * **Descarga** de archivos: le permite descargar un archivo.
   * **Carga** de archivos: permite cargar un archivo. Al cargar un archivo desde un archivo Adobe Campaign, se genera una entrada de registro en el **[!UICONTROL Export audits]** menú. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md) .
   * **Compruebe si existe** un archivo: le permite comprobar si hay un archivo.
   * **Lista** de archivos: le permite realizar la lista de los archivos presentes en el servidor definido en la **[!UICONTROL Protocol]** ficha. Esta acción se utiliza principalmente con fines de depuración, para comprobar si la actividad está configurada según sus necesidades antes de descargar los archivos del servidor remoto.

1. Seleccione el protocolo que desee utilizar:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [almacenamiento de blob de Microsoft Azure](#azure-blob-configuration-wf)
   * [Archivos presentes en el servidor de Adobe Campaign](#files-server-configuration-wf)

1. La **[!UICONTROL Additional options]** sección, disponible en función del protocolo seleccionado, le permite agregar parámetros al protocolo. Se puede:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:: esta opción está disponible al seleccionar la acción. **[!UICONTROL File listing]** en la **[!UICONTROL General]** ficha. Permite indexar todos los archivos presentes en el servidor en la variable de evento **vars.filenames** en la que los nombres de archivo están separados por los caracteres **&#39;n&#39;** .

1. La **[!UICONTROL If no files are found]** sección de la **[!UICONTROL Advanced options]** ficha permite configurar acciones específicas si se detectan errores o archivos inexistentes al iniciar la actividad.

   También puede definir reintentos. Los diferentes reintentos aparecen en el registro de ejecución del flujo de trabajo.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

### Configuración con HTTP {#HTTP-configuration-wf}

El protocolo HTTP permite el inicio de descargar un archivo desde una cuenta externa o desde una dirección URL.

Con este procotol, puede elegir **[!UICONTROL Use connection parameters defined in an external account]** esta opción. En este caso, seleccione la cuenta que desee y especifique la ruta del archivo que desea descargar.
![](assets/wkf_file_transfer_03.png)

También puede elegir la **[!UICONTROL Quick configuration]** opción. Solo es necesario introducir la dirección URL en el campo URL.
![](assets/wkf_file_transfer_04.png)

### Configuración con SFTP {#SFTP-configuration-wf}

El protocolo SFTP permite el inicio de descargar un archivo desde una dirección URL o una cuenta externa.

Con este procotol, puede elegir la opción **[!UICONTROL Use connection parameters defined in an external account]** , luego seleccionar la cuenta que desee y especificar la ruta del archivo que desea descargar.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Se admiten comodines.

También puede elegir la **[!UICONTROL Quick configuration]** opción. Solo es necesario introducir la dirección URL en el campo URL.

### Configuración con Amazon S3 {#S3-configuration-wf}

El protocolo Amazon S3 permite el inicio de descargar un archivo desde una URL o una cuenta externa a través de Amazon Simple Almacenamiento Service (S3).

1. Seleccione una cuenta externa de Amazon S3. Para obtener más información, consulte [esta página](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

3. Especifique la ruta del archivo que desea descargar.

   ![](assets/wkf_file_transfer_08.png)

4. Si desea eliminar los archivos de origen cuando la transferencia se haya completado, marque **[!UICONTROL Delete the source files after transfer]**.

### Configuración con el almacenamiento de blob de Microsoft Azure {#azure-blob-configuration-wf}

El protocolo Blob de Microsoft Azure le permite acceder al blob ubicado en una cuenta de Almacenamiento Blob de Microsoft Azure.

1. Seleccione una **[!UICONTROL Microsoft Azure Blob]** cuenta externa. Para obtener más información, consulte [esta página](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Especifique la ruta del archivo que desea descargar; puede coincidir con varios blobs. En ese caso, la **[!UICONTROL File transfer]** actividad activará la transición saliente una vez por blob encontrado. Luego se procesarán en orden alfabético.

   >[!CAUTION]
   >
   >Los comodines no son compatibles con varios nombres de archivo. En su lugar, debe introducir un prefijo. Se admitirán todos los nombres de blob que coincidan con ese prefijo.

   A continuación encontrará una lista de los ejemplos de rutas de archivos:

   * **&quot;campaña/&quot;**: coincide con todos los blobs de la carpeta de Campañas ubicada en la raíz del contenedor.
   * **&quot;campaña/nuevo-&quot;**: coincide con todos los blobs con un nombre de archivo que empieza por &quot;new-&quot; y se encuentra en la carpeta de Campañas.
   * **&quot;&quot;**: la adición de una ruta vacía permite hacer coincidir todas las etiquetas disponibles en el contenedor.

### Configuración con archivos presentes en el servidor Adobe Campaign {#files-server-configuration-wf}

El **[!UICONTROL File(s) present on the Adobe Campaign server]** protocolo corresponde al repositorio que contiene los archivos que se van a recuperar.
Metacaracteres o comodines (por ejemplo, * o ?) se puede utilizar para filtrar archivos.

Elija si desea **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]** la **[!UICONTROL Use a dynamic file path]** opción, le permite utilizar una expresión estándar y variables de eventos para personalizar el nombre del archivo que desea transferir. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

Tenga en cuenta que la ruta debe ser relativa al directorio de espacio de almacenamiento del servidor de Adobe Campaign. Los archivos se encuentran en el directorio **sftp&lt;yourinstancename>/** . Tampoco puede examinar los directorios situados encima del espacio de almacenamiento. Por ejemplo:

    >**user&amp;lt;yourinstancename>/my_recipients.csv** es correcto.
    >
    >**../hello/my_recipients.csv** es incorrecto.
    >
    >**//myserver/hello/myrecipients.csv** es incorrecto.

## Configuración de la histórica {#historization-settings}

Cada vez que se ejecuta una **[!UICONTROL Transfer file]** actividad, almacena los archivos cargados o descargados en una carpeta dedicada. Se crea una carpeta para cada **[!UICONTROL Transfer file]** actividad de un flujo de trabajo. Por lo tanto, es importante poder limitar el tamaño de esta carpeta para conservar el espacio físico en el servidor.

Para ello, puede definir **[!UICONTROL Historization settings]** en el **[!UICONTROL Advanced options]** de la **[!UICONTROL Transfer File]** actividad.

**[!UICONTROL Historization settings]** permite definir un número máximo de archivos o un tamaño total para la carpeta de la actividad. De forma predeterminada, se autorizan 100 archivos y 50 MB.

Cada vez que se ejecuta la actividad, la carpeta se marca de la siguiente manera:

* Sólo se tienen en cuenta los archivos creados más de 24 horas antes de la ejecución de la actividad.
* Si el número de archivos que se tiene en cuenta es bueno al valor del **[!UICONTROL Maximum number of files]** parámetro, se eliminarán los archivos más antiguos hasta que se alcance el valor **[!UICONTROL Maximum number of files]** permitido.
* Si el tamaño total de los archivos que se tienen en cuenta es bueno al valor del **[!UICONTROL Maximum size (in MB)]** parámetro, se eliminarán los archivos más antiguos hasta que se alcance el valor **[!UICONTROL Maximum size (in MB)]** permitido.

>[!NOTE]
>
>Si la actividad no se vuelve a ejecutar, no se comprobará ni depurará la carpeta. Con esto en mente, tenga cuidado al transferir archivos de gran tamaño.

## Ejemplo {#example}

En el siguiente ejemplo se muestra la configuración de una actividad de transferencia **de** archivos que luego irá seguida de una actividad de archivo **de** carga y luego de una actividad de datos **de** actualización. El objetivo de este flujo de trabajo es agregar o actualizar los perfiles de la base de datos de Adobe Campaign con los datos recuperados por el flujo de trabajo.

1. Arrastre y suelte una actividad de archivo **** Transfer en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. En la **[!UICONTROL Protocol]** ficha, seleccione **SFTP**.
1. Seleccione la opción **Usar parámetros de conexión definidos en una cuenta externa** .
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la ruta **de archivo en el servidor** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme la actividad y guarde el flujo de trabajo.


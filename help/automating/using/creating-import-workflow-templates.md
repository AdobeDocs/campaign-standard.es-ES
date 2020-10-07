---
title: Creación de plantillas de flujo de trabajo para importar datos
description: Obtenga información sobre cómo crear plantillas de flujo de trabajo para importar datos.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 58%

---


# Creación de plantillas de flujo de trabajo para importar datos {#import-workflow-template}

La utilización de una plantilla de importación es una práctica recomendada si necesita importar con regularidad archivos con la misma estructura.

Este ejemplo muestra cómo se puede predefinir un flujo de trabajo para reutilizarlo a la hora de importar perfiles provenientes de un CRM en la base de datos de Adobe Campaign.

1. Cree una nueva plantilla de flujo de trabajo desde **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Añada las siguientes actividades:

   * **[!UICONTROL Load file]**: Defina la estructura esperada del archivo que contiene los datos que se van a importar.

      >[!NOTE]
      >
      >Sólo puede importar datos de un solo archivo. Si el flujo de trabajo tiene varias **[!UICONTROL Load file]** actividades, se utilizará el mismo archivo cada vez.

   * **[!UICONTROL Reconciliation]**: Reconcilie los datos importados con los datos de la base de datos.
   * **[!UICONTROL Segmentation]**: Cree filtros para procesar registros de formas diferentes, dependiendo de si se podrían reconciliar o no.
   * **[!UICONTROL Deduplication]**: Deduplique los datos del archivo entrante antes de insertarlos en la base de datos.
   * **[!UICONTROL Update data]**: Actualice la base de datos con los perfiles importados.

   ![](assets/import_template_example0.png)

1. Configure la actividad **[!UICONTROL Load file]**:

   * Cargue un archivo de muestra para definir la estructura que desee. El archivo de muestra debe contener tan solo unas pocas líneas, pero todas las columnas necesarias para la importación. Compruebe y edite el formato del archivo para asegurarse de que el tipo de cada columna está correctamente definido: texto, fecha, entero, etc. Por ejemplo:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * En la sección **[!UICONTROL File to load]** , seleccione **[!UICONTROL Upload a new file from the local machine]** y deje el campo en blanco. Cada vez que cree un nuevo flujo de trabajo a partir de esta plantilla, puede especificar aquí el archivo que desee, siempre que se corresponda con la estructura definida.

      Puede utilizar cualquiera de las opciones, pero debe modificar la plantilla según corresponda. Por ejemplo, si selecciona **[!UICONTROL Use the file specified in the inbound transition]**, puede añadir una actividad de **[!UICONTROL Transfer file]** antes de recuperar el archivo de importación de un servidor FTP/SFTP.

      Si desea que los usuarios puedan descargar un archivo que contenga errores producidos durante una importación, marque la **[!UICONTROL Keep the rejects in a file]** opción y especifique la **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure la actividad **[!UICONTROL Reconciliation]**. El objetivo de esta actividad en este contexto es identificar los datos entrantes.

   * In the **[!UICONTROL Relations]** tab, select **[!UICONTROL Create element]** and define a link between the imported data and the recipients targeting dimension (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). En este ejemplo, el campo personalizado **CRM ID** se utiliza para crear la condición de unión. Utilice el campo o la combinación de campos que necesite siempre que permita identificar registros únicos.
   * En la pestaña **[!UICONTROL Identification]** , deje la opción **[!UICONTROL Identify the document from the working data]** sin seleccionar.

   ![](assets/import_template_example2.png)

1. Configure la actividad **[!UICONTROL Segmentation]** para recuperar los destinatarios reconciliados en una transición, y los destinatarios que no pudieron ser reconciliados, pero que tengan datos suficientes en una segunda transición.

   La transición con los destinatarios reconciliados se puede utilizar después para actualizar la base de datos. La transición con destinatarios desconocidos se puede utilizar para crear nuevas entradas de destinatario en la base de datos si en el archivo hay un conjunto mínimo de información disponible.

   Los destinatarios que no se pueden reconciliar y no tienen datos suficientes se seleccionan en una transición saliente de complemento y se pueden exportar en un archivo independiente, o sencillamente se ignoran.

   * En la **[!UICONTROL General]** ficha de la actividad, establezca el **[!UICONTROL Resource type]** valor en **[!UICONTROL Temporary resource]** y seleccione **[!UICONTROL Reconciliation]** como conjunto de objetivos.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. Si lo necesita, puede seguir procesando los datos complementarios: exportación de archivo, actualización de lista, etc.
   * In the first segment of the **[!UICONTROL Segments]** tab, add a filtering condition on the inbound population to select only records for which the profile&#39;s CRM ID is not equal to 0. De este modo, los datos del archivo que se reconcilian con perfiles de la base de datos se seleccionan en ese subconjunto.

      ![](assets/import_template_example3.png)

   * Añada un segundo segmento que seleccione registros no conciliados que tengan suficientes datos para insertar en la base de datos. Por ejemplo: dirección de correo electrónico, nombre y apellidos. Los registros no conciliados tienen el valor de ID de CRM de su perfil igual a 0.

      ![](assets/import_template_example3_2.png)

   * Todos los registros que no están seleccionados en los dos primeros subconjuntos se seleccionan en la **[!UICONTROL Complement]**.

1. Configure la actividad **[!UICONTROL Update data]** ubicada después de la primera transición saliente de la actividad **[!UICONTROL Segmentation]** configurada anteriormente.

   * Seleccione **[!UICONTROL Update]** como **[!UICONTROL Operation type]**, ya que la transición de entrada solo contiene destinatarios ya presentes en la base de datos.
   * En la **[!UICONTROL Identification]** ficha, seleccione **[!UICONTROL Using reconciliation criteria]** y defina una clave entre la **[!UICONTROL Dimension to update]** -Perfiles en este caso- y el vínculo creado en la **[!UICONTROL Reconciliation]** actividad. En este ejemplo, se utiliza el campo personalizado **CRM ID**.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si los nombres de las columnas del archivo son idénticos o casi idénticos a los nombres de los campos de dimensión de los destinatarios, puede utilizar el botón de varita mágica para hacer coincidir automáticamente los diferentes campos.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si planea enviar correos directos a estos perfiles, asegúrese de incluir una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de que la **[!UICONTROL Address specified]** casilla de la información de sus perfiles esté marcada. Para actualizar esta opción desde un flujo de trabajo, simplemente agregue un elemento a los campos para actualizar, especifique **1** como **[!UICONTROL Source]** y seleccione el `postalAddress/@addrDefined` campo como **[!UICONTROL Destination]**. Para obtener más información sobre el correo directo y el uso de la **[!UICONTROL Address specified]** opción, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * En la **[!UICONTROL Properties]** ficha, establezca la **[!UICONTROL Resource type]** en el recurso temporal generado a partir de la **[!UICONTROL Reconciliation]** actividad del flujo de trabajo.

      ![](assets/import_template_example4.png)

   * En este ejemplo, el campo de correo electrónico se utiliza para buscar perfiles únicos. Puede utilizar cualquier campo que esté rellenado y que forme parte de una combinación única.
   * Elija un **[!UICONTROL Deduplication method]**. En este caso, la solicitud decide automáticamente qué registros se conservan en caso de duplicado.

   ![](assets/import_template_example7.png)

1. Configure la actividad **[!UICONTROL Update data]** ubicada después de la actividad **[!UICONTROL Deduplication]** configurada anteriormente.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * En la **[!UICONTROL Identification]** ficha, seleccione **[!UICONTROL Using reconciliation criteria]** y defina una clave entre la **[!UICONTROL Dimension to update]** -Perfiles en este caso- y el vínculo creado en la **[!UICONTROL Reconciliation]** actividad. En este ejemplo, se utiliza el campo personalizado **CRM ID**.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si los nombres de las columnas del archivo son idénticos o casi idénticos a los nombres de los campos de dimensión de los destinatarios, puede utilizar el botón de varita mágica para hacer coincidir automáticamente los diferentes campos.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si planea enviar correos directos a estos perfiles, asegúrese de incluir una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de que la **[!UICONTROL Address specified]** casilla de la información de sus perfiles esté marcada. Para actualizar esta opción desde un flujo de trabajo, simplemente agregue un elemento a los campos para actualizar, especifique **1** como **[!UICONTROL Source]** y seleccione el campo **[postalAddress/@addrDefined]** como **[!UICONTROL Destination]**. Para obtener más información sobre el correo directo y el uso de la **[!UICONTROL Address specified]** opción, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Después de la tercera transición de la actividad **[!UICONTROL Segmentation]**, añada una actividad **[!UICONTROL Extract file]** y una actividad **[!UICONTROL Transfer file]** si desea realizar un seguimiento de los datos que no se insertan en la base de datos. Configure las actividades para exportar la columna que necesite y para transferir el archivo en un servidor FTP o SFTP desde donde pueda recuperarlo.
1. Añada una actividad **[!UICONTROL End]** y guarde la plantilla de flujo de trabajo.

Ahora la plantilla se puede utilizar y está disponible para cada nuevo flujo de trabajo. A continuación, es necesario especificar el archivo que contiene los datos que se van a importar en la actividad **[!UICONTROL Load file]** .

![](assets/import_template_example9.png)

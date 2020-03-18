---
title: Importación de datos
description: Obtenga información sobre cómo importar datos con un flujo de trabajo.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ca603abd9b4ef1a9272a89acb62dee545b76114

---


# Importación de datos{#importing-data}

## Recopilación de datos {#collecting-data}

Puede recopilar datos de un archivo para procesarlos o importarlos en la base de datos de Adobe Campaign.

* La **[!UICONTROL Load file]** actividad permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign. Los datos se importan temporalmente y es necesaria otra actividad para integrarlos definitivamente en la base de datos de Adobe Campaign.

   For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).

* La **[!UICONTROL Transfer file]** actividad le permite recibir o enviar archivos, probar si hay archivos presentes o enumerar archivos en Adobe Campaign.
Puede utilizar esta actividad antes de una **[!UICONTROL Load file]** en caso de que necesite recuperar el archivo de una fuente externa.

   For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

## Prácticas recomendadas de importación {#import-best-practices}

Tenga cuidado y siga las sencillas reglas detalladas debajo, ya que le pueden ayudar a garantizar la coherencia de los datos en la base de datos y a evitar errores comunes durante la actualización o las exportaciones de datos.

### Uso de plantillas de importación {#using-import-templates}

La mayoría de los flujos de trabajo de importación deben contener las siguientes actividades: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

El uso de plantillas de importación facilita la preparación de importaciones similares y la coherencia de los datos en la base de datos.

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. Los duplicados aparecen en ocasiones al importar archivos diferentes. En este caso, la deduplicación resulta difícil. Por lo tanto, la deduplicación es una buena precaución en todos los flujos de trabajo de importación.

No dé por hecho que los datos entrantes son coherentes y correctos, o que el departamento de TI o el iniciador de Adobe Campaign se pueden encargar de ello. Durante el proyecto, tenga en cuenta la limpieza de los datos. Deduplique, reconcilie y mantenga la coherencia al importar datos.

En el [ejemplo encontrará un ejemplo de una plantilla de flujo de trabajo genérica diseñada para importar datos: Importar la sección de plantillas](#example--import-workflow-template) de flujo de trabajo.

>[!NOTE]
>
>También puede utilizar plantillas [de](../../automating/using/importing-data-with-import-templates.md)importación. Son plantillas de flujo de trabajo definidas por un administrador que, una vez activadas, solo ofrecen la posibilidad de especificar el archivo que contiene los datos que se van a importar.

**Temas relacionados:**

* [Cargar actividad de archivo](../../automating/using/load-file.md)
* [Actividad de reconciliación](../../automating/using/reconciliation.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Actividad de desduplicación](../../automating/using/deduplication.md)
* [Actualizar actividad de datos](../../automating/using/update-data.md)

### Uso de formatos de archivo plano {#using-flat-file-formats}

El formato más eficaz para las importaciones es un archivo plano. Los archivos planos se pueden importar en modo masivo a nivel de base de datos.

Por ejemplo:

* Separador: tabulación o punto y coma
* Primera línea con encabezados
* Sin delimitador de cadenas
* Formato de fecha: AAAA/MM/DD HH:mm:SS

Ejemplo del archivo que se va a importar:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Uso de compresión {#using-compression}

Utilice archivos comprimidos para importar y exportar cuando sea posible. GZIP es compatible de forma predeterminada. Puede agregar el preprocesamiento al importar archivos o el posprocesamiento al extraer datos, respectivamente, en las actividades **[!UICONTROL Load file]** y **[!UICONTROL Extract file]** del flujo de trabajo.

**Temas relacionados:**

* [Cargar actividad de archivo](../../automating/using/load-file.md)
* [Extraer actividad de archivo](../../automating/using/extract-file.md)

### Importación en modo Delta {#importing-in-delta-mode}

Las importaciones regulares deben realizarse en modo delta. Esto significa que solo se envían datos modificados o nuevos a Adobe Campaign, en lugar de toda la tabla de una sentada.

Las importaciones completas deben utilizarse únicamente para la carga inicial.

### Mantenimiento de la coherencia {#maintaining-consistency}

Para mantener la coherencia de los datos en la base de datos de Adobe Campaign, siga los principios siguientes:

* Si los datos importados coinciden con una tabla de referencia de Adobe Campaign, se deben reconciliar con esa tabla en el flujo de trabajo. Los registros que no coinciden deben ser rechazados.
* Asegúrese de que los datos importados siempre estén **“normalizados”** (correo electrónico, número de teléfono, dirección de correo postal) y que esta normalización sea fiable y no cambie con los años. Si no es así, es probable que algunos duplicados aparezcan en la base de datos y, como Adobe Campaign no proporciona herramientas para establecer correspondencias “difusas”, resulta muy difícil administrarlos y eliminarlos.
* Los datos de transacciones deben tener una clave de reconciliación y se deben reconciliar con los datos existentes para evitar la creación de duplicados.
* **Importación de archivos relacionados en orden**. Si la importación está compuesta por varios archivos que dependen unos de otros, el flujo de trabajo debe asegurar que los archivos se importen en el orden correcto. Si un archivo falla, los demás archivos no se importan.
* **Deduplique**, reconcilie y mantenga la coherencia al importar datos.

## Administración de datos cifrados {#managing-encrypted-data}

En algunos casos, es posible que los datos que desea importar los servidores de campañas deban cifrarse, por ejemplo, si contienen datos PII.

Para poder importar o exportar archivos cifrados, primero debe ponerse en contacto con el Servicio de atención al cliente de Adobe para que le proporcionen a su instancia los comandos de cifrado y descifrado necesarios.

Para ello, envíe una solicitud que indique:

* La **etiqueta** que se mostrará en la interfaz de Campaign para utilizar el comando. Por ejemplo, &quot;Cifrar archivo&quot;.
* El **comando** que se va a instalar en la instancia.
Por ejemplo, para descifrar un archivo con PGP, el comando será:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Una vez procesada la solicitud, los comandos de cifrado/descifrado estarán disponibles en el **!UICONTROL Pre-processing stage]** campo desde las **[!UICONTROL Load file]** actividades y **[!UICONTROL Extract file]** . Puede utilizarlos para descifrar o cifrar los archivos que desea importar o exportar.

![](assets/preprocessing-encryption.png)

**Temas relacionados:**

* [Cargar archivo](../../automating/using/load-file.md)
* [Extraer archivo](../../automating/using/extract-file.md)

## Creación de una plantilla de flujo de trabajo para importar datos {#example--import-workflow-template}

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

1. Configure la **[!UICONTROL Load file]** actividad:

   * Cargue un archivo de muestra para definir la estructura que desee. El archivo de muestra debe contener tan solo unas pocas líneas, pero todas las columnas necesarias para la importación. Compruebe y edite el formato del archivo para asegurarse de que el tipo de cada columna está correctamente definido: texto, fecha, entero, etc. Por ejemplo:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * En la **[!UICONTROL File to load]** sección, seleccione **[!UICONTROL Upload a new file from the local machine]** y deje el campo en blanco. Cada vez que cree un nuevo flujo de trabajo a partir de esta plantilla, puede especificar aquí el archivo que desee, siempre que se corresponda con la estructura definida.

      Puede utilizar cualquiera de las opciones, pero debe modificar la plantilla según corresponda. For example, if you select **[!UICONTROL Use the file specified in the inbound transition]**, you can add a **[!UICONTROL Transfer file]** activity before to retrieve the file to import from a FTP/SFTP server.

      Si desea que los usuarios puedan descargar un archivo que contenga errores producidos durante una importación, marque la **[!UICONTROL Keep the rejects in a file]** opción y especifique la **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure la **[!UICONTROL Reconciliation]** actividad. El objetivo de esta actividad en este contexto es identificar los datos entrantes.

   * En la **[!UICONTROL Relations]** ficha, seleccione **[!UICONTROL Create element]** y defina un vínculo entre los datos importados y la dimensión de objetivo de destinatarios (consulte [Segmentación de dimensiones y recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). En este ejemplo, el campo personalizado **CRM ID** se utiliza para crear la condición de unión. Utilice el campo o la combinación de campos que necesite siempre que permita identificar registros únicos.
   * En la **[!UICONTROL Identification]** ficha, deje la **[!UICONTROL Identify the document from the working data]** opción sin marcar.
   ![](assets/import_template_example2.png)

1. Configure the **[!UICONTROL Segmentation]** activity to retrieve reconciled recipients in one transition and recipients that could not be reconciled but who have enough data in a second transition.

   La transición con los destinatarios reconciliados se puede utilizar después para actualizar la base de datos. La transición con destinatarios desconocidos se puede utilizar para crear nuevas entradas de destinatario en la base de datos si en el archivo hay un conjunto mínimo de información disponible.

   Los destinatarios que no se pueden reconciliar y no tienen datos suficientes se seleccionan en una transición saliente de complemento y se pueden exportar en un archivo independiente, o sencillamente se ignoran.

   * En la **[!UICONTROL General]** ficha de la actividad, establezca el **[!UICONTROL Resource type]** en **[!UICONTROL Temporary resource]** y seleccione **[!UICONTROL Reconciliation]** como conjunto de objetivos.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. Si lo necesita, puede seguir procesando los datos complementarios: exportación de archivo, actualización de lista, etc.
   * In the first segment of the **[!UICONTROL Segments]** tab, add a filtering condition on the inbound population to select only records for which the profile&#39;s CRM ID is not equal to 0. De este modo, los datos del archivo reconciliados con perfiles de la base de datos se seleccionan en ese subconjunto.

      ![](assets/import_template_example3.png)

   * Agregue un segundo segmento que seleccione registros no conciliados que tengan suficientes datos para insertar en la base de datos. Por ejemplo: dirección de correo electrónico, nombre y apellidos. Los registros no conciliados tienen el valor de ID de CRM de su perfil igual a 0.

      ![](assets/import_template_example3_2.png)

   * Todos los registros que no están seleccionados en los dos primeros subconjuntos se seleccionan en la **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * En la **[!UICONTROL Identification]** ficha, seleccione **[!UICONTROL Using reconciliation criteria]** y defina una clave entre el vínculo **[!UICONTROL Dimension to update]** - Perfiles en este caso- y el vínculo creado en la **[!UICONTROL Reconciliation]** actividad. En este ejemplo, se utiliza el campo personalizado **CRM ID**.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si los nombres de las columnas del archivo son idénticos o casi idénticos a los nombres de los campos de dimensión de los destinatarios, puede utilizar el botón de varita mágica para hacer coincidir automáticamente los diferentes campos.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si planea enviar correos directos a estos perfiles, asegúrese de incluir una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de que la **[!UICONTROL Address specified]** casilla de la información de los perfiles está marcada. Para actualizar esta opción desde un flujo de trabajo, simplemente agregue un elemento a los campos para actualizar, especifique **1** como **[!UICONTROL Source]** y seleccione el `postalAddress/@addrDefined` campo como **[!UICONTROL Destination]**. Para obtener más información sobre el correo directo y el uso de la **[!UICONTROL Address specified]** opción, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * En la **[!UICONTROL Properties]** ficha, establezca la **[!UICONTROL Resource type]** en el recurso temporal generado a partir de la **[!UICONTROL Reconciliation]** actividad del flujo de trabajo.

      ![](assets/import_template_example4.png)

   * En este ejemplo, el campo de correo electrónico se utiliza para buscar perfiles únicos. Puede utilizar cualquier campo que esté rellenado y que forme parte de una combinación única.
   * Elija un **[!UICONTROL Deduplication method]**. En este caso, la aplicación decide automáticamente qué registros se conservan en caso de duplicados.
   ![](assets/import_template_example7.png)

1. Configure the **[!UICONTROL Update data]** activity located after the **[!UICONTROL Deduplication]** activity configured previously.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * En la **[!UICONTROL Identification]** ficha, seleccione **[!UICONTROL Using reconciliation criteria]** y defina una clave entre el vínculo **[!UICONTROL Dimension to update]** - Perfiles en este caso- y el vínculo creado en la **[!UICONTROL Reconciliation]** actividad. En este ejemplo, se utiliza el campo personalizado **CRM ID**.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si los nombres de las columnas del archivo son idénticos o casi idénticos a los nombres de los campos de dimensión de los destinatarios, puede utilizar el botón de varita mágica para hacer coincidir automáticamente los diferentes campos.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si planea enviar correos directos a estos perfiles, asegúrese de incluir una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de que la **[!UICONTROL Address specified]** casilla de la información de los perfiles está marcada. Para actualizar esta opción desde un flujo de trabajo, simplemente agregue un elemento a los campos para actualizar, especifique **1** como **[!UICONTROL Source]** y seleccione el campo **[postalAddress/@addrDefined]** como **[!UICONTROL Destination]**. Para obtener más información sobre el correo directo y el uso de la **[!UICONTROL Address specified]** opción, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. After the third transition of the **[!UICONTROL Segmentation]** activity, add a **[!UICONTROL Extract file]** activity and a **[!UICONTROL Transfer file]** activity if you want to keep track of data not inserted in the database. Configure las actividades para exportar la columna que necesite y para transferir el archivo en un servidor FTP o SFTP desde donde pueda recuperarlo.
1. Add an **[!UICONTROL End]** activity and save the workflow template.

Ahora la plantilla se puede utilizar y está disponible para cada nuevo flujo de trabajo. All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)

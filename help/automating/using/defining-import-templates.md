---
title: Definición de plantillas de importación
description: Las Plantillas de importación permiten reducir la configuración necesaria e importar datos más rápido.
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Definición de plantillas de importación{#defining-import-templates}

Las Plantillas de importación permiten al administrador definir previamente un determinado número de configuraciones técnicas de importación. Estas plantillas se pueden poner a disposición de los usuarios estándar para llevar a cabo y cargar archivos.

El administrador funcional define una plantilla de importación que se puede administrar en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Hay tres plantillas de solo lectura predeterminadas disponibles:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**:: esta plantilla puede servir de base para nuevas importaciones a fin de actualizar cuarentenas y registros de envío para el Correo postal. El flujo de trabajo de la plantilla contiene las siguientes actividades:
* **[!UICONTROL Import data]**:: esta plantilla puede servir de base para que las nuevas importaciones inserten datos de un archivo en la base de datos. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**:: esta actividad le permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Update data]**:: esta actividad le permite insertar datos del archivo en la base de datos.

* **[!UICONTROL Import list]**:: esta plantilla puede servir de base para que las nuevas importaciones creen una audiencia de tipo de **Lista** a partir de los datos de un archivo. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**:: esta actividad le permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Reconciliation]**:: esta actividad le permite vincular una dimensión de segmentación a los datos importados. Esto le permite crear una audiencia de tipo de **Lista** . Si no se conoce la dimensión de segmentación de los datos importados, la audiencia es de tipo **Archivo** . Consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**:: esta actividad permite guardar datos importados en forma de audiencia de tipo de **Lista** . El nombre de la audiencia guardada corresponde al nombre del archivo importado por el usuario y se agregará un sufijo que especifica la fecha y la hora de la importación. Por ejemplo: &#39;perfiles_20150406_151448&#39;.

Estas plantillas predeterminadas son de solo lectura y no son visibles para los usuarios estándar. Para crear una plantilla que estará disponible para los usuarios, siga estos pasos:

1. Duplicado de una plantilla predeterminada. La plantilla duplicada contiene tres fichas:

   * **[!UICONTROL Properties]**:: los parámetros generales de la plantilla de importación. Esta ficha le permite activar la plantilla y cargar un archivo de muestra.
   * **[!UICONTROL Workflow]**:: flujo de trabajo de importación. Esta ficha le permite definir las actividades del flujo de trabajo. Estas actividades no son visibles durante las importaciones simplificadas efectuadas por los usuarios.
   * **[!UICONTROL Executed imports]**:: lista de las importaciones efectuadas utilizando este modelo. Puede vista el estado, los detalles y los resultados de cada importación que se haya realizado con esta plantilla. Puede acceder directamente al flujo de trabajo (realizado de forma transparente para el usuario) desde esta lista.

1. En la **[!UICONTROL Properties]** ficha, cambie el nombre de la plantilla y agregue una descripción. Los usuarios podrán realizar la vista de la descripción cuando la plantilla esté disponible.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Desde aquí puede enriquecer el flujo de trabajo ofrecido de forma predeterminada agregando nuevas actividades según sus necesidades.

   Para obtener más información sobre cómo configurar las actividades del flujo de trabajo, consulte el caso de uso descrito en esta sección: [Ejemplo: Importar plantilla](../../automating/using/importing-data.md#example--import-workflow-template)de flujo de trabajo. Este caso de uso le ayudará a configurar un flujo de trabajo que se puede reutilizar para importar perfiles procedentes de una CRM en la base de datos de Adobe Campaign.

1. Guarde la plantilla para que la configuración del flujo de trabajo se tenga en cuenta correctamente.
1. Cargue un archivo de muestra desde la **[!UICONTROL Properties]** ficha. El archivo cargado solo puede tener columnas necesarias para futuras importaciones o datos de muestra. Los datos del archivo de muestra le permiten probar la importación simplificada una vez definido el flujo de trabajo.

   ![](assets/import_template_sample.png)

   Este archivo de muestra estará disponible para que los usuarios que utilicen la plantilla realicen una importación. Podrán descargarlo en su ordenador, por ejemplo, para rellenarlo con datos que se van a importar. Asegúrese de tener esto en cuenta al agregar un archivo de muestra.

1. Guarde la plantilla. Ahora se tiene en cuenta el archivo de muestra. En cualquier momento puede descargarlo en su ordenador para comprobar el contenido o modificarlo marcando la **[!UICONTROL Drop a new sample file]** opción.

   ![](assets/simplified_import_model2.png)

1. Vuelva a la **[!UICONTROL Workflow]** ficha y abra la **[!UICONTROL Load file]** actividad para comprobar y ajustar la configuración de columna del archivo de muestra que se cargó en el paso anterior.
1. Pruebe la importación iniciando el flujo de trabajo. El archivo de muestra cargado en el paso **5** debe contener datos.

   Los datos del archivo de muestra se importan de forma genuina. Asegúrese de que los datos utilizados sean pequeños y ficticios para garantizar que la base de datos no se vea comprometida.

1. Vaya al registro de ejecución del flujo de trabajo, disponible en la barra de acciones. Si se produce un error, compruebe que las actividades estén configuradas correctamente.

   ![](assets/simplified_import_model3.png)

1. En la **[!UICONTROL Properties]** ficha, establezca el valor **[!UICONTROL Import template status]** en **[!UICONTROL Available]** y, a continuación, guarde la plantilla. Para dejar de usar esta plantilla, puede establecer el **[!UICONTROL Import template status]** en **[!UICONTROL Archived]**.

El flujo de trabajo de la plantilla se puede modificar cargando de nuevo el archivo de ejemplo y comprobando la **[!UICONTROL Load file]** configuración.

La plantilla de importación ya está disponible para los usuarios y se puede utilizar para cargar archivos.

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Importación de datos](../../automating/using/importing-data.md)
* [Ejemplo: Importar plantilla de flujo de trabajo](../../automating/using/importing-data.md#example--import-workflow-template)


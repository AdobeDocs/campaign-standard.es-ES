---
title: Definición de plantillas de importación
seo-title: Definición de plantillas de importación
description: Definición de plantillas de importación
seo-description: Importe las plantillas para reducir la configuración necesaria e importar datos más rápidamente.
page-status-flag: no activado nunca
uuid: 651 eb 57 c-adac -4 e 3 e-b 454-b 39 aea 1 f 0484
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: importar y exportar datos
discoiquuid: 85 d 13147-fb 31-446 a -8476-f 112 c 841 fb 82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Defining import templates{#defining-import-templates}

Importar plantillas permite al administrador definir previamente un cierto número de configuraciones de importación técnica. Estas plantillas pueden estar disponibles para los usuarios estándar para que realicen y carguen archivos.

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

Hay disponibles tres plantillas de solo lectura predeterminadas:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: esta plantilla puede servir como base para nuevas importaciones para actualizar ubicaciones y registros de entrega de correo directo. El flujo de trabajo de la plantilla contiene las siguientes actividades:
* **[!UICONTROL Import data]**: esta plantilla puede servir como base para las importaciones nuevas para insertar datos de un archivo en la base de datos. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**: esta actividad permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Update data]**: esta actividad permite insertar datos del archivo en la base de datos.

* **[!UICONTROL Import list]**: esta plantilla puede servir como base para las importaciones nuevas a fin de crear una audiencia de tipo **Lista** a partir de datos de un archivo. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**: esta actividad permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: esta actividad permite vincular una dimensión de segmentación a datos importados. This then allows you to create a **List** type audience. If the targeting dimension of the imported data is not known, the audience is **File** type. See [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: esta actividad permite guardar datos importados en forma de audiencia de tipo **de lista** . El nombre de la audiencia guardada corresponde al nombre del archivo importado por el usuario y se agregará un sufijo que especifique la fecha y la hora de la importación. Por ejemplo: ' profiles_ 20150406_ 151448 '.

Estas plantillas predeterminadas son de solo lectura y no son visibles para los usuarios estándar. Para crear una plantilla que estará disponible para los usuarios, siga estos pasos:

1. Duplicar una plantilla predeterminada. La plantilla duplicada contiene tres fichas:

   * **[!UICONTROL Properties]**: los parámetros generales de la plantilla de importación. Esta ficha permite habilitar la plantilla y cargar un archivo de ejemplo.
   * **[!UICONTROL Workflow]**: flujo de trabajo de importación. Esta ficha permite definir las actividades del flujo de trabajo. Estas actividades no están visibles durante importaciones simplificadas realizadas por usuarios.
   * **[!UICONTROL Executed imports]**: lista de importaciones realizadas con esta plantilla. Puede ver el estado, los detalles y los resultados de cada importación que se haya realizado con esta plantilla. Puede acceder directamente al flujo de trabajo (se lleva a cabo de forma transparente para el usuario) desde esta lista.

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. Los usuarios podrán ver la descripción cuando la plantilla esté disponible.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Desde aquí puede enriquecer el flujo de trabajo ofrecido de forma predeterminada mediante la adición de nuevas actividades según sus necesidades.

   For more on how to configure the workflow activities, refer to the use case describe in this section: [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template). Este caso de uso le ayudará a configurar un flujo de trabajo que se puede reutilizar para importar perfiles provenientes de una CRM en la base de datos de Adobe Campaign.

1. Guarde la plantilla para que la configuración del flujo de trabajo se tenga en cuenta correctamente.
1. Upload a sample file from the **[!UICONTROL Properties]** tab. El archivo cargado sólo puede tener columnas necesarias para importaciones futuras o datos de ejemplo. Los datos del archivo de ejemplo le permiten probar la importación simplificada una vez definido el flujo de trabajo.

   ![](assets/import_template_sample.png)

   Este archivo de muestra estará disponible para los usuarios que utilicen la plantilla para realizar una importación. Podrán descargarlo en su equipo, por ejemplo para rellenarlo con datos que importar. Asegúrese de tener esto en cuenta al agregar un archivo de ejemplo.

1. Guarde la plantilla. Ahora se tiene en cuenta el archivo de ejemplo. At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. Pruebe la importación iniciando el flujo de trabajo. The sample file uploaded at step **5** has to contain data.

   Los datos del archivo de ejemplo se importan realmente. Asegúrese de que los datos utilizados son pequeños y ficticios para garantizar que la base de datos no se encuentre comprometida.

1. Vaya al registro de ejecución del flujo de trabajo, disponible en la barra de acciones. Si se produce un error, compruebe que las actividades estén configuradas correctamente.

   ![](assets/simplified_import_model3.png)

1. In the **[!UICONTROL Properties]** tab, set the **[!UICONTROL Import template status]** to **[!UICONTROL Available]**, then save the template. To stop using this template, you can set the **[!UICONTROL Import template status]** to **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

La plantilla de importación ya está disponible para los usuarios y se puede utilizar para cargar archivos.

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/discovering-workflows.md)
* [Importación de datos](../../automating/using/importing-data.md)
* [Ejemplo: Importar plantilla de flujo de trabajo](../../automating/using/importing-data.md#example--import-workflow-template)


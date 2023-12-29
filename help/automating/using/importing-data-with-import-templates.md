---
title: Importación de datos con plantillas de importación
description: Obtenga información sobre cómo recopilar datos para alimentar la base de datos de Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5e93b39e-cdd1-4632-8f65-dfa76a735626
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 99%

---

# Importación de datos con plantillas de importación{#importing-data-with-import-templates}

La importación de datos le permite recopilar datos para alimentar la base de datos de Campaign.

Como alternativa a [Flujos de trabajo](../../automating/using/get-started-workflows.md), Adobe Campaign ofrece una función de importación simplificada que permite al usuario gestionar determinados tipos de importación definidos por un administrador.

El principio de funcionamiento es el siguiente: un **administrador** define y gestiona plantillas de importación (consulte [Definición de plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)). Estas plantillas de importación se ponen a disposición de los usuarios con vistas simplificadas en el menú **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]**.

Así, estos usuarios solo tendrán que seleccionar el tipo de importación que desean realizar y cargar el archivo con los datos que se van a importar. El flujo de trabajo definido por el administrador se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación una vez que haya finalizado.

>[!NOTE]
>
>Los usuarios con funciones de **[!UICONTROL GENERIC IMPORT (import)]** y **[!UICONTROL WORKFLOW (workflow)]** pueden gestionar la funcionalidad de importación de datos. Para obtener más información sobre las funciones, consulte [esta sección](../../administration/using/list-of-roles.md).

Las importaciones se pueden filtrar según la plantilla desde la que se ejecutaron, la fecha de ejecución y el estado de ejecución.

1. En la descripción general de importaciones, haga clic en el botón **[!UICONTROL Create]**. Se abre el asistente.
1. Seleccione el tipo de importación que desea realizar. Los tipos de importación corresponden a las plantillas de importación disponibles.
1. Si es necesario, descargue el archivo de muestra vinculado a la plantilla en el equipo para ver los tipos de datos esperados en el archivo que se va a importar.
1. Descargue el archivo que contiene los datos que desea importar en el asistente.
1. Inicie la importación. El asistente se cierra y le lleva de nuevo a la lista de las importaciones realizadas con la plantilla utilizada.
1. Actualice la página y seleccione la importación que acaba de realizar para ver los detalles de ejecución.

   ![](assets/simplified_import1.png)

Ya están disponibles los detalles de la ejecución de la importación. Tanto el archivo que se ha importado como el archivo que contiene los datos rechazados (datos que no se importaron) pueden descargarse en el equipo.

## Configuración de plantillas de importación {#setting-up-import-templates}

Las plantillas de importación permiten al administrador definir previamente un determinado número de configuraciones técnicas de importación. Estas plantillas se pueden poner a disposición de los usuarios estándar para llevar a cabo y cargar archivos.

El administrador funcional define una plantilla de importación que se puede administrar en el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]**.

![](assets/import_template_list.png)

Hay tres plantillas de solo lectura predeterminadas disponibles:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: esta plantilla puede servir de base para nuevas importaciones a fin de actualizar cuarentenas y registros de envío para el correo postal. El flujo de trabajo de la plantilla contiene las siguientes actividades:
* **[!UICONTROL Import data]**: esta plantilla puede servir de base para que las nuevas importaciones inserten datos de un archivo en la base de datos. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**: esta actividad le permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Update data]**: esta actividad le permite insertar datos del archivo en la base de datos.

* **[!UICONTROL Import list]**: esta plantilla puede servir de base para que las nuevas importaciones creen una audiencia de tipo **lista** a partir de los datos de un archivo. El flujo de trabajo de esta plantilla contiene las siguientes actividades:

   * **[!UICONTROL Load file]**: esta actividad le permite cargar un archivo en el servidor de Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: esta actividad le permite vincular una dimensión de segmentación a los datos importados. Esto le permite crear una audiencia de tipo **lista**. Si no se conoce la dimensión de segmentación de los datos importados, la audiencia es de tipo **archivo**. Consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: esta actividad permite guardar datos importados en forma de audiencia de tipo **lista**. El nombre de la audiencia guardada corresponde al nombre del archivo importado por el usuario y se añade un sufijo que especifica la fecha y la hora de la importación. Por ejemplo: “perfiles_20150406_151448”.

Estas plantillas predeterminadas son de solo lectura y no son visibles para los usuarios estándar. Para crear una plantilla disponible para los usuarios, siga estos pasos:

1. Duplicado de una plantilla predeterminada. La plantilla duplicada contiene tres pestañas:

   * **[!UICONTROL Properties]**: parámetros generales de la plantilla de importación. Esta pestaña le permite activar la plantilla y cargar un archivo de muestra.
   * **[!UICONTROL Workflow]**: flujo de trabajo de importación. Esta pestaña le permite definir las actividades del flujo de trabajo. Estas actividades no son visibles durante las importaciones simplificadas efectuadas por los usuarios.
   * **[!UICONTROL Executed imports]**: lista de las importaciones efectuadas utilizando este modelo. Puede ver el estado, los detalles y los resultados de cada importación que se haya realizado con esta plantilla. Puede acceder directamente al flujo de trabajo (realizado de forma transparente para el usuario) desde esta lista.

1. En la pestaña **[!UICONTROL Properties]**, cambie el nombre de la plantilla y añada una descripción. Los usuarios pueden ver la descripción cuando la plantilla esté disponible.

   ![](assets/simplified_import_model1.png)

1. Vaya a la pestaña **[!UICONTROL Workflow]**. Desde aquí puede enriquecer el flujo de trabajo ofrecido de forma predeterminada añadiendo nuevas actividades según sus necesidades.

   Para obtener más información sobre cómo configurar las actividades del flujo de trabajo, consulte el caso de uso descrito en esta sección: [Ejemplo: importar plantilla de flujo de trabajo](../../automating/using/creating-import-workflow-templates.md). Este caso de uso le puede ayudar a configurar un flujo de trabajo que se puede reutilizar para importar perfiles procedentes de una CRM en la base de datos de Adobe Campaign.

1. Guarde la plantilla para que la configuración del flujo de trabajo se tenga en cuenta correctamente.
1. Cargue un archivo de muestra desde la pestaña **[!UICONTROL Properties]**. El archivo cargado solo puede tener columnas necesarias para futuras importaciones o datos de muestra. Los datos del archivo de muestra le permiten probar la importación simplificada una vez definido el flujo de trabajo.

   ![](assets/import_template_sample.png)

   Este archivo de muestra está disponible para que los usuarios que utilicen la plantilla realicen una importación. Podrán descargarlo en su ordenador, por ejemplo, para rellenarlo con datos que se van a importar. Asegúrese de tener esto en cuenta al añadir un archivo de muestra.

1. Guarde la plantilla. Ahora se tiene en cuenta el archivo de muestra. En cualquier momento puede descargarlo en el ordenador para comprobar el contenido o modificarlo marcando la opción **[!UICONTROL Drop a new sample file]**.

   ![](assets/simplified_import_model2.png)

1. Vuelva a la pestaña **[!UICONTROL Workflow]** y abra la actividad **[!UICONTROL Load file]** para comprobar y ajustar la configuración de columna del archivo de muestra que ha cargado en el paso anterior.
1. Pruebe la importación iniciando el flujo de trabajo. El archivo de muestra cargado en el paso **5** debe contener datos.

   Los datos del archivo de muestra se importan de forma genuina. Asegúrese de que los datos utilizados sean pequeños y ficticios para garantizar que la base de datos esté en peligro.

1. Vaya al registro de ejecución del flujo de trabajo, disponible en la barra de acciones. Si se produce un error, compruebe que las actividades estén configuradas correctamente.

   ![](assets/simplified_import_model3.png)

1. En la pestaña **[!UICONTROL Properties]**, establezca el **[!UICONTROL Import template status]** en **[!UICONTROL Available]** y, a continuación, guarde la plantilla. Para dejar de usar esta plantilla, puede establecer el **[!UICONTROL Import template status]** en **[!UICONTROL Archived]**.

El flujo de trabajo de la plantilla se puede modificar cargando de nuevo el archivo de ejemplo y comprobando la configuración de **[!UICONTROL Load file]**.

La plantilla de importación ya está disponible para los usuarios y se puede utilizar para cargar archivos.

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Ejemplo: importar plantilla de flujo de trabajo](../../automating/using/creating-import-workflow-templates.md)

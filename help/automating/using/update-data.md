---
title: Actualización de datos
description: La actividad actualización de datos permite realizar una actualización masiva de los campos de la base de datos.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d362563f-5ab3-4f7f-ae9f-a42b6f0bb2b9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 98%

---

# Actualización de datos{#update-data}

## Descripción {#description}

![](assets/data_update.png)

La actividad **[!UICONTROL Update data]** le permite realizar una actualización masiva de los campos de la base de datos.

## Contexto de uso {#context-of-use}

La actividad **actualización de datos** se puede utilizar después de importar un archivo para insertar los datos recuperados en la base de datos de Adobe Campaign. Varias opciones permiten personalizar la actualización de los datos.

**Temas relacionados:**

* [Caso de uso: Actualización de datos basados en un archivo](../../automating/using/update-database-file.md)
* [Actualización de datos en función de una descarga automática de archivos](../../automating/using/update-data-automatic-download.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Update data]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Especifique el **[!UICONTROL Operation type]** que se va a realizar:

   * **[!UICONTROL Insert or update]**: inserte datos o actualícelos si los registros ya existen en la base de datos.
   * **[!UICONTROL Insert only]**: insertar solo datos. Los registros que ya existen no se actualizan. Si se definen los criterios de reconciliación, solo se añaden los registros que no se han cuadrado.

     Marque la casilla **[!UICONTROL Generate an outbound transition for rejects]** si los datos importados contienen ciertos registros que ya existen en la base de datos para evitar posibles errores.

   * **[!UICONTROL Update]**: actualizar los datos de los registros que ya existen solo en la base de datos.
   * **[!UICONTROL Delete]**: eliminar datos.

   >[!NOTE]
   >
   >El campo **[!UICONTROL Batch size]** permite definir el tamaño máximo del lote de datos que se va a cargar.

1. En la pestaña **[!UICONTROL Identification]**, especifique cómo identificar los registros de la base de datos:

   * **[!UICONTROL Using the targeting dimension]**: seleccione la **[!UICONTROL Dimension to update]** y luego especifique la **[!UICONTROL Keys for finding records]**. Para obtener más información, consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Si los datos especificados coinciden con una dimensión de segmentación existente, seleccione la opción **[!UICONTROL Using one or more links]**. A continuación, seleccione la **[!UICONTROL Dimension to update]**.

   Si el tipo de operación seleccionado requiere una actualización, debe utilizar claves de reconciliación.

1. En la pestaña **[!UICONTROL Fields to update]**, especifique los campos en los que se debe aplicar la actualización y, si es necesario, añada condiciones para que se realice la actualización. Para ello, utilice la columna **[!UICONTROL Taken into account if]**. Las condiciones se aplican una tras otra en orden de lista. Utilice las flechas de la derecha para cambiar el orden de las actualizaciones. Puede utilizar el mismo campo de destino varias veces.

   Los campos se pueden vincular automáticamente con el botón ![](assets/wkf_magic_wand-24px.png). La vinculación automática detecta los campos con el mismo nombre.

   Durante una operación de tipo **[!UICONTROL Insert or update]**, puede seleccionar individualmente la operación que se debe aplicar a cada campo. Para ello, seleccione el valor que desee en la columna **[!UICONTROL Operation]**.

   >[!NOTE]
   >
   >**Administración de actualizaciones** Los campos **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** y **[!UICONTROL createdBy]** se actualizan automáticamente cuando se ejecuta una actividad de actualización de datos, a menos que su configuración se realice explícitamente en la tabla de actualización de campo. La actualización solo se realiza en los registros en los que se ha detectado al menos una diferencia. Si los valores son equivalentes, no se realiza ninguna actualización.

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.

   Si ha seleccionado **[!UICONTROL Insert only]** y los datos importados pueden contener registros que ya están presentes en la base de datos, marque la casilla **[!UICONTROL Generate an outbound transition for the rejects]** para evitar posibles errores.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

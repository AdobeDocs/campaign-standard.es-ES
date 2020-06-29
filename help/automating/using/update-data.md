---
title: Actualización de datos
description: La actividad Actualizar datos permite realizar una actualización masiva de los campos de la base de datos.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---


# Actualización de datos{#update-data}

## Descripción {#description}

![](assets/data_update.png)

La **[!UICONTROL Update data]** actividad le permite realizar una actualización masiva de los campos de la base de datos.

## Contexto de uso {#context-of-use}

La actividad **Actualizar datos** se puede utilizar después de importar un archivo para insertar los datos recuperados en la base de datos de Adobe Campaign. Varias opciones permiten personalizar la actualización de los datos.

**Temas relacionados:**

* [Caso de uso: Actualización de datos basados en un archivo](../../automating/using/update-database-file.md)
* [Actualización de datos en función de una descarga automática de archivos](../../automating/using/update-data-automatic-download.md)

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Update data]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Especifique el **[!UICONTROL Operation type]** que se realizará:

   * **[!UICONTROL Insert or update]**:: inserte datos o actualícelos si los registros ya existen en la base de datos.
   * **[!UICONTROL Insert only]**:: insertar sólo datos. Los registros que ya existen no se actualizan. Si se definen los criterios de conciliación, solo se agregarán los registros no conciliados.

      Marque la **[!UICONTROL Generate an outbound transition for rejects]** casilla si los datos importados contienen ciertos registros que ya existen en la base de datos para evitar posibles errores.

   * **[!UICONTROL Update]**:: actualizar los datos de los registros que ya existen solo en la base de datos.
   * **[!UICONTROL Delete]**:: eliminar datos.
   >[!NOTE]
   >
   >El **[!UICONTROL Batch size]** campo permite definir el tamaño máximo de lote de los datos que se van a cargar.

1. En la **[!UICONTROL Identification]** ficha, especifique cómo identificar los registros de la base de datos:

   * **[!UICONTROL Using the targeting dimension]**:: seleccione el **[!UICONTROL Dimension to update]** y luego especifique el **[!UICONTROL Keys for finding records]**. Para obtener más información, consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Si los datos especificados coinciden con una dimensión de segmentación existente, seleccione la **[!UICONTROL Using one or more links]** opción. A continuación, seleccione el **[!UICONTROL Dimension to update]**.
   Si el tipo de operación seleccionado requiere una actualización, debe utilizar claves de reconciliación.

1. En la **[!UICONTROL Fields to update]** ficha, especifique los campos en los que se aplicará la actualización y, si es necesario, agregue condiciones para que se realice la actualización. To do this, use the **[!UICONTROL Taken into account if]** column. Las condiciones se aplican una tras otra en orden de lista. Utilice las flechas de la derecha para cambiar el orden de las actualizaciones. Puede utilizar el mismo campo de destino varias veces.

   Los campos se pueden vincular automáticamente con el ![](assets/wkf_magic_wand-24px.png) botón. La vinculación automática detecta los campos con el mismo nombre.

   Durante una operación de **[!UICONTROL Insert or update]** tipo, puede seleccionar individualmente la operación que se aplicará a cada campo. Para ello, seleccione el valor que desee en la **[!UICONTROL Operation]** columna.

   >[!NOTE]
   >
   >**Administración de actualizaciones** Los campos **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]** y **[!UICONTROL created]****[!UICONTROL createdBy]** se actualizan automáticamente cuando se ejecuta una actividad de datos de actualización, a menos que su configuración se realice explícitamente en la tabla de actualización de campo. La actualización solo se realiza en los registros en los que se ha detectado al menos una diferencia. Si los valores son los mismos, no se realiza ninguna actualización.

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.

   Si ha seleccionado **[!UICONTROL Insert only]** y los datos importados pueden contener registros que ya están presentes en la base de datos, marque la **[!UICONTROL Generate an outbound transition for the rejects]** casilla para evitar posibles errores.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

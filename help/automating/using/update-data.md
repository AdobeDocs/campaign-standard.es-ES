---
title: Actualizar datos
seo-title: Actualizar datos
description: Actualizar datos
seo-description: La actividad de actualización de datos permite realizar una actualización masiva de los campos de la base de datos.
page-status-flag: no activado nunca
uuid: 1 dc 55 db 5-affd -4688-b 673-adfb 8 c 1338 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4 db 83 c 95-4 b 75-4 a 16-8 dbf-bd 8940431 fa 9
context-tags: redactor, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## Description {#description}

![](assets/data_update.png)

The **[!UICONTROL Update data]** activity allows you to perform a mass update on fields in the database.

## Context of use {#context-of-use}

The **Update data** activity can be used after importing a file in order to insert the data recovered into the Adobe Campaign database. Varias opciones permiten personalizar la actualización de datos.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**: inserta datos o actualícelos si los registros ya existen en la base de datos.
   * **[!UICONTROL Insert only]**: sólo inserta datos. Los registros que ya existen no se actualizan. Si se definen los criterios de reconciliación, solo se agregarán los registros no conciliados.

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**: actualizar los datos de los registros que ya existen en la base de datos.
   * **[!UICONTROL Delete]**: eliminar datos.
   >[!NOTE]
   >
   >The **[!UICONTROL Batch size]** field enables you to define the maximum batch size for the data to upload.

1. In the **[!UICONTROL Identification]** tab, specify how to identify the records in the database:

   * **[!UICONTROL Using the targeting dimension]**: seleccione la **[!UICONTROL Dimension to update]****[!UICONTROL Keys for finding records]** opción. For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   Si el tipo de operación seleccionado requiere una actualización, debe utilizar las claves de reconciliación.

1. In the **[!UICONTROL Fields to update]** tab, specify the fields on which the update will be applied and, if necessary, add conditions so that this update is carried out. To do this, use the **[!UICONTROL Taken into account if]** column. Las condiciones se aplican una tras otra en orden de lista. Utilice las flechas de la derecha para cambiar el orden de las actualizaciones. Puede utilizar el mismo campo de destino varias veces.

   You can automatically link fields using the ![](assets/wkf_magic_wand-24px.png) button. La vinculación automática detecta los campos con el mismo nombre.

   During an **[!UICONTROL Insert or update]** type operation, you can individually select the operation to apply for each field. To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**Administración de actualizaciones** La **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]****[!UICONTROL created]** y **[!UICONTROL createdBy]** los campos se actualizan automáticamente cuando se ejecuta una actividad de datos de actualización, a menos que se realice explícitamente su configuración en la tabla de actualizaciones del campo. La actualización solo se realiza en los registros donde se ha detectado al menos una diferencia. Si los valores son iguales, no se realiza ninguna actualización.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. El objetivo de este flujo de trabajo es agregar o actualizar perfiles a la base de datos de Adobe Campaign con los datos recuperados del archivo. La clave de reconciliación utilizada es la dirección de correo electrónico.

The file loaded is a **.txt** format file containing the following example data:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

**[!UICONTROL Update data]** La actividad se configura de la siguiente manera:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)


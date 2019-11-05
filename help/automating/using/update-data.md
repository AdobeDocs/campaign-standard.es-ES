---
title: Actualización de datos
description: La actividad de actualización de datos permite realizar una actualización masiva de los campos de la base de datos.
page-status-flag: nunca activado
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: gestión de datos-actividades
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: escritor,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Actualización de datos{#update-data}

## Descripción {#description}

![](assets/data_update.png)

La **[!UICONTROL Update data]** actividad permite realizar una actualización masiva de los campos de la base de datos.

## Contexto de uso {#context-of-use}

La actividad de **actualización de datos** se puede utilizar después de importar un archivo para insertar los datos recuperados en la base de datos de Adobe Campaign. Varias opciones permiten personalizar la actualización de los datos.

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

   * **[!UICONTROL Using the targeting dimension]**:: seleccione el **[!UICONTROL Dimension to update]** y luego especifique el **[!UICONTROL Keys for finding records]**. Para obtener más información, consulte [Segmentación de dimensiones y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Si los datos especificados coinciden con una dimensión de objetivo existente, seleccione la **[!UICONTROL Using one or more links]** opción. A continuación, seleccione el **[!UICONTROL Dimension to update]**.
   Si el tipo de operación seleccionado requiere una actualización, debe utilizar claves de reconciliación.

1. En la **[!UICONTROL Fields to update]** ficha, especifique los campos en los que se aplicará la actualización y, si es necesario, agregue condiciones para que se realice la actualización. Para ello, utilice la **[!UICONTROL Taken into account if]** columna. Las condiciones se aplican una tras otra en orden de lista. Utilice las flechas de la derecha para cambiar el orden de las actualizaciones. Puede utilizar el mismo campo de destino varias veces.

   Los campos se pueden vincular automáticamente con el ![](assets/wkf_magic_wand-24px.png) botón. La vinculación automática detecta los campos con el mismo nombre.

   Durante una operación de **[!UICONTROL Insert or update]** tipo, puede seleccionar individualmente la operación que se aplicará a cada campo. Para ello, seleccione el valor que desee en la **[!UICONTROL Operation]** columna.

   >[!NOTE]
   >
   >**Administración de actualizaciones** Los campos **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]** y **[!UICONTROL created]****[!UICONTROL createdBy]** se actualizan automáticamente cuando se ejecuta una actividad de actualización de datos, a menos que su configuración se lleve a cabo explícitamente en la tabla de actualización de campo. La actualización solo se realiza en los registros en los que se ha detectado al menos una diferencia. Si los valores son los mismos, no se realiza ninguna actualización.

1. Si es necesario, administre las [transiciones](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) de la actividad para acceder a las opciones avanzadas de la población saliente.

   Si ha seleccionado **[!UICONTROL Insert only]** y los datos importados pueden contener registros que ya están presentes en la base de datos, marque la **[!UICONTROL Generate an outbound transition for the rejects]** casilla para evitar posibles errores.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

La siguiente actividad muestra la configuración de una **[!UICONTROL Update data]** actividad después de una **[!UICONTROL Load file]** actividad. El objetivo de este flujo de trabajo es agregar o actualizar perfiles a la base de datos de Adobe Campaign con los datos recuperados del archivo. La clave de reconciliación utilizada es la dirección de correo electrónico.

El archivo cargado es un archivo de formato **.txt** que contiene los siguientes datos de ejemplo:

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

La **[!UICONTROL Update data]** actividad se configura de la siguiente manera:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)


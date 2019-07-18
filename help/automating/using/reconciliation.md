---
title: Reconciliación
seo-title: Reconciliación
description: Reconciliación
seo-description: La actividad de reconciliación permite vincular datos no identificados a recursos existentes.
page-status-flag: no activado nunca
uuid: 7884 db 8 c -1717-4724-be 15-3 b 0 b 32 ccc 071
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb 8 c 43 f 4-9 cdd -4 e 85-99 a 4-004 b 36 b 336 aa
context-tags: reconciliación, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Reconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

The **[!UICONTROL Reconciliation]** activity allows you to link unidentified data to existing resources.

## Context of use {#context-of-use}

The **[!UICONTROL Reconciliation]** activity is essentially used for Data Management purposes and implies two different use cases:

* Adding relations: a **[!UICONTROL Links]** tab allows you to add links between the inbound data and several other Adobe Campaign database dimensions.

   Por ejemplo, un archivo que contenga datos de compra también puede contener información para identificar los productos comprados y el comprador. Two additional dimensions (besides that of **Purchases**) are therefore concerned by the file data: the **Products** and **Profiles** dimensions. Relations then need to be created between these and the **Purchases** dimension (refer to the following example).

   Al definir una relación, se agrega una columna a los datos de entrada para hacer referencia a la clave externa de la dimensión vinculada.

   >[!NOTE]
   >
   >Esta operación implica que los datos de las dimensiones vinculadas ya están en la base de datos. Por ejemplo, si importa un archivo de compras que muestra qué producto se compró, a qué hora, por qué cliente, etc., debe existir el producto como así también el cliente en la base de datos.

* Data identification: an **[!UICONTROL Identification]** tab allows you to simply link inbound data to columns of an existing dimension in the Adobe Campaign database. Después de la actividad, los datos se identifican como pertenecientes a la dimensión definida.

   Por ejemplo, puede realizar una audiencia guardada, actualizar la base de datos, etc.

For example, the **[!UICONTROL Reconciliation]** activity can be placed after a load data activity with the aim of importing non-standard data into the database.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Reconciliation]** activity into your workflow, following a transition containing a population whose targeting dimension does not directly come from Adobe Campaign. For more on this, referr to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to define links between the inbound data and other database dimensions, go to the **[!UICONTROL Links]** tab.

   Agregue tantas relaciones como sea necesario. Para cada relación, seleccione primero la dimensión vinculada y, en el detalle del vínculo, especifique los campos correspondientes.

1. If you would like to simply identify the inbound data, go to the **[!UICONTROL Identification]** tab and check the **[!UICONTROL Identify the document from the working data]** box.

   Seleccione la dimensión de objetivo a la que desea reconciliar los datos de entrada.

   Agregue criterios de reconciliación para vincular un registro de transición entrante a un registro de dimensión de objetivo seleccionado. Si se especifican varios criterios, todos deben verificarse para que funcione el vínculo entre todos sus datos.

   Choose the **[!UICONTROL Processing unidentified source lines]** mode:

   * **[!UICONTROL Ignore them]**: solo se mantienen los datos identificables en la transición saliente de la actividad.
   * **[!UICONTROL Keep in the outbound population]**: todos los datos de la transición entrante se mantienen en la transición saliente de la actividad.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example 1: Relation definition {#example-1--relation-definition}

El siguiente ejemplo muestra un flujo de trabajo que actualiza la base de datos utilizando los datos de compra en un archivo. Los datos de compra contienen elementos de referencia de datos de otras dimensiones, como los correos electrónicos del cliente y los códigos de producto.

>[!NOTE]
>
>The **Transactions** and **Products** resources used in this example do not exist in the Adobe Campaign database by default. They were therefore created beforehand using the [Custom resources](../../developing/using/data-model-concepts.md) function. Los perfiles que corresponden a las direcciones de correo electrónico del archivo importado, al igual que los productos, se cargaban previamente en la base de datos.

El flujo de trabajo está formado por las siguientes actividades:

![](assets/reconciliation_example1.png)

* **[!UICONTROL Load file]** Actividad que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

   * Fecha de transacción
   * Dirección de correo electrónico del cliente
   * Código de producto comprado
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* **[!UICONTROL Reconciliation]** Actividad que enlaza los datos de compra a perfiles de base de datos y productos. Por lo tanto, es necesario definir una relación entre los datos del archivo y la tabla de perfil, así como la tabla del producto. This configuration is carried out in the activity's **[!UICONTROL Relations]** tab:

   * Relation with the **Profiles**: the file's **client** column is linked to the **email** field of the **Profiles** dimension.
   * Relation with the **Products**: the file's **product** column is linked to the **productCode** field of the **Profiles** dimension.
   Las columnas se agregan a los datos de entrada para hacer referencia a las claves externas de las dimensiones vinculadas.

   ![](assets/reconciliation_example3.png)

* An **[!UICONTROL Update data]** activity allows you to define the database fields to update using the imported data. As the data was already identified as belonging to the **Transactions** dimension in the previous activity, here you can use the **[!UICONTROL Directly using the targeting dimension]** identification option.

   By using the option that automatically detects fields to update, the links configured in the previous activity (to profiles and products) are added to the list of **[!UICONTROL Fields to update]**. También debe asegurarse de que el campo correspondiente a la fecha de transacción se agregue correctamente a esta lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Example 2: Identification {#example-2--identification}

El siguiente ejemplo muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes. Consta de las siguientes actividades:

![](assets/identification_example2.png)

* **[!UICONTROL Load file]** Actividad que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

   ```
   lastname;firstname;email;dateofbirth
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

* **[!UICONTROL Reconciliation]** Una actividad que vincula cada columna del archivo cargado a una columna de dimensión de perfil. Los registros de archivos que no se pueden identificar (falta datos, tipo de datos incompatible, etc.) se omiten para preservar la integridad de los datos de audiencia finales.

   ![](assets/identification_example1.png)

* **[!UICONTROL Save audience]** Actividad que guarda la audiencia de perfiles.

   ![](assets/identification_example3.png)


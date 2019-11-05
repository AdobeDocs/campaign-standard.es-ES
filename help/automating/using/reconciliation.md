---
title: Reconciliación
description: La actividad Reconciliación le permite vincular datos no identificados a recursos existentes.
page-status-flag: nunca activado
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: gestión de datos-actividades
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliación,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Reconciliación{#reconciliation}

## Descripción {#description}

![](assets/reconciliation.png)

La **[!UICONTROL Reconciliation]** actividad le permite vincular datos no identificados a recursos existentes.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Reconciliation]** actividad se utiliza esencialmente con fines de administración de datos e implica dos casos de uso diferentes:

* Agregando relaciones: una **[!UICONTROL Links]** ficha permite agregar vínculos entre los datos de entrada y varias otras dimensiones de base de datos de Adobe Campaign.

   Por ejemplo, un archivo que contenga datos de compra también puede contener información para identificar tanto los productos comprados como el comprador. Dos dimensiones adicionales (además de la de **Compras**) se preocupan por los datos del archivo: las dimensiones **Productos** y **Perfiles** . Luego deben crearse relaciones entre éstas y la dimensión **Compras** (consulte el siguiente ejemplo).

   Al definir una relación, se agrega una columna a los datos de entrada para hacer referencia a la clave externa de la dimensión vinculada.

   >[!NOTE]
   >
   >Esta operación implica que los datos de las dimensiones vinculadas ya están en la base de datos. Por ejemplo, si importa un archivo de compras que muestre qué producto se compró, a qué hora, por qué cliente, etc., el producto y el cliente ya deben existir en la base de datos.

* Identificación de datos: una **[!UICONTROL Identification]** ficha permite simplemente vincular datos de entrada a columnas de una dimensión existente en la base de datos de Adobe Campaign. Después de la actividad, los datos se identifican como pertenecientes a la dimensión definida.

   Por ejemplo, puede guardar una audiencia, actualizar la base de datos, etc.

Por ejemplo, la actividad se puede colocar después de una actividad de carga de datos con el fin de importar datos no estándar en la base de datos. **[!UICONTROL Reconciliation]**

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Reconciliation]** actividad en el flujo de trabajo, después de una transición que contenga una población cuya dimensión de objetivo no proceda directamente de Adobe Campaign. Para obtener más información sobre esto, consulte [Segmentación de dimensiones y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Si desea definir vínculos entre los datos de entrada y otras dimensiones de base de datos, vaya a la **[!UICONTROL Links]** ficha .

   Agregue tantas relaciones como sea necesario. Para cada relación, primero seleccione la dimensión vinculada y luego, en el detalle del vínculo, especifique los campos correspondientes.

1. Si desea simplemente identificar los datos entrantes, vaya a la **[!UICONTROL Identification]** ficha y marque la **[!UICONTROL Identify the document from the working data]** casilla.

   Seleccione la dimensión de objetivo a la que desea reconciliar los datos de entrada.

   Agregue criterios de reconciliación para vincular un registro de transición entrante a un registro de dimensión de objetivo seleccionado. Si se especifican varios criterios, todos deben verificarse para que funcione el vínculo entre todos sus datos.

   Elija el **[!UICONTROL Processing unidentified source lines]** modo:

   * **[!UICONTROL Ignore them]**:: solo los datos identificables se conservan en la transición de salida de la actividad.
   * **[!UICONTROL Keep in the outbound population]**:: todos los datos de la transición de entrada se guardan en la transición de salida de la actividad.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo 1: Definición de relación {#example-1--relation-definition}

En el siguiente ejemplo se muestra un flujo de trabajo que actualiza la base de datos con los datos de compra de un archivo. Los datos de compra contienen datos que hacen referencia a elementos de otras dimensiones, como los correos electrónicos del cliente y los códigos de producto.

>[!NOTE]
>
>Los recursos **Transacciones** y **Productos** utilizados en este ejemplo no existen de forma predeterminada en la base de datos de Adobe Campaign. Por lo tanto, se crearon de antemano utilizando la función de recursos [](../../developing/using/data-model-concepts.md) personalizados. Los perfiles que corresponden a las direcciones de correo electrónico del archivo importado, así como los productos, se cargaron en la base de datos de antemano.

El flujo de trabajo se compone de las siguientes actividades:

![](assets/reconciliation_example1.png)

* Una **[!UICONTROL Load file]** actividad que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

   * Fecha de transacción
   * Dirección de correo electrónico del cliente
   * Código del producto comprado
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

* Una **[!UICONTROL Reconciliation]** actividad para enlazar datos de compra a perfiles de base de datos, así como a productos. Por lo tanto, es necesario definir una relación entre los datos del archivo y la tabla del perfil, así como la tabla del producto. Esta configuración se realiza en la **[!UICONTROL Relations]** ficha de la actividad:

   * Relación con los **perfiles**: la columna **cliente** del archivo está vinculada al campo de **correo electrónico** de la dimensión **Perfiles** .
   * Relación con los **productos**: la columna de **producto** del archivo está vinculada al campo **productCode** de la dimensión **Perfiles** .
   Las columnas se agregan a los datos de entrada para hacer referencia a las claves externas de las dimensiones vinculadas.

   ![](assets/reconciliation_example3.png)

* Una **[!UICONTROL Update data]** actividad permite definir los campos de la base de datos que se actualizarán con los datos importados. Como los datos ya se identificaron como pertenecientes a la dimensión **Transacciones** en la actividad anterior, aquí puede utilizar la opción de **[!UICONTROL Directly using the targeting dimension]** identificación.

   Mediante la opción que detecta automáticamente los campos que se van a actualizar, los vínculos configurados en la actividad anterior (a perfiles y productos) se agregan a la lista de **[!UICONTROL Fields to update]**. También debe asegurarse de que el campo que corresponde a la fecha de transacción se agrega correctamente a esta lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Ejemplo 2: Identificación {#example-2--identification}

En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes. Se compone de las siguientes actividades:

![](assets/identification_example2.png)

* Una **[!UICONTROL Load file]** actividad que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

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

* Una **[!UICONTROL Reconciliation]** actividad que vincula cada columna del archivo cargado con una columna de dimensión de perfil. Los registros de archivos que no se pueden identificar (falta datos, tipo de datos incompatible, etc.) se ignoran para preservar la integridad de los datos de audiencia final.

   ![](assets/identification_example1.png)

* Una **[!UICONTROL Save audience]** actividad que guarda la audiencia de perfiles.

   ![](assets/identification_example3.png)


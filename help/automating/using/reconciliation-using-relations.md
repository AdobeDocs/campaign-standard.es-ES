---
title: Reconciliación de datos mediante relaciones
description: En el siguiente ejemplo se muestra un flujo de trabajo que actualiza la base de datos con los datos de compra de un archivo.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 86%

---


# Reconciliación de datos mediante relaciones {#reconciliation-relations}

En el siguiente ejemplo se muestra un flujo de trabajo que actualiza la base de datos con los datos de compra de un archivo. Los datos de compra contienen datos que hacen referencia a elementos de otras dimensiones, como los correos electrónicos del cliente y los códigos de producto.

>[!NOTE]
>
>Los recursos de **Transactions** y **Products** utilizados en este ejemplo no existen de forma predeterminada en la base de datos de Adobe Campaign. Por lo tanto, se crearon de antemano utilizando la función [Recursos personalizados](../../developing/using/data-model-concepts.md). Los perfiles que corresponden a las direcciones de correo electrónico del archivo importado, así como a los productos, se cargaron en la base de datos de antemano.

El flujo de trabajo se compone de las siguientes actividades:

![](assets/reconciliation_example1.png)

* A [Load file](../../automating/using/load-file.md) activity, which loads and detects the data of the file to import. El archivo importado contiene los siguientes datos:

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity to bind purchasing data to database profiles as well as products. Por lo tanto, es necesario definir una relación entre los datos del archivo y la tabla de perfiles, así como la tabla de productos. Esta configuración se realiza en la pestaña **[!UICONTROL Relations]** de la actividad:

   * Relación con **Profiles**: la columna **cliente** del archivo está vinculada al campo de **correo electrónico** de la dimensión **Profiles** .
   * Relación con **Products**: la columna de **producto** del archivo está vinculada al campo **productCode** de la dimensión **Profiles** .

   Las columnas se agregan a los datos de entrada para hacer referencia a las claves externas de las dimensiones vinculadas.

   ![](assets/reconciliation_example3.png)

* An [Update data](../../automating/using/update-data.md) activity allows you to define the database fields to update using the imported data. Como los datos ya se identificaron como pertenecientes a la dimensión **Transactions** en la actividad anterior, aquí puede utilizar la opción de identificación **[!UICONTROL Directly using the targeting dimension]**.

   Mediante la opción que detecta automáticamente los campos que se van a actualizar, los vínculos configurados en la actividad anterior (a perfiles y productos) se agregan a la lista de **[!UICONTROL Fields to update]**. También debe asegurarse de que el campo que corresponde a la fecha de transacción se agrega correctamente a esta lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

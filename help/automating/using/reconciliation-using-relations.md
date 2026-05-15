---
title: Reconciliación de datos mediante relaciones
description: En el siguiente ejemplo se muestra un flujo de trabajo que actualiza la base de datos con los datos de compra de un archivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 7d0e3f17-ef04-4890-b63b-6957fc6cd648
TQID: https://experienceleague.adobe.com/0-hk7-ypJoU-1Sw4HYmYoYnv9z9iwFrsSQoPWNyhmik
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 86%

---

# Reconciliación de datos mediante relaciones {#reconciliation-relations}

En el siguiente ejemplo se muestra un flujo de trabajo que actualiza la base de datos con los datos de compra de un archivo. Los datos de compra contienen datos que hacen referencia a elementos de otras dimensiones, como los correos electrónicos del cliente y los códigos de producto.

>[!NOTE]
>
>Los recursos de **Transactions** y **Products** utilizados en este ejemplo no existen de forma predeterminada en la base de datos de Adobe Campaign. Por lo tanto, se crearon de antemano utilizando la función [Recursos personalizados](../../developing/using/data-model-concepts.md). Los perfiles que corresponden a las direcciones de correo electrónico del archivo importado, así como a los productos, se cargaron en la base de datos de antemano.

El flujo de trabajo se compone de las siguientes actividades:

![](assets/reconciliation_example1.png)

* Una actividad [Cargar archivo](../../automating/using/load-file.md), que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

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

* Una actividad [Reconciliation](../../automating/using/reconciliation.md) para enlazar datos de compra a perfiles de base de datos y a productos. Por lo tanto, es necesario definir una relación entre los datos del archivo y la tabla de perfiles, así como la tabla de productos. Esta configuración se realiza en la pestaña **[!UICONTROL Relations]** de la actividad:

   * Relación con **Profiles**: la columna **cliente** del archivo está vinculada al campo de **correo electrónico** de la dimensión **Profiles** .
   * Relación con **Products**: la columna de **producto** del archivo está vinculada al campo **productCode** de la dimensión **Profiles** .

  Las columnas se agregan a los datos de entrada para hacer referencia a las claves externas de las dimensiones vinculadas.

  ![](assets/reconciliation_example3.png)

* Una actividad [Actualizar datos](../../automating/using/update-data.md) permite definir los campos de base de datos que se actualizarán con los datos importados. Como los datos ya se identificaron como pertenecientes a la dimensión **Transactions** en la actividad anterior, aquí puede utilizar la opción de identificación **[!UICONTROL Directly using the targeting dimension]**.

  Mediante la opción que detecta automáticamente los campos que se van a actualizar, los vínculos configurados en la actividad anterior (a perfiles y productos) se agregan a la lista de **[!UICONTROL Fields to update]**. También debe asegurarse de que el campo que corresponde a la fecha de transacción se agrega correctamente a esta lista.

  ![](assets/reconciliation_example5.png)

  ![](assets/reconciliation_example4.png)

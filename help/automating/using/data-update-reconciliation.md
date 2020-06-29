---
title: Actualización de datos mediante reconciliación
description: En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Actualización de datos mediante reconciliación {#data-update-reconciliation}

En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes. Se compone de las siguientes actividades:

![](assets/identification_example2.png)

* Una actividad [Cargar archivo](../../automating/using/load-file.md) que carga y detecta los datos del archivo que se van a importar. El archivo importado contiene los siguientes datos:

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

* actividad [Reconciliación](../../automating/using/reconciliation.md) que vincula cada columna del archivo cargado con una columna de dimensión de perfil. Los registros de archivos que no se pueden identificar (falta datos, tipo de datos incompatible, etc.) se ignoran para preservar la integridad de los datos de audiencia final.

   ![](assets/identification_example1.png)

* actividad [Guardar audiencia](../../automating/using/save-audience.md) , que guarda la audiencia de perfiles.

   ![](assets/identification_example3.png)

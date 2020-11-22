---
solution: Campaign Standard
product: campaign
title: Actualización de datos mediante reconciliación
description: En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---


# Actualización de datos mediante reconciliación {#data-update-reconciliation}

En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes. Se compone de las siguientes actividades:

![](assets/identification_example2.png)

* A [Load file](../../automating/using/load-file.md) activity, which loads and detects tshe data of the file to import. El archivo importado contiene los siguientes datos:

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity, which links each column of the loaded file to a profile dimension column. Los registros de archivos que no se pueden identificar (por falta de datos, tipo de datos incompatible, etc.) se ignoran para preservar la integridad de los datos de audiencia final.

   ![](assets/identification_example1.png)

* A [Save audience](../../automating/using/save-audience.md) activity, which saves the audience of profiles.

   ![](assets/identification_example3.png)

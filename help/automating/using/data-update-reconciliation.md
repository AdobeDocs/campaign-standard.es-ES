---
title: Actualización de datos mediante reconciliación
description: En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 52%

---

# Actualización de datos mediante reconciliación {#data-update-reconciliation}

En el siguiente ejemplo se muestra un flujo de trabajo que crea una audiencia de perfiles directamente desde un archivo importado que contiene nuevos clientes. Se compone de las siguientes actividades:

![](assets/identification_example2.png)

* Una actividad [Cargar archivo](../../automating/using/load-file.md), que carga y detecta los datos del archivo que se va a importar. El archivo importado contiene los siguientes datos:

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

* Una actividad [Reconciliation](../../automating/using/reconciliation.md) que vincula cada columna del archivo cargado con una columna de dimensión de perfil. Los registros de archivos que no se pueden identificar (por falta de datos, tipo de datos incompatible, etc.) se ignoran para preservar la integridad de los datos de audiencia final.

  ![](assets/identification_example1.png)

* Una actividad [Guardar audiencia](../../automating/using/save-audience.md), que guarda la audiencia de perfiles.

  ![](assets/identification_example3.png)

---
title: Actualización de la base de datos con datos externos
description: Este caso de uso presenta cómo añadir o actualizar perfiles a la base de datos de Adobe Campaign con los datos recuperados del archivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%

---

# Actualización de la base de datos con datos externos {#update-database-file}

El siguiente ejemplo muestra la configuración de una actividad **[!UICONTROL Update data]** después de una actividad **[!UICONTROL Load file]**. El objetivo de este flujo de trabajo es añadir o actualizar perfiles a la base de datos de Adobe Campaign con los datos recuperados del archivo.

En este ejemplo, la clave de reconciliación utilizada es **la dirección de correo electrónico**. El archivo cargado en la actividad [Cargar archivo](../../automating/using/load-file.md) es un archivo de formato **.txt** que contiene los siguientes datos de ejemplo:

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

La actividad [Actualizar datos](../../automating/using/update-data.md) está configurada de la siguiente manera:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

---
title: Deduplicación de datos de un archivo importado
description: Este ejemplo muestra cómo deduplicar datos de un archivo importado antes de cargar los datos en la base de datos.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 631eb661-a696-4352-aa58-9097b391723e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 89%

---

# Deduplicación de datos de un archivo importado {#deduplicating-the-data-from-an-imported-file}

Este ejemplo muestra cómo deduplicar datos de un archivo importado antes de cargar los datos en la base de datos. Este procedimiento mejora la calidad de los datos cargados en la base de datos.

El flujo de trabajo consta de:

![](assets/deduplication_example2_workflow.png)

* Un archivo que contiene una lista de perfiles se importa mediante una [Cargar archivo](../../automating/using/load-file.md) actividad. En este ejemplo, el archivo importado está en formato .csv y contiene 10 perfiles:

  ```
  lastname;firstname;dateofbirth;email
  Smith;Hayden;23/05/1989;hayden.smith@example.com
  Mars;Daniel;17/11/1987;dannymars@example.com
  Smith;Clara;08/02/1989;hayden.smith@example.com
  Durance;Allison;15/12/1978;allison.durance@example.com
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com
  Binder;Tom;19/01/1982;tombinder@example.com
  Binder;Tommy;19/01/1915;tombinder@example.com
  Connor;Jade;10/10/1979;connor.jade@example.com
  Mack;Clarke;02/03/1985;clarke.mack@example.com
  Ross;Timothy;04/07/1986;timross@example.com
  ```

  Este archivo también puede utilizarse como archivo de muestra para detectar y definir el formato de las columnas. Desde la pestaña **[!UICONTROL Column definition]**, asegúrese de que cada columna del archivo importado esté configurada correctamente.

  ![](assets/deduplication_example2_fileloading.png)

* A [Deduplicación](../../automating/using/deduplication.md) actividad. La deduplicación se realiza directamente después de importar el archivo y antes de insertar los datos en la base de datos. Por lo tanto, debe basarse en el **[!UICONTROL Temporary resource]** de la actividad de **[!UICONTROL Load file]**.

  Para este ejemplo, queremos mantener una sola entrada por dirección de correo electrónico única contenida en el archivo. Por lo tanto, la identificación del duplicado se lleva a cabo en la columna de **correo electrónico** del recurso temporal. Sin embargo, aparecen dos veces en el archivo dos direcciones de correo electrónico. Por consiguiente, las dos líneas se considerarán duplicados.

  ![](assets/deduplication_example2_dedup.png)

* Un [Actualización de datos](../../automating/using/update-data.md) La actividad de le permite insertar los datos guardados desde el proceso de deduplicación en la base de datos. Solo cuando se actualizan los datos, se identifican los datos importados como pertenecientes a la dimensión de perfil.

  En este caso, nos gustaría **[!UICONTROL Insert only]** los perfiles que no existen en la base de datos. Vamos a hacerlo utilizando la columna de correo electrónico del archivo y el campo de correo electrónico de la dimensión de **Perfil** como clave de reconciliación.

  ![](assets/deduplication_example2_writer1.png)

  Especifique las asignaciones entre las columnas del archivo desde las que desea insertar los datos y los campos de la base de datos desde la pestaña **[!UICONTROL Fields to update]**.

  ![](assets/deduplication_example2_writer2.png)

A continuación, inicie el flujo de trabajo. Los registros guardados desde el proceso de deduplicación se añaden entonces a los perfiles de la base de datos.

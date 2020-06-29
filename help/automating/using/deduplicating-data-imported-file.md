---
title: Desduplicación de datos de un archivo importado
description: En este ejemplo se muestra cómo anular la duplicación de datos de un archivo importado antes de cargar los datos en la base de datos.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Desduplicación de datos de un archivo importado {#deduplicating-the-data-from-an-imported-file}

En este ejemplo se muestra cómo anular la duplicación de datos de un archivo importado antes de cargar los datos en la base de datos. Este procedimiento mejora la calidad de los datos cargados en la base de datos.

El flujo de trabajo se compone de:

![](assets/deduplication_example2_workflow.png)

* Un archivo que contiene una lista de perfiles se importa mediante una actividad [Cargar archivo](../../automating/using/load-file.md) . En este ejemplo, el archivo importado tiene formato .csv y contiene 10 perfiles:

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

   Este archivo también puede utilizarse como archivo de muestra para detectar y definir el formato de las columnas. Desde la **[!UICONTROL Column definition]** ficha, asegúrese de que cada columna del archivo importado está configurada correctamente.

   ![](assets/deduplication_example2_fileloading.png)

* Una actividad [Deduplicación](../../automating/using/deduplication.md) . La Deduplicación se realiza directamente después de importar el archivo y antes de insertar los datos en la base de datos. Por lo tanto, debe basarse en la **[!UICONTROL Temporary resource]** información de la **[!UICONTROL Load file]** actividad.

   Para este ejemplo, queremos mantener una sola entrada por dirección de correo electrónico única contenida en el archivo. Por lo tanto, la identificación del Duplicado se lleva a cabo en la columna de **correo electrónico** del recurso temporal. Sin embargo, dos direcciones de correo electrónico aparecen dos veces en el archivo. Por consiguiente, se considerarán duplicados dos líneas.

   ![](assets/deduplication_example2_dedup.png)

* Una actividad de [actualización de datos](../../automating/using/update-data.md) permite insertar los datos que se conservan desde el proceso de deduplicación en la base de datos. Sólo cuando se actualizan los datos se identifican los datos importados como pertenecientes a la dimensión de perfil.

   En este caso, nos gustaría conocer **[!UICONTROL Insert only]** los perfiles que no existen en la base de datos. Vamos a hacer esto utilizando la columna de correo electrónico del archivo y el campo de correo electrónico de la dimensión de **Perfil** como clave de reconciliación.

   ![](assets/deduplication_example2_writer1.png)

   Especifique las asignaciones entre las columnas del archivo desde las que desea insertar los datos y los campos de la base de datos desde la **[!UICONTROL Fields to update]** ficha.

   ![](assets/deduplication_example2_writer2.png)

A continuación, inicio el flujo de trabajo. Los registros guardados desde el proceso de deduplicación se agregan a los perfiles de la base de datos.

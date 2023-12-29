---
title: Deduplicación
description: La actividad de deduplicación le permite eliminar duplicados en los resultados de las actividades entrantes.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 57c56e4a-892c-46d6-9bb4-6a345a8d9f5b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 96%

---

# Anulación de duplicación{#deduplication}

## Descripción {#description}

![](assets/deduplication.png)

La actividad **[!UICONTROL Deduplication]** le permite eliminar duplicados en los resultados de las actividades entrantes.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Deduplication]** se utiliza generalmente después de actividades de segmentación o después de importar un archivo y antes de actividades que permiten el uso de datos de objetivo.

Durante la deduplicación, las transiciones entrantes se procesan por separado. Por ejemplo, si el perfil “A” está presente como resultado de la consulta 1 y también como resultado de la consulta 2, no se deduplicará.

Por lo tanto, se aconseja que una deduplicación solo tenga una transición entrante. Para ello, puede combinar sus diferentes consultas mediante actividades que se correspondan con sus necesidades de segmentación, como una actividad de unión, una actividad de intersección, etc. Por ejemplo:

![](assets/dedup_bonnepratique.png)

**Temas relacionados**

* [Caso de uso: Identificación de duplicados antes de una entrega](../../automating/using/identifying-duplicated-before-delivery.md)
* [Caso de uso: Deduplicación de datos de un archivo importado](../../automating/using/deduplicating-data-imported-file.md)

## Configuración {#configuration}

Para configurar una actividad de deduplicación, debe introducir una etiqueta, el método y los criterios de deduplicación, así como las opciones relacionadas con el resultado.

1. Arrastre y suelte una actividad de **[!UICONTROL Deduplication]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.

   ![](assets/deduplication_1.png)

1. Seleccione el **[!UICONTROL Resource type]** en que debe llevarse a cabo la deduplicación:

   * **[!UICONTROL Database resource]** si la deduplicación se realiza sobre datos que ya existen en la base de datos. Seleccione **[!UICONTROL Filtering dimension]** y **[!UICONTROL Targeting dimension]**, en función de los datos que desee deduplicar. De forma predeterminada, la deduplicación se realiza en los **perfiles**.
   * **[!UICONTROL Temporary resource]** si la deduplicación se realiza en los datos temporales del flujo de trabajo: seleccione el **[!UICONTROL Targeted set]** que contiene los datos que desea deduplicar. Este caso de uso se puede encontrar después de importar un archivo o si los datos de la base de datos se han enriquecido (por ejemplo, con un código de segmento).

1. Seleccione el **[!UICONTROL Number of unique records to keep]**. El valor predeterminado de este campo es 1. El valor 0 le permite mantener todos los duplicados.

   Por ejemplo, si los registros A y B se consideran duplicados del registro Y, y un registro C se considera un duplicado del registro Z:

   * Si el valor del campo es 1: solo se guardan los registros Y y Z.
   * Si el valor del campo es 0: se guardan todos los registros.
   * Si el valor del campo es 2: se conservan los registros C y Z y se conservan dos registros de A, B e Y, al azar o en función del método de deduplicación seleccionado posteriormente.

1. Defina los criterios **[!UICONTROL Duplicate identification]** agregando condiciones en la lista proporcionada. Especifique los campos o expresiones para los que los valores idénticos permiten identificar los duplicados: dirección de correo electrónico, nombre, apellidos, etc. El orden de las condiciones le permite especificar las que se procesarán en primer lugar.
1. En la lista desplegable, seleccione el **[!UICONTROL Deduplication method]** que desee utilizar:

   * **[!UICONTROL Choose for me]**: selecciona de forma aleatoria el registro que se va a excluir de los duplicados.
   * **[!UICONTROL Following a list of values]**: permite definir una prioridad de valor para uno o varios campos. Para definir los valores, seleccione un campo o cree una expresión y, a continuación, añada los valores a la tabla adecuada. Para definir un nuevo campo, haga clic en el botón **[!UICONTROL Add]** situado sobre la lista de valores.

     ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: esto permite mantener registros para los que el valor de la expresión seleccionada no está vacío como prioridad.

     ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: esto le permite mantener los registros en los que el valor de la expresión introducida es el más pequeño o el más grande.

     ![](assets/deduplication_4.png)

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

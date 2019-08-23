---
title: Enriquecimiento
seo-title: Enriquecimiento
description: Enriquecimiento
seo-description: La actividad Enriquecimiento es una actividad avanzada que permite definir datos adicionales para procesar en el flujo de trabajo.
page-status-flag: no activado nunca
uuid: 8 c 1693 ef -1312-422 c-b 05 d -263553113 f 8 f f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: f 67 c 1 caf -3284-4 c 34-a 5 b 0-8654 a 95640 ae
context-tags: enriquecimiento, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Enriquecimiento{#enrichment}

## Descripción {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** La actividad es una actividad avanzada que permite definir datos adicionales para procesar en el flujo de trabajo.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Enrichment]** actividad se utiliza generalmente después de actividades de segmentación o después de importar un archivo y antes de las actividades que permiten el uso de datos de objetivo.

Esta actividad contiene funciones de enriquecimiento más avanzadas que la **[!UICONTROL Query]** actividad. Algunos casos simples de enriquecimiento se pueden realizar directamente en la actividad [Consulta](../../automating/using/query.md#enriching-data).

Con **[!UICONTROL Enrichment]** la actividad, puede aprovechar la transición entrante y configurar la actividad para completar la transición de salida con datos adicionales. Permite combinar datos provenientes de varios conjuntos o crear vínculos a un recurso temporal.

## Configuración {#configuration}

Para configurar una **[!UICONTROL Enrichment]** actividad:

1. Arrastre y suelte una **[!UICONTROL Enrichment]** actividad en el flujo de trabajo.
1. Seleccione la actividad y ábrala utilizando ![](assets/edit_darkgrey-24px.png) el botón de las acciones rápidas que aparecen.
1. Si la actividad tiene varias transiciones entrantes, seleccione la **[!UICONTROL Primary set]**. Los datos adicionales configurados en esta actividad se agregarán a este conjunto primario de la transición saliente.

   Si el conjunto principal ya contiene datos adicionales, puede optar por mantenerlos o eliminarlos. Si desactiva la **[!UICONTROL Keep all additional data from the main set]** opción, solo se mantendrán los datos adicionales **[!UICONTROL Enrichment]** configurados en la transición saliente.

1. Si hay varias transiciones de entrada, defina las relaciones entre el conjunto principal y los demás datos entrantes en la **[!UICONTROL Advanced Relations]** ficha de la actividad. Puede agregar varias relaciones mediante **[!UICONTROL Add element]** el botón.

   Al definir una nueva relación, seleccione el conjunto de datos entrantes que desea vincular al conjunto principal. A continuación, defina el tipo de relación. Hay varios tipos de relaciones disponibles, según los datos de entrada y el modelo de datos:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro de los datos entrantes está asociado a uno y solo a un registro del conjunto principal. Cada registro del conjunto primario tiene un registro asociado en los datos vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o más (N) registros de los datos vinculados pueden asociarse con 1 registro del conjunto primario.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: los registros del conjunto principal pueden asociarse con 0 o 1 registros de los datos vinculados, pero no más de uno.
   Una vez definido, **[!UICONTROL Cardinality]** defina **[!UICONTROL Reconciliation criteria]** un. **[!UICONTROL Source expression]** Los criterios de reconciliación pueden ser un campo del recurso de destino, una [expresión](../../automating/using/advanced-expression-editing.md) o directamente un valor especificado entre comillas.

   Defina un **[!UICONTROL Label]** y un **[!UICONTROL ID]** que será fácil de identificar posteriormente en el flujo de trabajo.

   >[!NOTE]
   >
   >Solo puede definir las relaciones entre el conjunto principal y las otras transiciones entrantes conectadas a **[!UICONTROL Enrichment]** la actividad. Para casos simples que tengan como objetivo definir relaciones con recursos de base de datos, utilice una actividad [de reconciliación](../../automating/using/reconciliation.md) .

1. Defina los datos adicionales de **[!UICONTROL Additional data]** la ficha de la actividad. Puede definir datos adicionales (campos simples, agregados y colecciones) relacionados con la dimensión de objetivo del conjunto principal o en función de los vínculos creados en **[!UICONTROL Advanced relations]** la ficha de **[!UICONTROL Enrichment]** la actividad.

   Consulte la sección [de datos](../../automating/using/query.md#enriching-data) enriquecer.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

Ahora los datos se pueden usar en las actividades conectadas después de **[!UICONTROL Enrichment]** la. Por ejemplo, puede encontrarlo bajo **[!UICONTROL Additional data (targetData)]** el vínculo del explorador Campos de personalización en un contenido de correo electrónico.

## Ejemplo: Enriquecimiento de datos de perfil con datos contenidos en un archivo {#example--enriching-profile-data-with-data-contained-in-a-file}

Este ejemplo muestra cómo enriquecer los datos de perfil con los datos de compra contenidos en un archivo. Aquí se considera que los datos de compra se almacenan en un sistema de terceros. Cada perfil puede tener varias compras almacenadas en el archivo. El objetivo final del flujo de trabajo es enviar un correo electrónico a los perfiles de destino que han comprado al menos dos artículos para agradecerles su lealtad.

El flujo de trabajo se configura de la siguiente manera:

![](assets/enrichment_example_workflow.png)

* **[!UICONTROL Query]** Actividad dirigida a los perfiles que recibirán el mensaje.
* **[!UICONTROL Load file]** Actividad que carga los datos de compra. Por ejemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Con este archivo de ejemplo, usaremos la dirección de correo electrónico para reconciliar los datos con los perfiles de la base de datos. También puede habilitar ID únicos como se describe en [este documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Actividad que crea un vínculo entre los datos de transacción cargados desde el archivo y los perfiles seleccionados en **[!UICONTROL Query]** la. El vínculo se define en **[!UICONTROL Advanced relations]** la ficha de la actividad. El vínculo se basa en la transición proveniente de **[!UICONTROL Load file]** la actividad. Utiliza el campo «correo electrónico» del recurso de perfil y la columna «cliente» del archivo importado como criterio de reconciliación.

   ![](assets/enrichment_example_workflow2.png)

   Una vez creado el vínculo, se agregan dos conjuntos **[!UICONTROL Additional data]** de elementos:

   * Una colección de dos líneas correspondientes a las dos últimas transacciones de cada perfil. Para esta colección, el nombre del producto, la fecha de transacción y el precio del producto se agregan como datos adicionales. Se aplica una ordenación descendente en los datos. Para crear la colección, desde **[!UICONTROL Additional data]** la ficha:

      Seleccione el vínculo definido anteriormente en **[!UICONTROL Advanced relations]** la ficha de la actividad.

      ![](assets/enrichment_example_workflow3.png)

      Marque **[!UICONTROL Collection]** y especifique el número de líneas que desea recuperar (2 en este ejemplo). En esta pantalla, puede personalizar el **[!UICONTROL Alias]** y el **[!UICONTROL Label]** de la colección. Estos valores serán visibles en las siguientes actividades del flujo de trabajo al hacer referencia a esta colección.

      ![](assets/enrichment_example_workflow4.png)

      Al igual **[!UICONTROL Data]** que para la colección, seleccione las columnas que se utilizarán en la entrega final.

      ![](assets/enrichment_example_workflow6.png)

      Aplique un orden descendente en la fecha de transacción para asegurarse de recuperar las transacciones más recientes.

      ![](assets/enrichment_example_workflow7.png)

   * Recuento agregado del número total de transacciones para cada perfil. Este agregado se utilizará más tarde para filtrar perfiles que tienen al menos dos transacciones registradas. Para crear el agregado, en **[!UICONTROL Additional data]** la ficha:

      Seleccione el vínculo definido anteriormente en **[!UICONTROL Advanced relations]** la ficha de la actividad.

      ![](assets/enrichment_example_workflow3.png)

      Seleccione **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Para **[!UICONTROL Data]** conservar, defina un **valor de Recuento todo** . Si lo necesita, especifique un alias personalizado para encontrarlo más rápido en las siguientes actividades.

      ![](assets/enrichment_example_workflow9.png)

* **[!UICONTROL Segmentation]** Actividad con un solo segmento que recupera perfiles del objetivo inicial que tienen al menos dos transacciones registradas. Solo se excluirán los perfiles con una transacción. Para ello, la consulta de la segmentación se realiza en el conjunto definido previamente.

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** Actividad que utiliza los datos adicionales definidos en la **[!UICONTROL Enrichment]** para recuperar dinámicamente las dos últimas compras realizadas por el perfil. Los datos adicionales se pueden encontrar en el nodo Datos **adicionales (targetdata)** al agregar un campo de personalización.

   ![](assets/enrichment_example_workflow10.png)

**Tema relacionado:**

* [Enriquecimiento de perfiles de cliente con datos externos](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)


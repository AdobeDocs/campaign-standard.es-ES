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
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## Description {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** La actividad es una actividad avanzada que permite definir datos adicionales para procesar en el flujo de trabajo.

## Context of use {#context-of-use}

The **[!UICONTROL Enrichment]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

With the **[!UICONTROL Enrichment]** activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data. Permite combinar datos provenientes de varios conjuntos o crear vínculos a un recurso temporal.

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. Los datos adicionales configurados en esta actividad se agregarán a este conjunto primario de la transición saliente.

   Si el conjunto principal ya contiene datos adicionales, puede optar por mantenerlos o eliminarlos. If you uncheck the **[!UICONTROL Keep all additional data from the main set]** option, only the additional data configured in the **[!UICONTROL Enrichment]** are kept in the outbound transition.

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. You can add several relations using the **[!UICONTROL Add element]** button.

   Al definir una nueva relación, seleccione el conjunto de datos entrantes que desea vincular al conjunto principal. A continuación, defina el tipo de relación. Hay varios tipos de relaciones disponibles, según los datos de entrada y el modelo de datos:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro de los datos entrantes está asociado a uno y solo a un registro del conjunto principal. Cada registro del conjunto primario tiene un registro asociado en los datos vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o más (N) registros de los datos vinculados pueden asociarse con 1 registro del conjunto primario.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: los registros del conjunto principal pueden asociarse con 0 o 1 registros de los datos vinculados, pero no más de uno.
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. **[!UICONTROL Source expression]** Los criterios de reconciliación pueden ser un campo del recurso de destino, una [expresión](../../automating/using/advanced-expression-editing.md) o directamente un valor especificado entre comillas.

   Define a **[!UICONTROL Label]** and an **[!UICONTROL ID]** that will be easy to identify later in the workflow.

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

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

   Con este archivo de ejemplo, usaremos la dirección de correo electrónico para reconciliar los datos con los perfiles de la base de datos. You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Actividad que crea un vínculo entre los datos de transacción cargados desde el archivo y los perfiles seleccionados en **[!UICONTROL Query]** la. The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. Utiliza el campo «correo electrónico» del recurso de perfil y la columna «cliente» del archivo importado como criterio de reconciliación.

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * Una colección de dos líneas correspondientes a las dos últimas transacciones de cada perfil. Para esta colección, el nombre del producto, la fecha de transacción y el precio del producto se agregan como datos adicionales. Se aplica una ordenación descendente en los datos. To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. Estos valores serán visibles en las siguientes actividades del flujo de trabajo al hacer referencia a esta colección.

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      Aplique un orden descendente en la fecha de transacción para asegurarse de recuperar las transacciones más recientes.

      ![](assets/enrichment_example_workflow7.png)

   * Recuento agregado del número total de transacciones para cada perfil. Este agregado se utilizará más tarde para filtrar perfiles que tienen al menos dos transacciones registradas. To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. Si lo necesita, especifique un alias personalizado para encontrarlo más rápido en las siguientes actividades.

      ![](assets/enrichment_example_workflow9.png)

* **[!UICONTROL Segmentation]** Actividad con un solo segmento que recupera perfiles del objetivo inicial que tienen al menos dos transacciones registradas. Solo se excluirán los perfiles con una transacción. Para ello, la consulta de la segmentación se realiza en el conjunto definido previamente.

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** Actividad que utiliza los datos adicionales definidos en la **[!UICONTROL Enrichment]** para recuperar dinámicamente las dos últimas compras realizadas por el perfil. The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)


---
title: Reconciliación
description: La actividad Reconciliación le permite vincular datos no identificados a recursos existentes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 95%

---

# Reconciliación{#reconciliation}

## Descripción {#description}

![](assets/reconciliation.png)

La actividad **[!UICONTROL Reconciliation]** le permite vincular datos no identificados a recursos existentes.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Reconciliation]** se utiliza esencialmente con fines de gestión de datos e implica dos casos de uso diferentes:

* Añadir relaciones: una pestaña **[!UICONTROL Links]** permite agregar vínculos entre los datos de entrada y otras dimensiones de la base de datos de Adobe Campaign.

   Por ejemplo, un archivo que contenga datos de compra también puede tener información para identificar tanto a los productos comprados como al comprador. Dos dimensiones adicionales (además de la de **Purchases**) están preocupadas por los datos del archivo: las dimensiones **Products** y **Profiles**. Luego deben crearse relaciones entre estas y la dimensión **Purchases** (consulte el siguiente ejemplo).

   Al definir una relación, se agrega una columna a los datos de entrada para hacer referencia a la clave externa de la dimensión vinculada.

   >[!NOTE]
   >
   >Esta operación implica que los datos de las dimensiones vinculadas ya están en la base de datos. Por ejemplo, si importa un archivo de compras que muestre qué producto se compró, a qué hora, por qué cliente, etc., el producto y el cliente ya deben existir en la base de datos.

* Identificación de datos: una pestaña **[!UICONTROL Identification]** permite simplemente vincular datos de entrada a columnas de una dimensión existente en la base de datos de Adobe Campaign. Después de la actividad, los datos se identifican como pertenecientes a la dimensión definida.

   Por ejemplo, puede guardar una audiencia, actualizar la base de datos, etc.

Por ejemplo, la actividad **[!UICONTROL Reconciliation]** se puede colocar después de una actividad de datos de carga con el fin de importar datos no estándar en la base de datos.

**Temas relacionados:**

* [Caso de uso: Reconciliación de datos mediante relaciones](../../automating/using/reconciliation-using-relations.md)
* [Caso de uso: Actualización de datos mediante reconciliación](../../automating/using/data-update-reconciliation.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Reconciliation]** en el flujo de trabajo siguiendo una transición que contenga una población cuya dimensión de segmentación no provenga directamente de Adobe Campaign. Para obtener más información sobre esto, consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Si desea definir vínculos entre los datos de entrada y otras dimensiones de base de datos, vaya a la pestaña **[!UICONTROL Links]**.

   Añada tantas relaciones como sea necesario. Para cada relación, primero seleccione la dimensión vinculada y, luego, en el detalle del vínculo, especifique los campos correspondientes.

1. Si desea simplemente identificar los datos de entrada, vaya a la pestaña **[!UICONTROL Identification]** y marque la casilla **[!UICONTROL Identify the document from the working data]**.

   Seleccione la dimensión de segmentación a la que desea reconciliar los datos de entrada.

   Añada criterios de reconciliación para vincular un registro de transición entrante a un registro de dimensión de segmentación seleccionado. Si se especifican varios criterios, todos deben verificarse para que funcione el vínculo entre todos sus datos.

   Elija el modo **[!UICONTROL Processing unidentified source lines]**:

   * **[!UICONTROL Ignore them]**: solo los datos identificables se conservan en la transición saliente de la actividad.
   * **[!UICONTROL Keep in the outbound population]**: todos los datos de la transición entrante se guardan en la transición saliente de la actividad.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

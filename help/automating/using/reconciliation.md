---
title: Reconciliación
description: La actividad Reconciliación permite vincular datos no identificados a recursos existentes.
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
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---


# Reconciliación{#reconciliation}

## Descripción {#description}

![](assets/reconciliation.png)

La **[!UICONTROL Reconciliation]** actividad le permite vincular datos no identificados a recursos existentes.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Reconciliation]** actividad se utiliza esencialmente con fines de Gestión de datos e implica dos casos de uso diferentes:

* Añadir relaciones: una **[!UICONTROL Links]** ficha permite agregar vínculos entre los datos de entrada y otras dimensiones de la base de datos de Adobe Campaign.

   Por ejemplo, un archivo que contenga datos de compra también puede contener información para identificar tanto los productos comprados como el comprador. Dos dimensiones adicionales (además de la de **Compras**) están preocupadas por los datos del archivo: las dimensiones **Productos** y **Perfiles** . Luego deben crearse relaciones entre éstas y la dimensión **Compras** (consulte el siguiente ejemplo).

   Al definir una relación, se agrega una columna a los datos de entrada para hacer referencia a la clave externa de la dimensión vinculada.

   >[!NOTE]
   >
   >Esta operación implica que los datos de las dimensiones vinculadas ya están en la base de datos. Por ejemplo, si importa un archivo de compras que muestre qué producto se compró, a qué hora, por qué cliente, etc., el producto y el cliente ya deben existir en la base de datos.

* Identificación de datos: una **[!UICONTROL Identification]** ficha permite simplemente vincular datos de entrada a columnas de una dimensión existente en la base de datos de Adobe Campaign. Después de la actividad, los datos se identifican como pertenecientes a la dimensión definida.

   Por ejemplo, puede realizar una audiencia de almacenamiento, una actualización de la base de datos, etc.

Por ejemplo, la **[!UICONTROL Reconciliation]** actividad se puede colocar después de una actividad de datos de carga con el fin de importar datos no estándar en la base de datos.

**Temas relacionados:**

* [Caso de uso: Reconciliación de datos mediante relaciones](../../automating/using/reconciliation-using-relations.md)
* [Caso de uso: Actualización de datos mediante reconciliación](../../automating/using/data-update-reconciliation.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Reconciliation]** actividad en el flujo de trabajo, siguiendo una transición que contenga una población cuya dimensión de segmentación no proviene directamente del Adobe Campaign. Para obtener más información sobre esto, consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Si desea definir vínculos entre los datos de entrada y otras dimensiones de base de datos, vaya a la **[!UICONTROL Links]** ficha .

   Añada tantas relaciones como sea necesario. Para cada relación, primero seleccione la dimensión vinculada y luego, en el detalle del vínculo, especifique los campos correspondientes.

1. Si desea simplemente identificar los datos de entrada, vaya a la **[!UICONTROL Identification]** ficha y marque la **[!UICONTROL Identify the document from the working data]** casilla.

   Seleccione la dimensión de segmentación a la que desea reconciliar los datos de entrada.

   Añada criterios de reconciliación para vincular un registro de transición entrante a un registro de dimensión de segmentación seleccionado. Si se especifican varios criterios, todos deben verificarse para que funcione el vínculo entre todos sus datos.

   Elija el **[!UICONTROL Processing unidentified source lines]** modo:

   * **[!UICONTROL Ignore them]**:: sólo los datos identificables se conservan en la transición saliente de la actividad.
   * **[!UICONTROL Keep in the outbound population]**:: todos los datos de la transición entrante se guardan en la transición saliente de la actividad.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

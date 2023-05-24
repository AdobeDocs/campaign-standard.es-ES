---
title: Enriquecimiento
description: La actividad Enriquecimiento es una actividad avanzada que le permite definir datos adicionales para procesarlos en el flujo de trabajo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c8af67b0-6789-4b4e-9d01-e2dfa14f1e8f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---

# Enriquecimiento{#enrichment}

## Descripción {#description}

![](assets/enrichment.png)

La actividad **[!UICONTROL Enrichment]** es una actividad avanzada que le permite definir datos adicionales para procesarlos en el flujo de trabajo.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Enrichment]** se utiliza generalmente después de actividades de segmentación o después de importar un archivo y antes de actividades que permiten el uso de datos de objetivo.

Esta actividad contiene funciones de enriquecimiento más avanzadas que la actividad de **[!UICONTROL Query]**. Algunos casos sencillos de enriquecimiento se pueden realizar directamente en la [actividad de consulta](../../automating/using/query.md#enriching-data).

Con la actividad de **[!UICONTROL Enrichment]**, puede aprovechar la transición de entrada y configurar la actividad para completar la transición de salida con datos adicionales. Permite combinar datos procedentes de varios conjuntos o crear vínculos a un recurso temporal.

**Temas relacionados**

* [Caso de uso: enriquecimiento de datos de perfil con datos contenidos en un archivo](../../automating/using/enriching-profile-data-file.md).
* [Caso de uso: Envío de un correo electrónico con campos enriquecidos](../../automating/using/sending-email-enriched-fields.md)

## Configuración {#configuration}

Para configurar una actividad de **[!UICONTROL Enrichment]**:

1. Arrastre y suelte una actividad de **[!UICONTROL Enrichment]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Si la actividad tiene varias transiciones de entrada, seleccione la opción **[!UICONTROL Primary set]**. Los datos adicionales configurados en esta actividad se añaden a este conjunto principal en la transición de salida.

   Si el conjunto principal ya contiene datos adicionales, puede optar por conservarlos o eliminarlos. Si desmarca la opción **[!UICONTROL Keep all additional data from the main set]**, solo los datos adicionales configurados en la actividad de **[!UICONTROL Enrichment]** se guardan en la transición de salida.

1. Si hay varias transiciones de entrada, defina las relaciones entre el conjunto primario y los demás datos de entrada en la pestaña **[!UICONTROL Advanced Relations]** de la actividad. Puede añadir varias relaciones con el botón **[!UICONTROL Add element]**.

   Al definir una nueva relación, seleccione el conjunto de datos de entrada que quiera vincular al conjunto principal. A continuación, defina el tipo de relación. Existen varios tipos de relaciones disponibles, según los datos de entrada y el modelo de datos:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro de los datos de entrada se asocia a un registro del conjunto principal y solo a uno. Cada registro del conjunto principal tiene un registro asociado en los datos vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o más registros (N) de los datos vinculados se pueden asociar a 1 registro del conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: los registros del conjunto principal pueden asociarse con 0 o 1 registro de los datos vinculados, pero no más de uno.

   Una vez definido el **[!UICONTROL Cardinality]**, defina un **[!UICONTROL Reconciliation criteria]**. La **[!UICONTROL Source expression]** de los criterios de reconciliación puede ser un campo del recurso de destino, una [expresión](../../automating/using/advanced-expression-editing.md) o directamente un valor especificado entre comillas.

   Defina una **[!UICONTROL Label]** y un **[!UICONTROL ID]** que resulten fáciles de identificar más adelante en el flujo de trabajo.

   >[!NOTE]
   >
   >Solo se pueden definir relaciones entre el conjunto principal y las demás transiciones de entrada conectadas a la actividad de **[!UICONTROL Enrichment]**. Para casos más sencillos con el fin de definir las relaciones con los recursos de la base de datos, utilice una actividad de [reconciliación](../../automating/using/reconciliation.md).

1. Defina los datos adicionales desde la pestaña **[!UICONTROL Additional data]** de la actividad. Puede definir datos adicionales (campos simples, añadidos y colecciones) relacionados con la dimensión de segmentación del conjunto principal o basados en los vínculos creados en la pestaña **[!UICONTROL Advanced relations]** de la actividad de **[!UICONTROL Enrichment]**.

   Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Los datos ahora están disponibles para su uso en las actividades conectadas después del **[!UICONTROL Enrichment]**. Por ejemplo, puede encontrarlo en el vínculo **[!UICONTROL Additional data (targetData)]** del explorador de campos de personalización en un contenido de correo electrónico.

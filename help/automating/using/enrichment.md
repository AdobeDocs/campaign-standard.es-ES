---
title: Enriquecimiento
description: La actividad de Enriquecimiento es una actividad avanzada que le permite definir datos adicionales para procesar en el flujo de trabajo.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# Enriquecimiento{#enrichment}

## Descripción {#description}

![](assets/enrichment.png)

La **[!UICONTROL Enrichment]** actividad es una actividad avanzada que le permite definir datos adicionales para procesar en el flujo de trabajo.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Enrichment]** actividad se utiliza generalmente después de actividades de objetivo o después de importar un archivo y antes de actividades que permiten el uso de datos de objetivo.

Esta actividad contiene funciones de enriquecimiento más avanzadas que la **[!UICONTROL Query]** actividad. Algunos casos sencillos de enriquecimiento se pueden realizar directamente en la actividad [de](../../automating/using/query.md#enriching-data)Consulta.

Con la **[!UICONTROL Enrichment]** actividad, puede aprovechar la transición de entrada y configurar la actividad para completar la transición de salida con datos adicionales. Permite combinar datos procedentes de varios conjuntos o crear vínculos a un recurso temporal.

**Temas relacionados**

* [Caso de uso: Enriquecimiento de datos de perfil con datos contenidos en un archivo](../../automating/using/enriching-profile-data-file.md).
* [Caso de uso: Envío de un correo electrónico con campos enriquecidos](../../automating/using/sending-email-enriched-fields.md)

## Configuración {#configuration}

Para configurar una **[!UICONTROL Enrichment]** actividad:

1. Arrastre y suelte una **[!UICONTROL Enrichment]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Si la actividad tiene varias transiciones de entrada, seleccione la opción **[!UICONTROL Primary set]**. Los datos adicionales configurados en esta actividad se agregarán a este conjunto principal en la transición saliente.

   Si el conjunto principal ya contiene datos adicionales, puede optar por conservarlos o eliminarlos. Si desmarca la **[!UICONTROL Keep all additional data from the main set]** opción, solo los datos adicionales configurados en la **[!UICONTROL Enrichment]** se guardan en la transición de salida.

1. Si hay varias transiciones de entrada, defina las relaciones entre el conjunto primario y los demás datos de entrada en la **[!UICONTROL Advanced Relations]** ficha de la actividad. Puede agregar varias relaciones con el **[!UICONTROL Add element]** botón.

   Al definir una nueva relación, seleccione el conjunto de datos entrantes que desea vincular al conjunto principal. A continuación, defina el tipo de relación. Existen varios tipos de relaciones disponibles, según los datos entrantes y el modelo de datos:

   * **[!UICONTROL 1 cardinality simple link]**:: cada registro de los datos entrantes se asocia a un registro del conjunto principal y solo a uno. Cada registro del conjunto principal tiene un registro asociado en los datos vinculados.
   * **[!UICONTROL N cardinality collection link]**:: 0, 1 o más registros (N) de los datos vinculados se pueden asociar a 1 registro del conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**:: los registros del conjunto principal pueden asociarse con un registro 0 o 1 de los datos vinculados, pero no más de uno.
   Una vez definido el **[!UICONTROL Cardinality]** , defina un **[!UICONTROL Reconciliation criteria]**. El **[!UICONTROL Source expression]** de los criterios de reconciliación puede ser un campo del recurso de destinatario, una [expresión](../../automating/using/advanced-expression-editing.md) o directamente un valor especificado entre comillas.

   Defina un **[!UICONTROL Label]** y un **[!UICONTROL ID]** que resulten fáciles de identificar más adelante en el flujo de trabajo.

   >[!NOTE]
   >
   >Solo se pueden definir relaciones entre el conjunto principal y las demás transiciones entrantes conectadas a la **[!UICONTROL Enrichment]** actividad. Para casos más sencillos con el fin de definir las relaciones con los recursos de la base de datos, utilice una actividad [Reconciliación](../../automating/using/reconciliation.md) .

1. Defina los datos adicionales desde la **[!UICONTROL Additional data]** ficha de la actividad. Puede definir datos adicionales (campos simples, agregados y colecciones) relacionados con la dimensión de segmentación del conjunto principal o basados en los vínculos creados en la **[!UICONTROL Advanced relations]** ficha de la **[!UICONTROL Enrichment]** actividad.

   Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data) .

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Los datos ahora están disponibles para su uso en las actividades conectadas después de la **[!UICONTROL Enrichment]**. Por ejemplo, puede encontrarlo en el **[!UICONTROL Additional data (targetData)]** vínculo del explorador de campos de personalización en un contenido de correo electrónico.

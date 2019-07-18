---
title: Unión
seo-title: Unión
description: Unión
seo-description: La actividad de la Unión permite reagrupar el resultado de varias actividades en un solo objetivo.
page-status-flag: no activado nunca
uuid: fafc 3 ce 9-2212-4403-8754-cfbb 28 ba 6 e 26
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 99 a 8 c 3 a 5-7 d 90-4 dbb-aa 37-1 d 0 a 84719 cf 6
context-tags: unión, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## Description {#description}

![](assets/union.png)

The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target.

>[!NOTE]
>
>Los conjuntos no necesariamente tienen que ser homogéneos.

## Context of use {#context-of-use}

The **[!UICONTROL Union]** activity is used to combine the populations from inbound transitions when performing a segmentation, defining an audience, or when preparing the message target for example.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. Conéctela a otras actividades anteriores, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**: este es el modo predeterminado. La actividad sólo conserva un elemento cuando los elementos de las distintas transiciones entrantes tienen la misma clave. Esta opción sólo se puede utilizar si las poblaciones entrantes son homogéneas.
   * **[!UICONTROL All shared columns]**: Los datos se concilian según todas las columnas en común con las transiciones entrantes. Por lo tanto, debe seleccionar el conjunto principal que se conservará en caso de duplicado. Esta opción se puede utilizar si las dimensiones de objetivo de población entrante son diferentes.
   * **[!UICONTROL A selection of columns]**: Seleccione esta opción para definir la lista de columnas en la que se aplicará la reconciliación de datos. Primero debe seleccionar el conjunto principal (que contiene los datos de origen), luego las columnas que se utilizarán para la unión.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

El siguiente ejemplo muestra el resultado de dos actividades de consulta dirigidas a reagrupar perfiles de la base de datos de Adobe Campaign que tienen entre 18 y 27 años y aquellos que tienen entre 34 y 40 años. El resultado contiene todos los perfiles de las dos consultas o el número máximo de registros, si corresponde, según se especifica durante la configuración.

![](assets/wkf_union_example.png)
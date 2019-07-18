---
title: Intersección
seo-title: Intersección
description: Intersección
seo-description: La actividad Intersección permite mantener solo los elementos comunes a las diferentes poblaciones entrantes de la actividad.
page-status-flag: no activado nunca
uuid: a 60 f 9811-0158-44 b 3-952 b -392685 c 006 cc
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 7 a 107 d 6 b-edc 3-44 c 3-bbb 7-ba 3 dec 8 e 43 f 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity.

## Context of use {#context-of-use}

The **[!UICONTROL Intersection]** activity is generally used to carry out additional filtering on populations from inbound transitions.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. Conéctela a otras actividades anteriores, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modo predeterminado. La actividad sólo conserva un elemento cuando los elementos de las distintas transiciones entrantes tienen la misma clave.
   * **[!UICONTROL All shared columns]**: Los datos se concilian según las columnas en común con las transiciones entrantes. Por lo tanto, debe seleccionar el conjunto principal que servirá como base para la comparación. Esta opción se puede utilizar si las dimensiones de objetivo de población entrante son diferentes.
   * **[!UICONTROL A selection of columns]**: Seleccione esta opción para definir la lista de columnas en la que se aplicará la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y, a continuación, especificar los campos que se utilizarán para la unión.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

El siguiente ejemplo muestra la intersección entre dos actividades de consulta. Se utiliza aquí para ver la base de datos de Adobe Campaign y recuperar perfiles que tienen entre 18 y 27 años y perfiles cuya dirección de correo electrónico se haya proporcionado respectivamente.

![](assets/wkf_intersection_example.png)


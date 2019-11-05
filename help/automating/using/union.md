---
title: Unión
description: La actividad de la Unión le permite agrupar los resultados de varias actividades en un único objetivo.
page-status-flag: nunca activado
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: unión, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Unión{#union}

## Descripción {#description}

![](assets/union.png)

La **[!UICONTROL Union]** actividad le permite agrupar el resultado de varias actividades en un único objetivo.

>[!NOTE]
>
>Los conjuntos no necesariamente tienen que ser homogéneos.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Union]** actividad se utiliza para combinar las poblaciones de las transiciones de entrada al realizar una segmentación, definir una audiencia o, por ejemplo, al preparar el destino del mensaje.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Union]** actividad en el flujo de trabajo.
1. Conéctelo a las demás actividades anteriores, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione la opción **[!UICONTROL Reconciliation type]** para definir cómo se manejan los duplicados de la confrontación entre poblaciones entrantes:

   * **[!UICONTROL Keys only]**:: este es el modo predeterminado. La actividad solo mantiene un elemento cuando los elementos de las distintas transiciones de entrada tienen la misma clave. Esta opción solo se puede utilizar si las poblaciones entrantes son homogéneas.
   * **[!UICONTROL All shared columns]**:: Los datos se concilian sobre la base de todas las columnas comunes con las transiciones de entrada. Por lo tanto, debe seleccionar el conjunto principal que se conservará en caso de que se produzca un duplicado. Esta opción se puede utilizar si las dimensiones de objetivo de población entrante son diferentes.
   * **[!UICONTROL A selection of columns]**:: seleccione esta opción para definir la lista de columnas en las que se aplicará la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y luego las columnas que se utilizarán para la combinación.

1. Marque la **[!UICONTROL Use common additional data only]** casilla si desea mantener solo los datos adicionales que están en todas las transiciones de entrada.
1. Si desea limitar el tamaño de la población final, marque la **[!UICONTROL Limit size of generated population]** casilla. El tamaño se puede especificar en el **[!UICONTROL Maximum number of records]** campo.
1. Si es necesario, administre las [transiciones](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) de la actividad para acceder a las opciones avanzadas de la población calculada.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra el resultado de dos actividades de consulta que tienen como objetivo agrupar perfiles de la base de datos de Adobe Campaign con edades comprendidas entre los 18 y los 27 años y con edades comprendidas entre los 34 y los 40 años. El resultado contiene todos los perfiles de las dos consultas o el número máximo de registros, si corresponde, según se especificó durante la configuración.

![](assets/wkf_union_example.png)
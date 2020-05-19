---
title: Unión
description: La actividad de Unión permite agrupar el resultado de varias actividades en un solo destinatario.
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---


# Unión{#union}

## Descripción {#description}

![](assets/union.png)

La **[!UICONTROL Union]** actividad le permite agrupar el resultado de varias actividades en un único destinatario.

>[!NOTE]
>
>Los conjuntos no necesariamente tienen que ser homogéneos.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Union]** actividad se utiliza para combinar las poblaciones de transiciones entrantes al realizar una segmentación, definir una audiencia o, por ejemplo, al preparar el destinatario de mensajes.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Union]** actividad en el flujo de trabajo.
1. Conéctelo a las demás actividades que le precedan, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione el **[!UICONTROL Reconciliation type]** para definir cómo se manejan los duplicados de la confrontación entre poblaciones entrantes:

   * **[!UICONTROL Keys only]**:: este es el modo predeterminado. La actividad solo mantiene un elemento cuando los elementos de las distintas transiciones entrantes tienen la misma clave. Esta opción solo se puede utilizar si las poblaciones entrantes son homogéneas.
   * **[!UICONTROL All shared columns]**:: Los datos se concilian sobre la base de todas las columnas comunes con las transiciones entrantes. Por lo tanto, debe seleccionar el conjunto principal que se mantendrá en caso de duplicado. Esta opción se puede utilizar si las dimensiones de segmentación de población entrante son diferentes.
   * **[!UICONTROL A selection of columns]**:: seleccione esta opción para definir la lista de columnas en las que se aplicará la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y luego las columnas que se utilizarán para la combinación.

1. Marque la **[!UICONTROL Use common additional data only]** casilla si desea mantener sólo los datos adicionales que están en todas las transiciones de entrada.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. El tamaño se puede especificar en el **[!UICONTROL Maximum number of records]** campo.
1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población calculada.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra el resultado de dos actividades de consulta que tienen como objetivo agrupar perfiles de la base de datos de Adobes Campaign que tienen entre 18 y 27 años y que tienen entre 34 y 40 años. El resultado contiene todos los perfiles de las dos consultas o el número máximo de registros, si corresponde, según se especificó durante la configuración.

![](assets/wkf_union_example.png)
---
title: Intersección
description: La actividad Intersección permite mantener solo los elementos comunes a las distintas poblaciones entrantes de la actividad.
page-status-flag: nunca activado
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Intersección{#intersection}

## Descripción {#description}

![](assets/intersection.png)

La **[!UICONTROL Intersection]** actividad permite mantener solo los elementos comunes a las distintas poblaciones entrantes de la actividad.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Intersection]** actividad se utiliza generalmente para realizar filtraciones adicionales en poblaciones de las transiciones de entrada.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Intersection]** actividad en el flujo de trabajo.
1. Conéctelo a las demás actividades anteriores, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione el **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**:: Modo predeterminado. La actividad solo mantiene un elemento cuando los elementos de las distintas transiciones de entrada tienen la misma clave.
   * **[!UICONTROL All shared columns]**:: Los datos se concilian sobre la base de columnas comunes con las transiciones de entrada. Por lo tanto, debe seleccionar el conjunto principal que servirá como base para la comparación. Esta opción se puede utilizar si las dimensiones de objetivo de población entrante son diferentes.
   * **[!UICONTROL A selection of columns]**:: Seleccione esta opción para definir la lista de columnas en las que se aplicará la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y luego especificar los campos que se utilizarán para la combinación.

1. Marque la **[!UICONTROL Use common additional data only]** casilla si desea mantener solo los datos adicionales que están en todas las transiciones de entrada.
1. Si es necesario, administre las [transiciones](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra la intersección entre dos actividades de consulta. Se utiliza aquí para buscar en la base de datos de Adobe Campaign y recuperar perfiles de entre 18 y 27 años de edad y perfiles cuya dirección de correo electrónico se ha proporcionado respectivamente.

![](assets/wkf_intersection_example.png)


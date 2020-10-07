---
title: Intersección
description: La actividad Intersección permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad.
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---


# Intersección{#intersection}

## Descripción {#description}

![](assets/intersection.png)

La actividad **[!UICONTROL Intersection]** permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Intersection]** se utiliza generalmente como un filtro extra para separar las poblaciones de las transiciones de entrada.

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Intersection]** en el flujo de trabajo.
1. Conéctelo a las demás actividades que le precedan, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione el **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: modo predeterminado. La actividad solo mantiene un elemento cuando los elementos de las distintas transiciones de entrada tienen la misma clave.
   * **[!UICONTROL All shared columns]**: los datos se cuadran sobre la base de columnas comunes con las transiciones de entrada. Por lo tanto, debe seleccionar el conjunto principal que debe servir como base para la comparación. Esta opción se puede utilizar si las dimensiones de segmentación de población de entrada son diferentes.
   * **[!UICONTROL A selection of columns]**: seleccione esta opción para definir la lista de columnas a las que desea aplicar la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y luego especificar los campos que se deben utilizar para la combinación.

1. Marque la casilla **[!UICONTROL Use common additional data only]** si desea mantener solo los datos adicionales que están en todas las transiciones de entrada.
1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra la intersección entre dos actividades de consulta. Se está utilizando aquí para buscar en la base de datos de Adobe Campaign y recuperar perfiles de entre 18 y 27 años y perfiles cuya dirección de correo electrónico se ha proporcionado respectivamente.

![](assets/wkf_intersection_example.png)


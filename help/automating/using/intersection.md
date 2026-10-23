---
title: Intersección
description: La actividad Intersección permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2a6a851c-df91-472b-a8a4-0b3876d51c1d
TQID: 'https://experienceleague.adobe.com/G9ptSqWfh2BTA76Ul-j2th1W2aHI-eiPvJBpcasLJXs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 98%
---
# Intersección{#intersection}

## Descripción {#description}

![](assets/intersection.png)

La actividad **[!UICONTROL Intersection]** permite mantener solo los elementos comunes a las diferentes poblaciones de entrada de la actividad.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Intersection]** se utiliza generalmente como un filtro extra para separar las poblaciones de las transiciones de entrada.

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Intersection]** en el flujo de trabajo.
1. Conéctela a las demás actividades que la precedan, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione el **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: modo predeterminado. La actividad solo mantiene un elemento cuando los elementos de las distintas transiciones de entrada tienen la misma clave.
   * **[!UICONTROL All shared columns]**: los datos se reconcilian sobre la base de columnas comunes con las transiciones de entrada. Por lo tanto, debe seleccionar el conjunto principal que debe servir como base para la comparación. Esta opción se puede utilizar si las dimensiones de segmentación de población de entrada son diferentes.
   * **[!UICONTROL A selection of columns]**: seleccione esta opción para definir la lista de columnas a las que desea aplicar la reconciliación de datos. Primero debe seleccionar el conjunto principal (el que contiene los datos de origen) y luego especificar los campos que se deben utilizar para la combinación.

1. Marque la casilla **[!UICONTROL Use common additional data only]** si desea mantener solo los datos adicionales que están en todas las transiciones de entrada.
1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra la intersección entre dos actividades de consulta. Se está utilizando aquí para buscar en la base de datos de Adobe Campaign y recuperar perfiles de entre 18 y 27 años y perfiles cuya dirección de correo electrónico se ha proporcionado respectivamente.

![](assets/wkf_intersection_example.png)

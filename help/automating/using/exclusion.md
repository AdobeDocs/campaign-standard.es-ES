---
title: Exclusión
description: La actividad Exclusión permite excluir elementos de una población según determinados criterios.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dccb9545-0d7e-4d40-9a8f-2915b4da99a7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 98%

---

# Exclusión {#exclusion}

## Descripción {#description}

![](assets/exclusion.png)

La actividad **[!UICONTROL Exclusion]** permite excluir elementos de una población según determinados criterios.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Exclusion]** se utiliza esencialmente para aplicar filtros adicionales a las poblaciones de transición de entrada.

Un conjunto principal se define entre transiciones de entrada. Los miembros de otras transiciones de entrada se excluyen del conjunto principal. La transición de salida de la actividad exclusión solo contiene los miembros del conjunto principal que no se han identificado en las demás transiciones de entrada.

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Exclusion]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione el **[!UICONTROL Primary set]** de las transiciones de entrada. Es el conjunto desde el que se excluyen los elementos. Los demás conjuntos coinciden con elementos antes de excluirse del conjunto principal.

   >[!NOTE]
   >
   >Las transiciones de entrada deben contener el mismo tipo de población. Por ejemplo, si el conjunto principal contiene perfiles de prueba, las demás transiciones también deben contener perfiles de prueba.

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra dos actividades de consulta configuradas para filtrar perfiles de la base de datos de Adobe Campaign que tienen entre 18 y 27 años y tienen una dirección de correo electrónico no válida. Los perfiles con direcciones de correo electrónico no válidas se excluyen del primer conjunto. Esto le permite enviar un correo electrónico, por ejemplo.

![](assets/wkf_exclusion_example.png)

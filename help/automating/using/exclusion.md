---
title: Exclusión
description: La actividad Exclusión permite excluir elementos de una población según determinados criterios.
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Exclusión{#exclusion}

## Descripción {#description}

![](assets/exclusion.png)

La **[!UICONTROL Exclusion]** actividad permite excluir elementos de una población según determinados criterios.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Exclusion]** actividad se utiliza esencialmente para aplicar filtros adicionales a las poblaciones de transición de entrada.

Un conjunto principal se define entre transiciones de entrada. Los miembros de otras transiciones entrantes se excluyen del conjunto principal. La transición de salida de la actividad de exclusión solo contiene los miembros del conjunto principal que no se encontraron en las demás transiciones de entrada.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Exclusion]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione la **[!UICONTROL Primary set]** de las transiciones de entrada. Es el conjunto desde el que se excluyen los elementos. Los demás conjuntos coinciden con elementos antes de excluirse del conjunto principal.

   >[!NOTE]
   >
   >Las transiciones entrantes deben contener el mismo tipo de población. Por ejemplo, si el conjunto principal contiene perfiles de prueba, las demás transiciones también deben contener perfiles de prueba.

1. Si es necesario, administre las [Transiciones](../../automating/using/activity-properties.md) de la actividad para acceder a las opciones avanzadas de la población saliente.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra dos actividades de consulta configuradas para filtrar perfiles de la base de datos de Adobe Campaign que tienen entre 18 y 27 años y tienen una dirección de correo electrónico no válida. Los perfiles con direcciones de correo electrónico no válidas se excluyen del primer conjunto. Esto le permite enviar un correo electrónico, por ejemplo.

![](assets/wkf_exclusion_example.png)


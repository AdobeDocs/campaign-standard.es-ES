---
title: Exclusión
seo-title: Exclusión
description: Exclusión
seo-description: La actividad de exclusión permite excluir elementos de una población según determinados criterios.
page-status-flag: no activado nunca
uuid: b 79 e 7 f 73-37 a 0-4 ec 3-ac 5 a -5449 dc 1 b 1 f 22
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: d 5312 fcd -43 ad -428 e-bde 9-90 f 062 e 9358 c
context-tags: exclusión, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria.

## Context of use {#context-of-use}

The **[!UICONTROL Exclusion]** activity is used essentially to carry out additional filtering on inbound transition populations.

Se define un conjunto principal entre las transiciones entrantes. Los miembros de otras transiciones entrantes se excluyen del conjunto principal. La transición saliente de la actividad de exclusión sólo contiene los miembros del conjunto primario que no se encontraban en las otras transiciones entrantes.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. Es el conjunto desde el cual se excluyen los elementos. Los demás conjuntos coinciden con elementos antes de excluirlos del conjunto principal.

   >[!NOTE]
   >
   >Las transiciones de entrada deben contener el mismo tipo de población. Por ejemplo, si el conjunto principal contiene perfiles de prueba, las otras transiciones deben contener también perfiles de prueba.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

El siguiente ejemplo muestra dos actividades de consulta configuradas para filtrar perfiles de la base de datos de Adobe Campaign que tienen entre 18 y 27 años y tienen una dirección de correo electrónico no válida. Los perfiles con direcciones de correo electrónico no válidas se excluyen del primer conjunto. Esto le permite enviar un correo electrónico por ejemplo.

![](assets/wkf_exclusion_example.png)


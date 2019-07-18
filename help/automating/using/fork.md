---
title: Fork
seo-title: Fork
description: Fork
seo-description: La actividad de Fork permite crear transiciones salientes para iniciar varias actividades al mismo tiempo.
page-status-flag: no activado nunca
uuid: e 4 eaf 69 b -84 ee -4 f 79-8 b 80-99284697 cd 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: f 8 ffe 7 af-e 18 c -4599-8 fd 0-fcd 192565323
context-tags: ramificación, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## Description {#description}

![](assets/fork.png)

The **[!UICONTROL Fork]** activity allows you to create outbound transitions to start several activities at the same time.

## Context of use {#context-of-use}

The **[!UICONTROL Fork]** activity allows you to carry out several different activities independently within the same workflow.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. Conéctela a otras actividades anteriores, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Especifique el número de transiciones salientes creándolas, eliminándolas o duplicándolas. También puede atribuir un nombre y una etiqueta a ellos.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

En el siguiente ejemplo se muestra una intersección de dos actividades de consulta que dirigen perfiles de la base de datos de Adobe Campaign, en este caso mujeres que viven en París. Por lo tanto, la actividad de ramificación permite utilizar varias actividades al mismo tiempo: uno que guarda la audiencia para recordar la población calculada y otra que segmenta a la población para que envíe dos correos electrónicos distintos con un contenido objetivo para cada segmento. El primer correo electrónico se envía a mujeres parisian que tienen edades comprendidas entre 18 y 40 y otro dirigido a mujeres parisian envejecidas mayores de 40 años.

![](assets/wkf_fork_example.png)


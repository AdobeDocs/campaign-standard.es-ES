---
title: Fork
description: La actividad Fork le permite crear transiciones de salida para iniciar varias actividades al mismo tiempo.
page-status-flag: nunca activado
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: horquilla,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Fork{#fork}

## Descripción {#description}

![](assets/fork.png)

La **[!UICONTROL Fork]** actividad permite crear transiciones de salida para iniciar varias actividades al mismo tiempo.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Fork]** actividad le permite llevar a cabo varias actividades diferentes de forma independiente dentro del mismo flujo de trabajo.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Fork]** actividad en el flujo de trabajo.
1. Conéctelo a las demás actividades anteriores, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Especifique el número de transiciones de salida creándolas, eliminándolas o duplicándolas. También puede atribuirles un nombre y una etiqueta.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo muestra una intersección de dos actividades de consulta que segmentan perfiles de la base de datos de Adobe Campaign. En este caso, las mujeres que viven en París. Por lo tanto, la actividad de la horquilla le permite utilizar varias actividades al mismo tiempo: una que guarda a la audiencia para que recuerde la población calculada y otra que segmenta la población para que envíe dos correos electrónicos diferentes con un contenido de objetivo para cada segmento. El primer correo electrónico se envía a mujeres parisinas de entre 18 y 40 años y a otras mujeres parisinas de más de 40 años.

![](assets/wkf_fork_example.png)


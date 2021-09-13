---
title: Bifurcación (Fork)
description: La actividad Bifurcación permite crear transiciones de salida para el inicio de varias actividades al mismo tiempo.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 100%

---

# Bifurcación{#fork}

## Descripción {#description}

![](assets/fork.png)

La actividad **[!UICONTROL Fork]** permite crear transiciones salientes para el inicio de varias actividades al mismo tiempo.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Fork]** le permite llevar a cabo varias actividades diferentes de forma independiente dentro del mismo flujo de trabajo.

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Fork]** en su flujo de trabajo.
1. Conéctela a las demás actividades que la precedan, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Especifique el número de transiciones de salida creándolas, eliminándolas o duplicándolas. También puede atribuirles un nombre y una etiqueta.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

En el siguiente ejemplo se muestra una intersección de dos actividades de consulta que identifica perfiles de la base de datos de Adobe Campaign, en este caso mujeres que viven en París. La actividad Bifurcación permite utilizar varias actividades al mismo tiempo: una que guarda la audiencia para recordar la población calculada y otra que segmenta la población para enviar dos correos electrónicos diferentes con un contenido de objetivo para cada segmento. El primer correo electrónico se envía a mujeres parisinas de entre 18 y 40 años y otro, a mujeres parisinas de más de 40 años.

![](assets/wkf_fork_example.png)

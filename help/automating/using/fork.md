---
title: Bifurcación (Fork)
description: La actividad Bifurcación permite crear transiciones de salida para el inicio de varias actividades al mismo tiempo.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 98%

---

# Bifurcación (Fork){#fork}

## Descripción {#description}

![](assets/fork.png)

La actividad **[!UICONTROL Fork]** permite crear transiciones salientes para el inicio de varias actividades al mismo tiempo.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Fork]** le permite llevar a cabo varias actividades diferentes de forma independiente dentro del mismo flujo de trabajo.

## Configuración {#configuration}

1. Arrastre y suelte una actividad de **[!UICONTROL Fork]** en el flujo de trabajo.
1. Conéctela a las demás actividades que la precedan, como consultas.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Especifique el número de transiciones de salida creándolas, eliminándolas o duplicándolas. También puede atribuirles un nombre y una etiqueta.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

En el siguiente ejemplo se muestra una intersección de dos actividades de consulta que identifica perfiles de la base de datos de Adobe Campaign, en este caso mujeres que viven en París. La actividad Bifurcación permite utilizar varias actividades al mismo tiempo: una que guarda el público para recordar la población calculada y otra que segmenta la población para enviar dos correos electrónicos diferentes con un contenido de objetivo para cada segmento. El primer correo electrónico se envía a mujeres parisinas de entre 18 y 40 años y otro, a mujeres parisinas de más de 40 años.

![](assets/wkf_fork_example.png)

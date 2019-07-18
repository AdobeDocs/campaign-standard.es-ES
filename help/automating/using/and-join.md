---
title: AND-join
seo-title: AND-join
description: AND-join
seo-description: La actividad Y-join permite sincronizar varias ramas de ejecución de un flujo de trabajo.
page-status-flag: no activado nunca
uuid: 9 b 54 fd 4 c -9915-400 f-a 494-74 e 52 c 329 b 8 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 4 b 55 efa 2-652 e -4493-bfa 7-eaee 59 b 383 ca
context-tags: unjoin, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## Description {#description}

![](assets/and_join.png)

The **[!UICONTROL AND-join]** activity allows you to synchronize multiple execution branches of a workflow.

## Context of use {#context-of-use}

**[!UICONTROL AND-join]** La actividad sólo activa la transición saliente una vez activadas todas las transiciones de entrada, es decir, una vez que todas las actividades anteriores han finalizado.

## Configuration {#configuration}

1. Coloque varias actividades como consultas en el flujo de trabajo para formar al menos dos ramas de ejecución diferentes.
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. Conéctela después de las dos ramas diferentes que desee sincronizar.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Seleccione el conjunto principal que se debe conservar en la transición saliente. Si no selecciona ningún conjunto, se enviará una población aleatoria desde la actividad.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)


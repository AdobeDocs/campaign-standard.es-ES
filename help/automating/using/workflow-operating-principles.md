---
title: Principios operativos del flujo de trabajo
seo-title: Principios operativos del flujo de trabajo
description: Principios operativos del flujo de trabajo
seo-description: Conozca los principales aspectos de los flujos de trabajo.
page-status-flag: no activado nunca
uuid: 85755 e 85-617 b -4 a 9 b-bb 30-96 ba 8333 f 4 f 0 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: acerca de los flujos de trabajo y gestión de datos
discoiquuid: 3 a 13785 d -1 ef 7-4043-9927-2 d 495 b 83709 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. Cada actividad tiene una función específica en el proceso. The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

El tipo de datos intercambiados entre una actividad y otro puede afectar a la configuración de las siguientes actividades. Por ejemplo, si una población se establece antes de la actividad de entrega de correo electrónico, puede servir como objetivo para el correo electrónico en cuestión.

Puede abrir actividades para comprobar o editar parámetros antes o después de ejecutar el flujo de trabajo.

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)


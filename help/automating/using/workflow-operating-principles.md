---
title: Principios operativos del flujo de trabajo
description: Conozca los principales aspectos de los flujos de trabajo.
page-status-flag: nunca activado
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: acerca de los flujos de trabajo y la administración de datos
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Principios operativos del flujo de trabajo{#workflow-operating-principles}

Un flujo de trabajo es una **secuencia de actividades** configurables. Cada actividad tiene una función específica en el proceso. El resultado de cada actividad se reenvía a la siguiente actividad mediante una **transición**, representada por una flecha.

El tipo de datos intercambiados entre una actividad y otra puede afectar a la configuración de las siguientes actividades. Por ejemplo, si se establece una población antes de la actividad de envío de correo electrónico, puede servir como objetivo para el correo electrónico en cuestión.

Puede abrir actividades para comprobar o editar parámetros antes o después de ejecutar el flujo de trabajo.

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Para acceder a la vista de detalles de las transiciones, debe comprobar la **[!UICONTROL Keep interim results]** opción en la **[!UICONTROL Execution]** sección de las propiedades del flujo de trabajo.

![](assets/workflow_overview.png)


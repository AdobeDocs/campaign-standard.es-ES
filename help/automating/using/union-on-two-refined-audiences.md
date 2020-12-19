---
solution: Campaign Standard
product: campaign
title: Unión de dos audiencias refinadas
description: Este caso de uso muestra la unión de dos actividades de audiencia de lectura.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# Unión de dos audiencias refinadas {#example--union-on-two-refined-audiences}

El flujo de trabajo definido en este ejemplo muestra la unión de dos actividades de **[!UICONTROL Read audience]**. El objetivo de este flujo de trabajo es enviar un correo electrónico a los socios oro o plata que tengan entre 18 y 30 años. Ya se han creado audiencias específicas en el sistema para realizar un seguimiento de los miembros oro y plata.

El flujo de trabajo está diseñado de la siguiente manera:

![](assets/readaudience_activity_example1.png)

* Una primera actividad [Leer audiencia](../../automating/using/read-audience.md) que recupera la audiencia de miembros Gold y la perfecciona seleccionando sólo perfiles con edades comprendidas entre 18 y 30 años.
* Una segunda actividad de **[!UICONTROL Read audience]** que recupera la audiencia de miembros plata y la perfecciona seleccionando solo perfiles de entre 18 y 30 años de edad.
* Una actividad [de Unión](../../automating/using/union.md) que une poblaciones de ambas actividades **[!UICONTROL Read audiences]** en una población final.
* Una actividad [envío de correo electrónico](../../automating/using/email-delivery.md) que envía el correo electrónico a la población que proviene de la actividad **[!UICONTROL Union]**.

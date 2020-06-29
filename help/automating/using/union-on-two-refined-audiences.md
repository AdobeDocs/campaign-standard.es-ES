---
title: Unión en dos audiencias refinadas
description: Este caso de uso muestra la unión de dos actividades de audiencia de lectura.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# Unión en dos audiencias refinadas {#example--union-on-two-refined-audiences}

El flujo de trabajo definido en este ejemplo muestra la unión de dos **[!UICONTROL Read audience]** actividades. El objetivo de este flujo de trabajo es enviar un correo electrónico a los socios Gold o Silver que tengan entre 18 y 30 años. Ya se han creado audiencias específicas en el sistema para realizar un seguimiento de los miembros Gold y Silver.

El flujo de trabajo está diseñado de la siguiente manera:

![](assets/readaudience_activity_example1.png)

* Una primera actividad de audiencia [de](../../automating/using/read-audience.md) lectura que recupera la audiencia de miembros Gold y la perfecciona seleccionando solo perfiles con edades comprendidas entre 18 y 30 años.
* Una segunda **[!UICONTROL Read audience]** actividad que recupera la audiencia de miembros Silver y la perfecciona seleccionando sólo perfiles de entre 18 y 30 años de edad.
* Una actividad de [Unión](../../automating/using/union.md) que une poblaciones de ambas **[!UICONTROL Read audiences]** actividades en una población final.
* actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico que envía el correo electrónico a la población que proviene de la **[!UICONTROL Union]** actividad.

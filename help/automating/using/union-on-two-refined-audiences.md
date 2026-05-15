---
title: Unión de dos públicos refinados
description: Este caso de uso muestra la unión de dos actividades Read audience.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
TQID: https://experienceleague.adobe.com/NZA7DqSxrgPvNPfo4dgWvyJaOp-2Ma07MZJuHff3sAA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 43%

---

# Unión de dos públicos refinados {#example--union-on-two-refined-audiences}

El flujo de trabajo definido en este ejemplo muestra la unión de dos actividades de **[!UICONTROL Read audience]**. El objetivo de este flujo de trabajo es enviar un correo electrónico a los socios oro o plata que tengan entre 18 y 30 años. Ya se han creado públicos específicos en el sistema para realizar un seguimiento de los miembros oro y plata.

El flujo de trabajo está diseñado de la siguiente manera:

![](assets/readaudience_activity_example1.png)

* Una primera actividad [Leer audiencia](../../automating/using/read-audience.md) que recupera la audiencia de miembros oro y la perfecciona seleccionando solo perfiles con edades comprendidas entre 18 y 30 años.
* Una segunda actividad de **[!UICONTROL Read audience]** que recupera el público de miembros plata y lo perfecciona seleccionando solo perfiles de entre 18 y 30 años de edad.
* Una actividad [Union](../../automating/using/union.md) que une poblaciones de ambas actividades **[!UICONTROL Read audiences]** en una población final.
* Una actividad [Email delivery](../../automating/using/email-delivery.md) que envía el correo electrónico a la población proveniente de la actividad **[!UICONTROL Union]**.

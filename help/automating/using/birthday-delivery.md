---
title: Envío de cumpleaños
description: Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Envío de cumpleaños {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.

Para generar el flujo de trabajo, siga estos pasos:

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. El cálculo del cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El envío [de](../../automating/using/email-delivery.md) correo electrónico se repite. Los envíos se acumulan por mes. Así que todos los correos electrónicos enviados en un mes se acumulan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas **ejecuciones recurrentes**) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

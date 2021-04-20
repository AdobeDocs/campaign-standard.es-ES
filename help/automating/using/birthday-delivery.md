---
solution: Campaign Standard
product: campaign
title: Envío de cumpleaños
description: Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 68%

---


# Envío de cumpleaños {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.

Para crear el flujo de trabajo, siga estos pasos:

* El [Scheduler](../../automating/using/scheduler.md) le permite iniciar el flujo de trabajo todos los días a las 8 a. m.

   ![](assets/wkf_delivery_example_2.png)

* La actividad [Query](../../automating/using/query.md) permite calcular los perfiles que han proporcionado un correo electrónico y cuyo cumpleaños es el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo del cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El [Email delivery](../../automating/using/email-delivery.md) es recurrente. Los envíos se acumulan por mes. Así que todos los correos electrónicos enviados en un mes se acumulan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas **ejecuciones recurrentes**) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

---
title: Envío de cumpleaños
description: Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 52%

---

# Envío de cumpleaños {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.

Para crear el flujo de trabajo, siga estos pasos:

* El [Planificador](../../automating/using/scheduler.md) le permite iniciar el flujo de trabajo todos los días a las 8 a. m.

  ![](assets/wkf_delivery_example_2.png)

* La actividad [Consulta](../../automating/using/query.md) le permite calcular los perfiles que han proporcionado un correo electrónico y cuyo cumpleaños es el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo del cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

  ![](assets/wkf_delivery_example_3.png)

* La [entrega de correo electrónico](../../automating/using/email-delivery.md) es recurrente. Los envíos se acumulan por mes. Así que todos los correos electrónicos enviados en un mes se acumulan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas **ejecuciones recurrentes**) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

  ![](assets/wkf_delivery_example_4.png)

---
solution: Campaign Standard
product: campaign
title: Envío de cumpleaños
description: Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Envío de cumpleaños {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.

Para generar el flujo de trabajo, siga estos pasos:

* El [Planificador](../../automating/using/scheduler.md) le permite realizar inicios en el flujo de trabajo todos los días a las 8 de la mañana.

   ![](assets/wkf_delivery_example_2.png)

* La actividad [Consulta](../../automating/using/query.md) permite calcular los perfiles que han proporcionado un correo electrónico y cuya fecha de nacimiento es el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo del cumpleaños se realiza mediante un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El [envío de correo electrónico](../../automating/using/email-delivery.md) es recurrente. Los envíos se acumulan por mes. Así que todos los correos electrónicos enviados en un mes se acumulan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas **ejecuciones recurrentes**) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

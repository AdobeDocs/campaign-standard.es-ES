---
title: envío de cumpleaños
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# envío de cumpleaños {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este ejemplo es un flujo de trabajo de cumpleaños. Cada día se envía un correo electrónico a los perfiles cuyo cumpleaños es ese día.

Para generar el flujo de trabajo, siga estos pasos:

* El [Planificador](../../automating/using/scheduler.md) le permite realizar inicios del flujo de trabajo todos los días a las 8:00 de la mañana.

   ![](assets/wkf_delivery_example_2.png)

* La actividad de [Consulta](../../automating/using/query.md) le permite calcular los perfiles que han proporcionado un correo electrónico y de quién es el cumpleaños en el día actual, cada vez que se ejecuta el flujo de trabajo. El cálculo de cumpleaños se realiza con un filtro predefinido disponible en la paleta de la herramienta de edición de consultas.

   ![](assets/wkf_delivery_example_3.png)

* El envío [de](../../automating/using/email-delivery.md) correo electrónico se repite. Los envíos se agregan por mes. Por lo tanto, todos los correos electrónicos enviados en un mes se agregan en una sola vista. En un año se ejecutan 365 envíos, pero se reagrupan en 12 vistas (también llamadas ejecuciones **** recurrentes) en la interfaz de Adobe Campaign. Los detalles del historial y del informe se muestran cada mes y no para cada envío.

   ![](assets/wkf_delivery_example_4.png)

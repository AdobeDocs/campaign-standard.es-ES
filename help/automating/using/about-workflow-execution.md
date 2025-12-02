---
title: Acerca de la ejecución del flujo de trabajo
description: Más información sobre la ejecución del flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 10%

---

# Acerca de la ejecución del flujo de trabajo {#about-workflow-execution}

Un flujo de trabajo siempre se inicia manualmente. Sin embargo, una vez iniciada, puede permanecer inactiva, según la información especificada en una actividad [Scheduler](../../automating/using/scheduler.md).

>[!IMPORTANT]
>
> Adobe recomienda a los clientes que no ejecuten más de 20 ejecuciones de flujos de trabajo activos simultáneamente, y que prioricen y extiendan la ejecución del flujo de trabajo a lo largo del tiempo. Para obtener más información, consulte las prácticas recomendadas que se proporcionan en [esta página](../../automating/using/best-practices-workflows.md).

Las acciones relacionadas con la ejecución (inicio, detención, pausa, etc.) son **procesos asincrónicos**: el comando se guarda y se aplicará una vez que el servidor esté disponible para su aplicación.

En un flujo de trabajo, el resultado de cada actividad se envía generalmente a la siguiente actividad a través de una transición, representada por una flecha.

Una transición no finaliza si no está vinculada a una actividad de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Se puede ejecutar igualmente un flujo de trabajo que contenga transiciones no finalizadas: se genera un mensaje de advertencia y el flujo de trabajo se pausa una vez que llega a la transición, pero esto no genera un error. También puede iniciar un flujo de trabajo sin haber terminado completamente el diseño y puede completarlo a medida que avanza.

Una vez ejecutada una actividad, encima de ella se muestra el número de registros enviados en la transición.

![](assets/wkf_transition_count.png)

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Puede ver los datos y la estructura de datos.

De forma predeterminada, solo se puede acceder a los detalles de la última transición del flujo de trabajo. Para poder acceder a los resultados de las actividades anteriores, debe comprobar la opción **[!UICONTROL Keep interim results]** en la sección **[!UICONTROL Execution]** de las propiedades del flujo de trabajo antes de iniciar el flujo de trabajo.

>[!NOTE]
>
>Esta opción consume mucha memoria y está diseñada para ayudar a construir un flujo de trabajo y garantizar que esté correctamente configurado y se comporte correctamente. Deje sin marcar las instancias de producción.

Cuando una transición está abierta, puede editar su **[!UICONTROL Label]** o enlazarle un **[!UICONTROL Segment code]**. Para ello, edite los campos correspondientes y confirme las modificaciones.

Con las API de REST de Campaign Standard, puede **iniciar**, **pausar**, **reanudar** y **detener** un flujo de trabajo. Puede encontrar más detalles y ejemplos de llamadas REST en la [documentación de API.](../../api/using/controlling-a-workflow.md)

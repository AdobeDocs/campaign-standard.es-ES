---
title: Acerca de la ejecución del flujo de trabajo
description: Obtenga más información sobre la ejecución del flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 9%

---

# Acerca de la ejecución del flujo de trabajo {#about-workflow-execution}

Un flujo de trabajo siempre se inicia manualmente. Sin embargo, una vez iniciada, puede permanecer inactiva, según la información especificada en una actividad [Scheduler](../../automating/using/scheduler.md).

>[!CAUTION]
>
> Adobe recomienda a los clientes priorizar las ejecuciones de flujos de trabajo y ejecutar hasta veinte ejecuciones de flujos de trabajo simultáneos para lograr de forma coherente el máximo rendimiento en toda la instancia. Se pueden planificar más de veinte ejecuciones de flujo de trabajo simultáneas y se ejecutarán secuencialmente de forma predeterminada. Puede ajustar la configuración predeterminada para el número máximo de ejecuciones de flujo de trabajo simultáneas enviando un ticket al Servicio de atención al cliente.

Acciones relacionadas con la ejecución (inicio, detención, pausa, etc.) son procesos **asíncronos**: el comando se guarda y se hace efectivo una vez que el servidor esté disponible para aplicarlo.

En un flujo de trabajo, el resultado de cada actividad se envía generalmente a la siguiente actividad a través de una transición, representada por una flecha.

Una transición no termina si no está vinculada a una actividad de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Se puede ejecutar igualmente un flujo de trabajo que contenga transiciones no finalizadas: se generará un mensaje de advertencia y el flujo de trabajo se pausará una vez que llegue a la transición, pero esto no generará un error. También puede iniciar un flujo de trabajo sin haber finalizado completamente el diseño y completarlo a medida que avanza.

Una vez ejecutada una actividad, el número de registros enviados en la transición se muestra encima de ella.

![](assets/wkf_transition_count.png)

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Puede ver los datos y la estructura de datos.

De forma predeterminada, solo se puede acceder a los detalles de la última transición del flujo de trabajo. Para poder acceder a los resultados de las actividades anteriores, debe marcar la opción **[!UICONTROL Keep interim results]** en la sección **[!UICONTROL Execution]** de las propiedades del flujo de trabajo antes de iniciar el flujo de trabajo.

>[!NOTE]
>
>Esta opción consume mucha memoria y está diseñada para ayudar a construir un flujo de trabajo y garantizar que esté correctamente configurado y se comporte. Deje sin marcar las instancias de producción.

Cuando una transición está abierta, puede editarla **[!UICONTROL Label]** o vincularla a **[!UICONTROL Segment code]**. Para ello, edite los campos correspondientes y confirme las modificaciones.

Mediante las API de REST del Campaign Standard, puede **iniciar**, **pausar**, **reanudar** y **detener** un flujo de trabajo. Puede encontrar más detalles y ejemplos de llamadas REST en la documentación de API [.](../../api/using/controlling-a-workflow.md)

---
title: Acerca de la ejecución del flujo de trabajo
description: Obtenga más información sobre la ejecución del flujo de trabajo.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 9%

---


# Acerca de la ejecución del flujo de trabajo {#about-workflow-execution}

Un flujo de trabajo siempre se inicia manualmente. Sin embargo, una vez iniciada, puede permanecer inactiva, según la información especificada en una actividad de [Planificador](../../automating/using/scheduler.md) .

>[!CAUTION]
>
> Adobe recomienda que los clientes den prioridad a las ejecuciones de flujos de trabajo y ejecuten hasta veinte ejecuciones de flujos de trabajo concurrentes para lograr de forma consistente el máximo rendimiento en toda la instancia. Se pueden planificar más de veinte ejecuciones de flujo de trabajo simultáneas que se ejecutarán secuencialmente de forma predeterminada. Puede ajustar la configuración predeterminada para el número máximo de ejecuciones de flujo de trabajo simultáneas enviando un ticket al Servicio de atención al cliente.

Acciones relacionadas con la ejecución (inicio, parada, pausa, etc.) son procesos **asincrónicos** : el comando se guarda y se hará efectivo cuando el servidor esté disponible para aplicarlo.

En un flujo de trabajo, el resultado de cada actividad generalmente se envía a la siguiente actividad mediante una transición, representada por una flecha.

Una transición no termina si no está vinculada a una actividad de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Se puede seguir ejecutando un flujo de trabajo que contenga transiciones sin terminar: se generará un mensaje de advertencia y el flujo de trabajo se pausará una vez que llegue a la transición, pero esto no generará un error. También puede realizar el inicio de un flujo de trabajo sin haber terminado completamente el diseño y puede completarlo a medida que avanza.

Una vez ejecutada una actividad, el número de registros enviados en la transición se muestra encima.

![](assets/wkf_transition_count.png)

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Puede vista de los datos y la estructura de datos.

De forma predeterminada, solo se puede acceder a los detalles de la última transición del flujo de trabajo. Para poder acceder a los resultados de las actividades anteriores, debe comprobar la **[!UICONTROL Keep interim results]** opción de la **[!UICONTROL Execution]** sección de las propiedades del flujo de trabajo antes de iniciar el flujo de trabajo.

>[!NOTE]
>
>Esta opción consume mucha memoria y está diseñada para ayudar a construir un flujo de trabajo y garantizar que esté correctamente configurado y se comporte. Deje sin marcar las instancias de producción.

Cuando una transición está abierta, puede editarla **[!UICONTROL Label]** o vincularla **[!UICONTROL Segment code]** . Para ello, edite los campos correspondientes y confirme las modificaciones.

Mediante las API de Campaign Standard REST, puede **realizar inicios**, **pausar**, **reanudar** y **detener** un flujo de trabajo. Puede encontrar más detalles y ejemplos de llamadas REST en la documentación de la [API.](../../api/using/controlling-a-workflow.md)

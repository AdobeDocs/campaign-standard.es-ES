---
title: Envío de una notificación push recurrente con un flujo de trabajo
description: En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 h a los suscriptores de la aplicación móvil según sus husos horarios.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# Envío de una notificación push recurrente con un flujo de trabajo {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 h a los suscriptores de la aplicación móvil según sus husos horarios.

Para crear el flujo de trabajo, siga estos pasos:

1. La actividad [Scheduler](../../automating/using/scheduler.md) le permite iniciar el flujo de trabajo días antes del inicio del envío para poder enviar la notificación a todos los suscriptores a las 20:00 en un huso horario determinado:

   * En el campo **[!UICONTROL Execution frequency]**, seleccione Mensual.
   * Seleccione las 8 pm en el campo **[!UICONTROL Time]**.
   * Elija el día en que se enviará la entrega cada mes.
   * Seleccione una fecha de inicio para el flujo de trabajo, al menos un día antes del inicio de la entrega. De lo contrario, algunos destinatarios podrían recibir el mensaje un día después si la hora seleccionada ya ha pasado en sus husos horarios.
   * En la pestaña **[!UICONTROL Execution options]** , seleccione el huso horario en el que comenzará el flujo de trabajo en el campo **[!UICONTROL Time zone]**. Aquí, por ejemplo, el flujo de trabajo comienza a las 20:00 h, hora del Pacífico, una semana antes del primer día del mes para permitir que se creen envíos para todas las zonas horarias aplicables.

   >[!NOTE]
   >
   >De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. La actividad [Query](../../automating/using/query.md) le permite dirigirse a sus clientes VIP de entre 20 y 30 años, que se han suscrito a su aplicación móvil y que no han abierto el correo electrónico enviado:

   * Seleccione una audiencia (sus clientes VIP) y filtre según su edad.
   * Arrastre y suelte el elemento **Subscriptions to an application** en el espacio de trabajo. Seleccione **Exists** y seleccione la aplicación móvil que desee utilizar.
   * Seleccione el correo electrónico que envió a sus clientes.
   * Arrastre y suelte el elemento **Delivery logs (logs)** en el espacio de trabajo y seleccione **Exists** para dirigirse a todos los clientes que recibieron el correo electrónico.
   * Arrastre y suelte el elemento **Tracking logs (tracking)** en el espacio de trabajo y seleccione **Does not exist** para dirigirse a todos los clientes que no hayan abierto el correo electrónico.

      ![](assets/wkf_push_example_2.png)

1. La actividad [Push notification delivery](../../automating/using/push-notification-delivery.md) permite introducir el contenido del mensaje y seleccionar los campos de personalización que desea utilizar:

   * Seleccione la opción **[!UICONTROL Recurring notification]**.
   * Defina el contenido de la notificación push. Para obtener más información sobre el contenido de las notificaciones push, consulte esta [sección](../../channels/using/preparing-and-sending-a-push-notification.md).
   * En el bloque **[!UICONTROL Schedule]** , seleccione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aquí, elegimos el **[!UICONTROL Time zone of the contact date]** Pacífico como en el flujo de trabajo **[!UICONTROL Scheduler]**.
   * En el campo **[!UICONTROL Optimize the sending time per recipient]**, seleccione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Haga clic en el botón **[!UICONTROL Start]** para iniciar el flujo de trabajo recurrente.

   ![](assets/wkf_push_example_3.png)

El flujo de trabajo se está ejecutando. Comenzará en la fecha de inicio elegida del **[!UICONTROL Scheduler]** a las 20:00, hora del Pacífico, la notificación push recurrente se enviará todos los primeros días del mes a las 20:00, según la zona horaria del cliente.

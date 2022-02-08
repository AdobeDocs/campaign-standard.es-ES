---
title: Envío de una notificación push recurrente con un flujo de trabajo
description: En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 h a los suscriptores de la aplicación móvil en función de sus zonas horarias
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# Envío de una notificación push recurrente con un flujo de trabajo {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 h a los suscriptores de la aplicación móvil según sus husos horarios.

Para crear el flujo de trabajo, siga estos pasos:

1. La variable [Planificador](../../automating/using/scheduler.md) actividad le permite iniciar el flujo de trabajo días antes del inicio de la entrega para poder enviar la notificación a cada suscriptor a las 20:00 en un huso horario determinado:

   * En el **[!UICONTROL Execution frequency]** , seleccione Mensual.
   * Seleccione las 8 pm en la **[!UICONTROL Time]** campo .
   * Elija el día en que se enviará la entrega cada mes.
   * Seleccione una fecha de inicio para el flujo de trabajo, al menos un día antes del inicio de la entrega. De lo contrario, algunos destinatarios podrían recibir el mensaje un día después si la hora seleccionada ya ha pasado en sus husos horarios.
   * En el **[!UICONTROL Execution options]** , seleccione la zona horaria en la que comenzará el flujo de trabajo **[!UICONTROL Time zone]** campo . Aquí, por ejemplo, el flujo de trabajo comienza a las 20:00 h, hora del Pacífico, una semana antes del primer día del mes para permitir que se creen envíos para todas las zonas horarias aplicables.

   >[!NOTE]
   >
   >De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. La variable [Consulta](../../automating/using/query.md) actividad le permite dirigirse a sus clientes de VIP de entre 20 y 30 años, que se han suscrito a su aplicación móvil y que no han abierto el correo electrónico enviado:

   * Seleccione una audiencia (sus clientes VIP) y filtre según su edad.
   * Arrastre y suelte la **Suscripciones a una aplicación** en el espacio de trabajo. Select **Existe** y seleccione la aplicación móvil que desee utilizar.
   * Seleccione el correo electrónico que envió a sus clientes.
   * Arrastre y suelte la **Registros de envío (registros)** en el espacio de trabajo y seleccione **Existe** para dirigirse a todos los clientes que recibieron el correo electrónico.
   * Arrastre y suelte la **Registros de seguimiento (seguimiento)** en el espacio de trabajo y seleccione **No existe** para dirigirse a todos los clientes que no hayan abierto el correo electrónico.

      ![](assets/wkf_push_example_2.png)

1. La variable [Envío de notificaciones push](../../automating/using/push-notification-delivery.md) actividad le permite introducir el contenido del mensaje y seleccionar los campos de personalización que desee utilizar:

   * Seleccione la opción **[!UICONTROL Recurring notification]**.
   * Defina el contenido de la notificación push. Para obtener más información sobre el contenido de las notificaciones push, consulte esta [sección](../../channels/using/preparing-and-sending-a-push-notification.md).
   * En el **[!UICONTROL Schedule]** bloquear, seleccionar **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aquí, elegimos el **[!UICONTROL Time zone of the contact date]** Pacific como en el flujo de trabajo **[!UICONTROL Scheduler]**.
   * En el campo **[!UICONTROL Optimize the sending time per recipient]**, seleccione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Haga clic en el **[!UICONTROL Start]** para iniciar el flujo de trabajo recurrente.

   ![](assets/wkf_push_example_3.png)

El flujo de trabajo se está ejecutando. Comenzará en la fecha de inicio elegida del **[!UICONTROL Scheduler]** a las 20:00, hora del Pacífico, la notificación push recurrente se envía todos los primeros días del mes a las 20:00, según la zona horaria del cliente.

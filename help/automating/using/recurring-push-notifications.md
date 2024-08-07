---
title: Envío de una notificación push recurrente con un flujo de trabajo
description: En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 a los suscriptores de la aplicación móvil en función de sus husos horarios
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 5%

---

# Envío de una notificación push recurrente con un flujo de trabajo {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20:00 a los suscriptores de la aplicación móvil, según sus husos horarios.

Para crear el flujo de trabajo, siga estos pasos:

1. La actividad [Scheduler](../../automating/using/scheduler.md) le permite iniciar el flujo de trabajo días antes del inicio de la entrega para poder enviar la notificación a todos los suscriptores a las 8 p. m. en cualquier zona horaria determinada:

   * En el campo **[!UICONTROL Execution frequency]**, seleccione Mensualmente.
   * Seleccione las 8 pm en el campo **[!UICONTROL Time]**.
   * Elija el día en el que se enviará la entrega todos los meses.
   * Seleccione una fecha de inicio para el flujo de trabajo, al menos un día antes del inicio de la entrega. De lo contrario, es posible que algunos destinatarios reciban el mensaje un día después si la hora seleccionada ya ha pasado en sus zonas horarias.
   * En la ficha **[!UICONTROL Execution options]**, seleccione el huso horario en el que comenzará el flujo de trabajo en el campo **[!UICONTROL Time zone]**. En este caso, por ejemplo, el flujo de trabajo se inicia a las 20:00, hora del Pacífico, una semana antes del primer día del mes para permitir que se cree un tiempo para las entregas para todos los husos horarios aplicables.

   >[!NOTE]
   >
   >De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. VIP La actividad [Consulta](../../automating/using/query.md) le permite dirigirse a sus clientes de entre 20 y 30 años de edad que se hayan suscrito a su aplicación móvil y que no hayan abierto el correo electrónico que ha enviado:

   * VIP Seleccione una audiencia (sus clientes de) y filtre por edad.
   * Arrastre y suelte el elemento **Subscriptions to an application** en el área de trabajo. Seleccione **Existe** y la aplicación móvil que desea utilizar.
   * Seleccione el correo electrónico que envió a sus clientes.
   * Arrastre y suelte el elemento **Registros de envío (registros)** en el área de trabajo y seleccione **Existe** para llegar a todos los clientes que recibieron el correo electrónico.
   * Arrastre y suelte el elemento **Registros de seguimiento (seguimiento)** en el área de trabajo y seleccione **No existe** para dirigirse a todos los clientes que no hayan abierto el correo electrónico.

     ![](assets/wkf_push_example_2.png)

1. La actividad [Envío de notificaciones push](../../automating/using/push-notification-delivery.md) le permite introducir el contenido del mensaje y seleccionar los campos de personalización que desea utilizar:

   * Seleccione la opción **[!UICONTROL Recurring notification]**.
   * Defina el contenido de las notificaciones push. Para obtener más información sobre el contenido de las notificaciones push, consulte esta [sección](../../channels/using/preparing-and-sending-a-push-notification.md).
   * En el bloque **[!UICONTROL Schedule]**, seleccione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aquí, elegimos el Pacífico **[!UICONTROL Time zone of the contact date]** como en el flujo de trabajo **[!UICONTROL Scheduler]**.
   * En el campo **[!UICONTROL Optimize the sending time per recipient]**, seleccione **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Haga clic en el botón **[!UICONTROL Start]** para iniciar el flujo de trabajo recurrente.

   ![](assets/wkf_push_example_3.png)

El flujo de trabajo se está ejecutando. Comenzará en la fecha de inicio elegida de **[!UICONTROL Scheduler]** a las 8 p. m. hora del Pacífico; la notificación push recurrente se enviará todos los primeros días del mes a las 8 p. m., según la zona horaria de los clientes.

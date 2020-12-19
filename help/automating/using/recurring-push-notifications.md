---
solution: Campaign Standard
product: campaign
title: Envío de una notificación push recurrente con un flujo de trabajo
description: En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20.00 horas a los suscriptores de la aplicación móvil, en función de sus zonas horarias.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---


# Envío de una notificación push recurrente con un flujo de trabajo {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

En este ejemplo, se envía una notificación push personalizada todos los primeros días del mes a las 20.00 horas a los suscriptores de la aplicación móvil, en función de sus zonas horarias.

Para generar el flujo de trabajo, siga estos pasos:

1. La actividad [Planificador](../../automating/using/scheduler.md) le permite realizar el inicio de los días del flujo de trabajo antes del inicio del envío para poder enviar la notificación a todos los suscriptores a las 20:00 en cualquier huso horario determinado:

   * En el campo **[!UICONTROL Execution frequency]**, seleccione Mensual.
   * Seleccione las 8 pm en el campo **[!UICONTROL Time]**.
   * Elija el día en que se enviará el envío todos los meses.
   * Seleccione una fecha de inicio para el flujo de trabajo, al menos un día antes del inicio del envío. De lo contrario, algunos destinatarios podrían recibir el mensaje un día después si la hora seleccionada ya ha pasado en sus husos horarios.
   * En la ficha **[!UICONTROL Execution options]**, seleccione en qué huso horario inicio el flujo de trabajo en el campo **[!UICONTROL Time zone]**. Aquí, por ejemplo, el flujo de trabajo tendrá un inicio a las 8 p.m. hora del Pacífico, una semana antes del primer día del mes para permitir que se creen envíos para todos los husos horarios aplicables.

   >[!NOTE]
   >
   >De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. La actividad [Consulta](../../automating/using/query.md) le permite realizar el destinatario de sus clientes VIP de entre 20 y 30 años, que se han suscrito a su aplicación móvil y que no han abierto el correo electrónico enviado:

   * Seleccione una audiencia (sus clientes VIP) y filtre según su edad.
   * Arrastre y suelte las **Suscripciones en un elemento de aplicación** en el área de trabajo. Seleccione **Existe** y seleccione la aplicación móvil que desee utilizar.
   * Seleccione el correo electrónico que ha enviado a sus clientes.
   * Arrastre y suelte el elemento **Registros de envío (registros)** en el espacio de trabajo y seleccione **Existe** para destinatario de todos los clientes que recibieron el correo electrónico.
   * Arrastre y suelte el elemento **Registros de seguimiento (seguimiento)** en el área de trabajo y seleccione **No existe** para destinatario a todos los clientes que no abrieron el correo electrónico.

      ![](assets/wkf_push_example_2.png)

1. La actividad [envío de notificaciones push](../../automating/using/push-notification-delivery.md) le permite introducir el contenido del mensaje y seleccionar los campos de personalización que desee utilizar:

   * Seleccione la opción **[!UICONTROL Recurring notification]**.
   * Defina el contenido de la notificación push. Para obtener más información sobre el contenido de las notificaciones push, consulte esta [sección](../../channels/using/preparing-and-sending-a-push-notification.md).
   * En el bloque **[!UICONTROL Schedule]**, seleccione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aquí, elegimos el **[!UICONTROL Time zone of the contact date]** Pacífico como en el flujo de trabajo **[!UICONTROL Scheduler]**.
   * En el campo **[!UICONTROL Optimize the sending time per recipient]**, seleccione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Haga clic en el botón **[!UICONTROL Start]** para inicio del flujo de trabajo recurrente.

   ![](assets/wkf_push_example_3.png)

El flujo de trabajo se está ejecutando. El inicio se realizará en la fecha de inicio elegida del **[!UICONTROL Scheduler]** a las 8 pm, hora del Pacífico, y la notificación push recurrente se enviará cada primer día del mes a las 8 pm, dependiendo del huso horario del cliente.

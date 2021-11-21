---
title: Cálculo de la fecha de envío
description: Descubra cómo enviar un mensaje en una fecha y hora específicas.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 7%

---

# Cálculo de la fecha de envío{#computing-the-sending-date}

Puede definir una fórmula para enviar el mensaje a cada destinatario en una fecha y hora específicas.

## Personalización de la fórmula de fecha {#customizing-date-formula}

Por ejemplo, puede utilizar la optimización del tiempo de envío durante el proceso de aceleración.

Cuando se envían correos electrónicos utilizando una plataforma nueva, los proveedores de servicios de Internet (ISP) sospechan de las direcciones IP desconocidas. Si se envían, de repente, grandes volúmenes de correos electrónicos, los ISP suelen marcarlos como correo no deseado.

Para evitar que se lo considere correo no deseado, puede aumentar progresivamente el volumen enviado distribuyendo grandes volúmenes de correos electrónicos en diferentes momentos. Esto debería garantizar un desarrollo uniforme de la fase de inicio y permitir reducir la velocidad total de direcciones no válidas.

Por ejemplo, puede segmentar la audiencia de destino aleatoriamente para realizar el envío en cinco lotes. Enviará un primer lote que represente el 10 % de la audiencia de destino el 1 de junio a las 10:00 a.m., un segundo lote 24 horas después con el 15 % de la audiencia, etc.

Puede programar esto mediante un flujo de trabajo.

![](assets/send-time_opt_workflow1.png)

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo. Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arrastre y suelte una **Consulta** actividad en el flujo de trabajo y ábrala. Consulte la [Consulta](../../automating/using/query.md) para obtener más información.
1. Seleccione una audiencia, por ejemplo, todos sus clientes Gold y haga clic en **[!UICONTROL Confirm]** para guardar la consulta.
1. Arrastre y suelte una **Segmentación** actividad en el flujo de trabajo y ábrala. Consulte la [Segmentación](../../automating/using/segmentation.md) para obtener más información.
1. Defina cinco segmentos. Para cada segmento:

   * Complete la variable **[!UICONTROL Segment code]** campo: introduzca manualmente la fecha y hora deseadas para enviar el mensaje.

      Por ejemplo, desea enviar el primer lote el 1 de junio a las 10:00 AM GMT+1. Utilice el siguiente formato: **AAAA-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      Para enviar el siguiente lote al día siguiente, introduzca **2017-06-02 11:00:00+01** para el segundo segmento.

      Para los segmentos restantes, defina los lotes siguientes como se indica a continuación:

      * **2017-06-03 11:00:00+01**
      * **2017-06-04 11:00:00+01**
      * **2017-06-05 11:00:00+01**
   * Asegúrese de seleccionar la variable **[!UICONTROL Limit the population of this segment]** .

      En el **[!UICONTROL Limitation]** , seleccione **[!UICONTROL Random sampling]** e introduzca el porcentaje deseado para cada segmento: 10 para el primer lote, 15 para el segundo, etc.

      ![](assets/send-time_opt_segment_limitation.png)


1. Una vez definidos todos los segmentos, seleccione **[!UICONTROL Generate all segments in the same transition]** y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Arrastre y suelte una **Envío de correo electrónico** actividad en el flujo de trabajo y ábrala. Consulte la [Envío de correo electrónico](../../automating/using/email-delivery.md) para obtener más información.
1. Haga clic en el **[!UICONTROL Schedule]** en el panel de correo electrónico y seleccione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. En el **[!UICONTROL Start sending from]** , defina una fecha de contacto.
1. En el menú desplegable de optimización del tiempo de envío, seleccione **[!UICONTROL Send at a custom date defined by a formula]**.
1. Haga clic en el **[!UICONTROL Edit an expression]** del botón **[!UICONTROL Custom date formula]** campo .

   ![](assets/send-time_opt_formula_define.png)

1. Cree la siguiente expresión utilizando la variable **[!UICONTROL ToDateTime]** y **[!UICONTROL Segment code]** campo . También puede escribir directamente en la expresión, pero asegúrese de utilizar la sintaxis y la ortografía correctas.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   La variable **[!UICONTROL ToDateTime]** transforma el código de segmento de una cadena de texto a un valor de fecha y hora.

   Confirme la expresión para volver a la pantalla anterior.

   ![](assets/send-time_opt_formula_define_segment.png)

   En el **[!UICONTROL Schedule]** , la fórmula de fecha personalizada se muestra de la siguiente manera:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Confirme la programación, guarde la entrega y ejecute el flujo de trabajo.

La entrega se envía progresivamente a todos los destinatarios objetivo durante cinco días.

>[!NOTE]
>
>Asegúrese de que todas las fechas estén en el futuro al confirmar el envío. De lo contrario, el mensaje se enviará en cuanto se confirme el envío.

## Uso de una expresión {#using-an-expression}

La optimización del tiempo de envío también es útil para campañas que implican un centro de llamadas. Puede asegurarse de que todos los mensajes no se reciban al mismo tiempo. Esto permite a su organización procesar el número de llamadas según su capacidad.

Por ejemplo, desea enviar un correo electrónico que invite a sus clientes a ponerse en contacto con un centro de llamadas para obtener una oferta promocional. Para evitar sobrecargar el centro de llamadas, decide segmentar la audiencia de destino aleatoriamente para enviar el correo electrónico en cuatro lotes.

Puede programar esto mediante un flujo de trabajo.

![](assets/send-time_opt_workflow2.png)

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo. Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arrastre y suelte una **Consulta** actividad en el flujo de trabajo y ábrala. Consulte la [Consulta](../../automating/using/query.md) para obtener más información.
1. Seleccione una audiencia, por ejemplo, de más de 35 perfiles y haga clic en **[!UICONTROL Confirm]** para guardar la consulta.
1. Arrastre y suelte una **Segmentación** actividad en el flujo de trabajo y ábrala. Consulte la [Segmentación](../../automating/using/segmentation.md) para obtener más información.
1. Defina cuatro segmentos. Para cada segmento:

   * Defina los códigos de segmento de la siguiente manera:

      * 8:00 AM - 10:00 AM: **0**. El mensaje se envía al primer trimestre de la población objetivo a las 8:00 a. m. (fecha de contacto).
      * 10:00 AM - 12:00 PM: **2**. El mensaje se envía al segundo trimestre de la población objetivo a las 10:00 (fecha de contacto + 2 horas).
      * 2:00 PM - 4:00 PM: **6**. El centro de llamadas, que se cierra entre las 12:00 y las 2:00 p.m., se envía al tercer trimestre de la población objetivo a las 2:00 p.m. (fecha de contacto + 6 horas).
      * 4:00 PM - 6:00 PM: **8**. El mensaje se envía al último trimestre de la población objetivo a las 4:00 pm (fecha de contacto + 8 horas).

      >[!NOTE]
      >
      >La fecha de contacto se define en la actividad Email delivery más adelante en el flujo de trabajo.

   * Asegúrese de seleccionar la variable **[!UICONTROL Limit the population of this segment]** .
   * En el **[!UICONTROL Limitation]** , seleccione **[!UICONTROL Random sampling]** e introduzca el porcentaje deseado para cada segmento: **25**.


1. Una vez definidos todos los segmentos, seleccione **[!UICONTROL Generate all segments in the same transition]** y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Arrastre y suelte una **Envío de correo electrónico** actividad en el flujo de trabajo y ábrala. Consulte la [Envío de correo electrónico](../../automating/using/email-delivery.md) para obtener más información.
1. Haga clic en el **[!UICONTROL Schedule]** en el panel de correo electrónico.
1. Seleccione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. En el **[!UICONTROL Start sending from]** , defina una fecha de contacto.

   En este ejemplo, seleccione 25 de mayo a las 8:00 a. m.

1. En el menú desplegable de optimización del tiempo de envío, seleccione **[!UICONTROL Send at a custom date defined by a formula]** y haga clic en el botón **[!UICONTROL Edit an expression]** botón.

   ![](assets/send-time_opt_formula_expression.png)

1. En el **[!UICONTROL Expression editor]**, establezca la fecha y los códigos de segmento para calcular los datos de cada cliente.

   En la lista de funciones, seleccione **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   En los campos disponibles, seleccione **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Esto le permite recuperar la fecha y la hora especificadas en la variable **[!UICONTROL Start sending from]** campo .

   En la lista de funciones, seleccione **[!UICONTROL ToInteger]**. En los campos disponibles, seleccione **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Esto le permite recuperar los números especificados en los códigos de segmento.

   Debe obtener la siguiente fórmula:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Confirme para guardar la expresión. Confirme la programación, guarde la entrega y ejecute el flujo de trabajo.

* El primer segmento recibirá el mensaje en la fecha de contacto (25 de mayo a las 8:00 a. m.).
* El segundo segmento recibirá el mensaje dos horas más tarde (25 de mayo a las 10:00 AM).
* El tercer segmento recibirá el mensaje seis horas después (25 de mayo a las 2:00 pm).
* El cuarto segmento recibirá el mensaje ocho horas más tarde (25 de mayo a las 4:00 pm).

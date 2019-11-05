---
title: Cálculo de la fecha de envío
description: Descubra cómo enviar un mensaje en una fecha y hora específicas.
page-status-flag: nunca activado
uuid: fbbb37a0-7257-4407-a4c9-f76bf04460d4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: programar mensajes
discoiquuid: 02a87cc6-c40c-44fe-bb4e-b68870a4859b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Cálculo de la fecha de envío{#computing-the-sending-date}

Puede definir una fórmula para enviar el mensaje a cada destinatario en una fecha y hora específicas.

## Personalización de la fórmula de fecha {#customizing-date-formula}

Por ejemplo, puede utilizar la optimización del tiempo de envío durante el proceso de ampliación.

Cuando se envían correos electrónicos utilizando una plataforma nueva, los proveedores de servicios de Internet (ISP) sospechan de las direcciones IP desconocidas. Si se envían, de repente, grandes volúmenes de correos electrónicos, los ISP suelen marcarlos como correo no deseado.

Para evitar ser marcado como correo no deseado, puede aumentar progresivamente el volumen enviado distribuyendo grandes volúmenes de correos electrónicos en diferentes momentos. Esto debería garantizar un desarrollo uniforme de la fase de inicio y permitir reducir la velocidad total de direcciones no válidas.

Por ejemplo, puede segmentar la audiencia de destino de forma aleatoria para enviar la entrega en cinco lotes. Enviará un primer lote que represente el 10 % de la audiencia objetivo el 1 de junio a las 10:00 AM, un segundo lote 24 horas después con el 15 % de la audiencia, etc.

Puede programar esto mediante un flujo de trabajo.

![](assets/send-time_opt_workflow1.png)

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo. Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. Consulte la sección [Consulta](../../automating/using/query.md) .
1. Seleccione una audiencia, por ejemplo todos los clientes Gold y haga clic en **[!UICONTROL Confirm]** para guardar la consulta.
1. Arrastre y suelte una actividad **de segmentación** en el flujo de trabajo y ábrala. Consulte la sección [Segmentación](../../automating/using/segmentation.md) .
1. Defina cinco segmentos. Para cada segmento:

   * Rellene el **[!UICONTROL Segment code]** campo: introduzca manualmente la fecha y hora deseadas para enviar el mensaje.

      Por ejemplo, desea enviar el primer lote el 1 de junio a las 10:00 AM GMT+1. Utilice el siguiente formato: **AAAA-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      Para enviar el siguiente lote al día siguiente, introduzca **2017-06-02 10:00:00+01** para el segundo segmento.

      Para los segmentos restantes, defina los siguientes lotes de la siguiente manera:

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * Asegúrese de seleccionar la **[!UICONTROL Limit the population of this segment]** opción.

      En la **[!UICONTROL Limitation]** ficha, seleccione **[!UICONTROL Random sampling]** e introduzca el porcentaje deseado para cada segmento: 10 para el primer lote, 15 para el segundo, y así sucesivamente.

      ![](assets/send-time_opt_segment_limitation.png)


1. Una vez definidos todos los segmentos, seleccione **[!UICONTROL Generate all segments in the same transition]** y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Arrastre y suelte una actividad de envío **** de correo electrónico en el flujo de trabajo y ábrala. Consulte la sección Envío [por correo electrónico](../../automating/using/email-delivery.md) .
1. Haga clic en la **[!UICONTROL Schedule]** sección del tablero de correo electrónico y seleccione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. En el **[!UICONTROL Start sending from]** campo, defina una fecha de contacto.
1. En el menú desplegable de optimización del tiempo de envío, elija **[!UICONTROL Send at a custom date defined by a formula]**.
1. Haga clic en el **[!UICONTROL Edit an expression]** botón del **[!UICONTROL Custom date formula]** campo.

   ![](assets/send-time_opt_formula_define.png)

1. Cree la siguiente expresión utilizando la **[!UICONTROL ToDateTime]** función y el **[!UICONTROL Segment code]** campo. También puede escribir directamente en la expresión, pero asegúrese de utilizar la sintaxis y la ortografía correctas.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   La **[!UICONTROL ToDateTime]** función transforma el código del segmento de una cadena de texto a un valor de fecha y hora.

   Confirme que la expresión volverá a la pantalla anterior.

   ![](assets/send-time_opt_formula_define_segment.png)

   En la **[!UICONTROL Schedule]** ventana, la fórmula de fecha personalizada se muestra de la siguiente manera:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Confirme la programación, guarde la entrega y ejecute el flujo de trabajo.

La entrega se enviará progresivamente a todos los destinatarios durante cinco días.

>[!NOTE]
>
>Asegúrese de que todas las fechas estén en el futuro al confirmar el envío. De lo contrario, el mensaje se enviará en cuanto se confirme el envío.

## Uso de una expresión {#using-an-expression}

La optimización del tiempo de envío también es útil para campañas que involucran un centro de llamadas. Puede asegurarse de que no se reciben todos los mensajes al mismo tiempo. Esto permite a su organización procesar el número de llamadas según su capacidad.

Por ejemplo: desea enviar un correo electrónico invitando a sus clientes a ponerse en contacto con un centro de llamadas para obtener una oferta promocional. Para evitar agobiar el centro de llamadas, decide segmentar la audiencia objetivo de forma aleatoria para enviar el correo electrónico en cuatro lotes.

Puede programar esto mediante un flujo de trabajo.

![](assets/send-time_opt_workflow2.png)

1. Acceda a la lista de actividades de marketing y cree un nuevo flujo de trabajo. Consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. Consulte la sección [Consulta](../../automating/using/query.md) .
1. Seleccione una audiencia, por ejemplo, más de 35 perfiles y haga clic en **[!UICONTROL Confirm]** para guardar la consulta.
1. Arrastre y suelte una actividad **de segmentación** en el flujo de trabajo y ábrala. Consulte la sección [Segmentación](../../automating/using/segmentation.md) .
1. Defina cuatro segmentos. Para cada segmento:

   * Defina los códigos de segmento de la siguiente manera:

      * 8:00 AM - 10:00 AM: **0**. El mensaje se enviará al primer trimestre de la población objetivo a las 8:00 AM (fecha de contacto).
      * 10:00 AM - 12:00 PM: **2**. El mensaje se enviará al segundo trimestre de la población objetivo a las 10:00 AM (fecha de contacto + 2 horas).
      * 2:00 PM - 4:00 PM: **6**. El centro de llamadas, que se cierra entre las 12:00 y las 2:00 PM, el mensaje se enviará al tercer trimestre de la población objetivo a las 2:00 PM (fecha de contacto + 6 horas).
      * 4:00 PM - 6:00 PM: **8**. El mensaje se enviará al último trimestre de la población objetivo a las 4:00 pm (fecha de contacto + 8 horas).
      >[!NOTE]
      >
      >La fecha de contacto se definirá en la actividad de envío por correo electrónico más adelante en el flujo de trabajo.

   * Asegúrese de seleccionar la **[!UICONTROL Limit the population of this segment]** opción.
   * En la **[!UICONTROL Limitation]** ficha, seleccione **[!UICONTROL Random sampling]** e introduzca el porcentaje deseado para cada segmento: **25**.


1. Una vez definidos todos los segmentos, seleccione **[!UICONTROL Generate all segments in the same transition]** y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Arrastre y suelte una actividad de envío **** de correo electrónico en el flujo de trabajo y ábrala. Consulte la sección Envío [por correo electrónico](../../automating/using/email-delivery.md) .
1. Haga clic en la **[!UICONTROL Schedule]** sección del tablero de correo electrónico.
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. En el **[!UICONTROL Start sending from]** campo, defina una fecha de contacto.

   En este ejemplo, seleccione 25 de mayo a las 8:00 AM.

1. En el menú desplegable de optimización del tiempo de envío, elija **[!UICONTROL Send at a custom date defined by a formula]** y haga clic en el **[!UICONTROL Edit an expression]** botón.

   ![](assets/send-time_opt_formula_expression.png)

1. En el **[!UICONTROL Expression editor]**, establezca la fecha y los códigos de segmento para calcular los datos de cada cliente.

   En la lista de funciones, seleccione **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   En los campos disponibles, seleccione **[!UICONTROL Current delivery]** &gt; **[!UICONTROL Delivery scheduling]** &gt; **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Esto le permite recuperar la fecha y la hora especificadas en el **[!UICONTROL Start sending from]** campo.

   En la lista de funciones, seleccione **[!UICONTROL ToInteger]**. En los campos disponibles, seleccione **[!UICONTROL Additional data]** &gt; **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Esto le permite recuperar los números especificados en los códigos de segmento.

   Debe obtener la fórmula siguiente:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Confirme que desea guardar la expresión. Confirme la programación, guarde la entrega y ejecute el flujo de trabajo.

* El primer segmento recibirá el mensaje en la fecha de contacto (25 de mayo a las 8:00 AM).
* El segundo segmento recibirá el mensaje dos horas después (25 de mayo a las 10:00 AM).
* El tercer segmento recibirá el mensaje seis horas después (25 de mayo a las 2:00 pm).
* El cuarto segmento recibirá el mensaje ocho horas después (25 de mayo a las 4:00 pm).


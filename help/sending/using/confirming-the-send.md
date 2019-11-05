---
title: Confirmación del envío
description: Aprenda a finalizar la preparación del mensaje.
page-status-flag: nunca activado
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: enviar y rastrear mensajes
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: entrega,implementación,devolución
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Confirmación del envío{#confirming-the-send}

Una vez que haya terminado de preparar sus mensajes y se hayan realizado los pasos de aprobación, puede enviarlos. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

Solo los usuarios con la **[!UICONTROL Start deliveries]** función pueden confirmar el envío. Para obtener más información sobre esto, consulte la sección [Lista de funciones](../../administration/using/list-of-roles.md) .

Los usuarios sin esta función verán el siguiente mensaje:

![](assets/confirm_delivery_2.png)

Para enviar la entrega, haga clic en el **[!UICONTROL Confirm send]** botón que se encuentra en la barra de acciones del mensaje.

![](assets/confirm_delivery.png)

Se le pedirá que finalice el envío definitivamente haciendo clic en el **[!UICONTROL OK]** botón.

![](assets/confirm_delivery1.png)

Se está enviando el mensaje.

>[!NOTE]
>
>Si el mensaje está programado, se enviará cuando se llegue a la hora de envío. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Si está utilizando una entrega recurrente sin período de agregación, puede solicitar confirmación antes de enviar la entrega. Para ello, abra el **[!UICONTROL Schedule]** bloque del panel de envío y active la opción dedicada.

![](assets/confirmation_recurring_deliveries.png)

El **[!UICONTROL Deployment]** bloque muestra el progreso del envío.

Una vez que el mensaje se envía a los contactos, la **[!UICONTROL Deployment]** zona muestra los datos de KPI (Indicador de rendimiento clave), incluidos:

* El número de mensajes que se van a entregar
* Número de mensajes enviados
* El porcentaje de mensajes enviados
* El porcentaje de devoluciones y errores
* El porcentaje de mensajes abiertos
* El porcentaje de clics en los mensajes (para correos electrónicos)

   >[!NOTE]
   >
   >El **[!UICONTROL Open rate]** y **[!UICONTROL Click-through rate]** se actualiza cada hora.

![](assets/sending_delivery.png)

Si los KPI tardan demasiado en actualizarse o no tienen en cuenta los resultados de los registros de envío, haga clic en el **[!UICONTROL Compute stats]** botón de la **[!UICONTROL Deployment]** ventana.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles de cliente que forman parte de la audiencia. See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

Una vez que se envía un mensaje, puede realizar un seguimiento del comportamiento de los destinatarios y controlarlo para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Seguimiento de un envío](../../sending/using/monitoring-a-delivery.md)


---
title: Confirmación del envío
seo-title: Confirmación del envío
description: Confirmación del envío
seo-description: Obtenga información sobre cómo finalizar la preparación de los mensajes.
page-status-flag: no activado nunca
uuid: 1 eaecb 32-ffd 2-45 d 0-a 8 b 4-f 97 bee 59 a 1 bd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: enviar y rastrear mensajes
discoiquuid: 8 bb 160 b 1-7 de 9-4 c 1 f-bb 89-b 2 e 5 fdafed 41
context-tags: entrega, implementación, atrás
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9dd7c374903d0c57ac4881ed125c3215bd7fe11

---


# Confirming the send{#confirming-the-send}

Una vez que haya terminado de preparar los mensajes y que se hayan llevado a cabo los pasos de aprobación, puede enviarlos. For more on messages preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

Only users with the **[!UICONTROL Start deliveries]** role can confirm send. For more on this, refer to the [List of roles](../../administration/using/list-of-roles.md) section.

Los usuarios sin esta función verán el mensaje siguiente:

![](assets/confirm_delivery_2.png)

To send your delivery, click the **[!UICONTROL Confirm send]** button found in the message's action bar.

![](assets/confirm_delivery.png)

You will be asked to finalize the send definitively by clicking the **[!UICONTROL OK]** button.

![](assets/confirm_delivery1.png)

El mensaje se está enviando.

>[!NOTE]
>
>Si el mensaje está programado, se enviará cuando se llegue al tiempo de envío. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Si utiliza un envío recurrente sin período de agregación, puede solicitar confirmación antes de enviar la entrega. To do this, open the **[!UICONTROL Schedule]** block of the delivery dashboard, then activate the dedicated option.

![](assets/confirmation_recurring_deliveries.png)

**[!UICONTROL Deployment]** El bloque muestra el progreso del envío.

Once the message is sent to the contacts, the **[!UICONTROL Deployment]** zone shows your KPIs (Key Performance Indicator) data , including:

* Cantidad de mensajes que entregar
* Cantidad de mensajes enviados
* El porcentaje de mensajes entregados
* El porcentaje de devoluciones y errores
* El porcentaje de mensajes abiertos
* El porcentaje de clics en los mensajes (para correos electrónicos)

   >[!NOTE]
   >
   >The **[!UICONTROL Open rate]** and **[!UICONTROL Click-through rate]** are updated every hour.

![](assets/sending_delivery.png)

If the KPIs take too long to update or don't take into account the results from the sending logs, click the **[!UICONTROL Compute stats]** button in the **[!UICONTROL Deployment]** window.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles de cliente que forman parte de la audiencia. See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

Una vez enviado el mensaje, puede rastrear el comportamiento de los destinatarios y monitorearlos para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Supervisión de una entrega](../../sending/using/monitoring-a-delivery.md)


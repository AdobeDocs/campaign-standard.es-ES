---
title: Confirmación del envío
description: Aprenda a finalizar la preparación del mensaje.
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---


# Confirmación del envío{#confirming-the-send}

Una vez que haya terminado de preparar sus mensajes y se hayan realizado los pasos de aprobación, puede enviarlos. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

Solo los usuarios con la función **[!UICONTROL Start deliveries]** pueden confirmar el envío. Para obtener más información al respecto, consulte la sección [Lista de funciones](../../administration/using/list-of-roles.md).

Los usuarios que no tengan esta función verán el siguiente mensaje:

![](assets/confirm_delivery_2.png)

Para entregar el envío, haga clic en el botón **[!UICONTROL Confirm send]**, en la barra de acciones del mensaje.

![](assets/confirm_delivery.png)

Se le pedirá que finalice el envío definitivamente haciendo clic en el botón **[!UICONTROL OK]**.

![](assets/confirm_delivery1.png)

El mensaje estará en proceso de envío

>[!NOTE]
>
>Si el mensaje está programado, se enviará cuando se llegue a la hora de envío. Para obtener más información sobre la programación de mensajes, consulte [esta sección](../../sending/using/about-scheduling-messages.md).

Si utiliza un envío recurrente sin período de acumulación, puede solicitar confirmación antes de proceder con el envío. Para ello, abra el bloque **[!UICONTROL Schedule]** del panel de envío y active la opción dedicada.

![](assets/confirmation_recurring_deliveries.png)

El bloque **[!UICONTROL Deployment]** muestra el progreso del envío.

Una vez que el mensaje se envía a los contactos, la zona **[!UICONTROL Deployment]** muestra los datos de KPI (indicador de rendimiento clave), que incluye la siguiente información:

* El número de mensajes que enviar
* El número de mensajes enviados
* El porcentaje de mensajes entregados
* El porcentaje de devoluciones y errores
* El porcentaje de mensajes abiertos
* El porcentaje de clics en los mensajes (en el caso de correos electrónicos)

   >[!NOTE]
   >
   >La **[!UICONTROL Open rate]** y **[!UICONTROL Click-through rate]** se actualiza cada hora.

![](assets/sending_delivery.png)

Si los KPI tardan demasiado en actualizarse o no tienen en cuenta los resultados de los registros de envío, haga clic en el botón **[!UICONTROL Compute stats]** de la ventana **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

El mensaje se puede ver en el historial de uno de los perfiles de cliente que forman parte de la audiencia. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Una vez enviado un mensaje, puede realizar un seguimiento del comportamiento de sus destinatarios y monitorearlo para medir su impacto. Para obtener más información, consulte estas secciones:

* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)


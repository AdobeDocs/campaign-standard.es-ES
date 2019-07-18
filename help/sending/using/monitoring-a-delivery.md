---
title: Supervisión de una entrega
seo-title: Supervisión de una entrega
description: Supervisión de una entrega
seo-description: Descubra cómo supervisar una entrega.
page-status-flag: no activado nunca
uuid: 7772 c 607-debd -40 fd -8322-4 d 49119979 b 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: monitoreo de mensajes
discoiquuid: eb 9 fa 216-4568-423 a -9396-8 f 7 b 82181 ae 9
context-tags: entrega, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

Existen varias formas de supervisar una entrega y medir su impacto:

* **Registros de mensajes**: Se puede acceder a estos registros directamente desde el panel de mensajes. Muestran los detalles del envío, el objetivo que se ha excluido y el motivo, así como la información de seguimiento como aperturas y clics.

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. See [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   El registro contiene todos los mensajes relacionados con la entrega y las pruebas. Los iconos específicos permiten identificar errores o advertencias. For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **Alertas de entrega**: Para realizar un seguimiento de la entrega correcta o fallida, Adobe Campaign proporciona un sistema de alerta por correo electrónico que envía notificaciones para informar a los usuarios de las actividades importantes del sistema.
* **Informes**: Desde el panel de mensajes, puede acceder a varios informes para este mensaje específico. You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* Un administrador también puede exportar registros en un archivo independiente que se puede procesar en sus propias herramientas de informes o BI. For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**Temas relacionados:**

* [Recepción de alertas cuando se producen errores](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informes](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

The **[!UICONTROL Sending logs]** tab offers a history of every occurrence of this delivery. La lista de mensajes enviados y sus estados se almacena aquí. Permite ver el estado de entrega de cada destinatario.

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

The **[!UICONTROL Exclusion logs]** tab lists all the messages that have been excluded from the target sent and specifies the reason for the send failure.

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

The **[!UICONTROL Exclusion causes]** tab displays the volume (in number of messages) of messages that were excluded from the target send.

![](assets/sending_delivery5.png)


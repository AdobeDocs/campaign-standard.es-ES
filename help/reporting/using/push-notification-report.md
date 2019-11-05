---
title: Informe de notificaciones push
description: Con el informe predeterminado de notificaciones Push, conozca el éxito de las notificaciones push.
page-status-flag: nunca activado
uuid: 5b121a37-1c09-4749-a409-6989978ddc4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: informes
content-type: referencia
topic-tags: lista de informes
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informe de notificaciones push{#push-notification-report}

>[!CAUTION]
>
>Tenga en cuenta que debe arrastrar y soltar las **[!UICONTROL Message type]** métricas en las tablas para dividir los datos según los tipos de envío, en este caso envíos de notificaciones push.

El informe de notificaciones **** push proporciona detalles del rendimiento de marketing de las notificaciones push en Adobe Campaign. Este informe predeterminado le ayudará a comprender cómo interactúan los usuarios con las notificaciones push, las aplicaciones móviles y los envíos.

Se requiere cierta configuración en la aplicación móvil para implementar el seguimiento push, consulte esta [página](https://helpx.adobe.com/campaign/kb/push-tracking.html) para ver los pasos detallados.

![](assets/dynamic_report_push.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar la forma en que se muestran los detalles en sus respectivas configuraciones de visualización.

La primera tabla Resumen **de participación de notificaciones** push se divide en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles para la reactividad del destinatario a la entrega:

* **[!UICONTROL Processed/sent]**::Número total de notificaciones push enviadas.
* **[!UICONTROL Delivered]**::Número de notificaciones push enviadas correctamente, en relación con el número total de notificaciones push enviadas.
* **[!UICONTROL Impressions]**::Número de veces que se ha enviado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número entregado. Esto garantiza que el dispositivo reciba el mensaje y reenvíe esa información al servidor.
* **[!UICONTROL Unique impressions]**::Número de impresiones por destinatario.
* **[!UICONTROL Click through rate]**::Porcentaje de usuarios que interactuaron con la notificación push.
* **[!UICONTROL Open rate]**::Porcentaje de notificaciones push abiertas.

![](assets/dynamic_report_push_2.png)

La segunda tabla Clics y aperturas de notificaciones **Push se divide** en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles para el comportamiento del destinatario por entrega:

* **[!UICONTROL Impressions]**:: Total de notificaciones push vistas por los destinatarios.
* **[!UICONTROL Unique impressions]**::Número de impresiones por destinatario.
* **[!UICONTROL Click]**:: Número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario deseaba ver la notificación, que luego se moverá al seguimiento Push Open o la descartará.
* **[!UICONTROL Unique clicks]**::Número de veces que un usuario único interactúa con la notificación push, por ejemplo, haciendo clic en la notificación o en el botón.
* **[!UICONTROL Open]**::Número total de notificaciones push enviadas al dispositivo y en las que los usuarios han hecho clic para abrir la aplicación. Esto es similar a los clics push, excepto que no se activará un push Open si se descartó la notificación.
* **[!UICONTROL Unique Opens]**::Número de destinatarios que abrieron el envío.


---
solution: Campaign Standard
product: campaign
title: Informe de notificaciones push
description: Con el informe predeterminado de notificaciones Push, conozca el éxito de las notificaciones push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Informe de notificaciones push{#push-notification-report}

>[!CAUTION]
>
>Tenga en cuenta que debe arrastrar y soltar las métricas **[!UICONTROL Message type]** en las tablas para dividir los datos en función de los tipos de envíos, en este caso envíos de notificaciones push.

El informe **Push notification** proporciona detalles del rendimiento de mercadotecnia de las notificaciones push en Adobe Campaign. Este informe predeterminado le ayudará a comprender cómo interactúan los usuarios con las notificaciones push, las aplicaciones móviles y los envíos.

Se requiere cierta configuración en la aplicación móvil para implementar el seguimiento push, consulte esta [página](../../administration/using/push-tracking.md) para conocer los pasos detallados.

![](assets/dynamic_report_push.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar la forma en que se muestran los detalles en sus respectivas configuraciones de visualización.

La primera tabla **Resumen de compromiso de notificación push** se divide en tres categorías: por día, por aplicación móvil y por envío. Contiene los datos disponibles para la reactividad del destinatario al envío:

* **[!UICONTROL Processed/sent]**:: Número total de notificaciones push enviadas.
* **[!UICONTROL Delivered]**:: Número de notificaciones push enviadas correctamente, en relación con el número total de notificaciones push enviadas.
* **[!UICONTROL Impressions]**:: Número de veces que se ha enviado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número entregado. Esto garantiza que el dispositivo reciba el mensaje y reenvíe esa información al servidor.
* **[!UICONTROL Unique impressions]**:: Número de impresiones por destinatario.
* **[!UICONTROL Click through rate]**:: Porcentaje de usuarios que interactuaron con la notificación push.
* **[!UICONTROL Open rate]**:: Porcentaje de notificaciones push abiertas.

![](assets/dynamic_report_push_2.png)

La segunda tabla **Clics y aperturas de notificaciones push** se divide en tres categorías: por día, por aplicación móvil y por envío. Contiene los datos disponibles para el comportamiento de destinatario por envío:

* **[!UICONTROL Impressions]**:: Total de notificaciones push vistas por destinatarios.
* **[!UICONTROL Unique impressions]**:: Número de impresiones por destinatario.
* **[!UICONTROL Click]**:: Número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario deseaba realizar la vista de la notificación, que luego se moverá al seguimiento Push Open o la descartará.
* **[!UICONTROL Unique clicks]**:: Número de veces que un usuario único interactúa con la notificación push, por ejemplo, haciendo clic en la notificación o en el botón.
* **[!UICONTROL Open]**:: Número total de notificaciones push enviadas al dispositivo y en las que los usuarios han hecho clic para abrir la aplicación. Esto es similar a los clics push, excepto que no se activará un push Open si se descartó la notificación.
* **[!UICONTROL Unique Opens]**:: Número de destinatarios que abrieron el envío.


---
title: Informe de notificaciones push
description: Con el informe de notificaciones push listo para usar, conozca el éxito de las notificaciones push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# Informe de notificaciones push{#push-notification-report}

>[!CAUTION]
>
>Tenga en cuenta que debe arrastrar y soltar el **[!UICONTROL Message type]** a las tablas para dividir los datos en función de los tipos de envío, en este caso envíos de notificaciones push.

La variable **Notificaciones push** proporciona detalles sobre el rendimiento de marketing de las notificaciones push en Adobe Campaign. Este informe de serie le ayuda a comprender cómo interactúan los usuarios con las notificaciones push, las aplicaciones móviles y los envíos.

Se requiere cierta configuración en la aplicación móvil para implementar el seguimiento push; consulte esta [página](../../administration/using/push-tracking.md) para ver los pasos detallados.

![](assets/dynamic_report_push.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivos ajustes de visualización.

La primera tabla **Resumen de participación de notificaciones push** se divide en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles para la reacción del destinatario a la entrega:

* **[!UICONTROL Processed/sent]**: Número total de notificaciones push enviadas.
* **[!UICONTROL Delivered]**: Número de notificaciones push enviadas correctamente, en relación con el número total de notificaciones push enviadas.
* **[!UICONTROL Impressions]**: Número de veces que se ha enviado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número entregado. Esto garantiza que el dispositivo obtuvo el mensaje y retransmitió esa información al servidor.
* **[!UICONTROL Unique impressions]**: Número de impresiones por destinatario.
* **[!UICONTROL Click through rate]**: Porcentaje de usuarios que interactuaron con la notificación push.
* **[!UICONTROL Open rate]**: Porcentaje de notificaciones push abiertas.

![](assets/dynamic_report_push_2.png)

La segunda tabla **Clics y aperturas de notificaciones push** se divide en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles para el comportamiento del destinatario por envío:

* **[!UICONTROL Impressions]**: Total de notificaciones push vistas por los destinatarios.
* **[!UICONTROL Unique impressions]**: Número de impresiones por destinatario.
* **[!UICONTROL Click]**: Número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario quería ver la notificación, que luego se moverá al seguimiento de Push Open, o la descartará.
* **[!UICONTROL Unique clicks]**: Número de veces que un usuario único interactúa con la notificación push, por ejemplo, haciendo clic en la notificación o el botón.
* **[!UICONTROL Open]**: Número total de notificaciones push enviadas al dispositivo y en las que los usuarios han hecho clic para abrir la aplicación. Esto es similar al clic push , excepto que no se activará un push Open si se descarta la notificación.
* **[!UICONTROL Unique Opens]**: Número de destinatarios que abrieron la entrega.

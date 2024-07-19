---
title: Informe de notificaciones push
description: Con el informe Predeterminado de notificaciones push, obtenga información sobre el éxito de las notificaciones push.
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
>Tenga en cuenta que debe arrastrar y soltar las métricas **[!UICONTROL Message type]** en las tablas para dividir los datos según los tipos de entrega, en este caso entregas de notificaciones push.

El informe **Notificación push** proporciona detalles sobre el rendimiento de marketing de las notificaciones push en Adobe Campaign. Este informe predeterminado le ayuda a comprender cómo interactúan los usuarios con las notificaciones push, las aplicaciones móviles y las entregas.

Se requiere cierta configuración en la aplicación móvil para implementar el seguimiento push. Consulte esta [página](../../administration/using/push-tracking.md) para ver los pasos detallados.

![](assets/dynamic_report_push.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivos ajustes de visualización.

La primera tabla **Resumen de participación de notificaciones push** se divide en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles para la reacción del destinatario a la entrega:

* **[!UICONTROL Processed/sent]**: número total de notificaciones push enviadas.
* **[!UICONTROL Delivered]**: número de notificaciones push enviadas correctamente en relación con la cantidad total de notificaciones push enviadas.
* **[!UICONTROL Impressions]**: número de veces que se ha entregado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número enviado. Esto garantiza que el dispositivo reciba el mensaje y retransmita esa información al servidor.
* **[!UICONTROL Unique impressions]**: número de impresiones por destinatario.
* **[!UICONTROL Click through rate]**: porcentaje de usuarios que interactuaron con la notificación push.
* **[!UICONTROL Open rate]**: porcentaje de notificaciones push abiertas.

![](assets/dynamic_report_push_2.png)

La segunda tabla **Clics y aperturas de notificaciones push** se divide en tres categorías: por día, por aplicación móvil y por entrega. Contiene los datos disponibles del comportamiento del destinatario por envío:

* **[!UICONTROL Impressions]**: Total de notificaciones push vistas por los destinatarios.
* **[!UICONTROL Unique impressions]**: número de impresiones por destinatario.
* **[!UICONTROL Click]**: número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario deseaba ver la notificación, que luego se moverá al seguimiento de Apertura push, o descartarla.
* **[!UICONTROL Unique clicks]**: número de veces que un usuario único interactúa con la notificación push, por ejemplo, hace clic en la notificación o el botón.
* **[!UICONTROL Open]**: número total de notificaciones push enviadas al dispositivo y en las que los usuarios hicieron clic al abrir la aplicación. Esto es similar al clic push, excepto que una apertura push no se activa si se descarta la notificación.
* **[!UICONTROL Unique Opens]**: número de destinatarios que abrieron la entrega.

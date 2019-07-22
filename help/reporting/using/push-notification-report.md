---
title: Informe de notificaciones Push
seo-title: Informe de notificaciones Push
description: Informe de notificaciones Push
seo-description: Con el informe predeterminado de notificaciones Push, obtenga información sobre el éxito de las notificaciones push.
page-status-flag: no activado nunca
uuid: 5 b 121 a 37-1 c 09-4749-a 409-6989978 ddc 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: lista de informes
discoiquuid: a 425 cd 59-edfd -42 c 5-a 6 bd -38773 c 353 ff 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Push notification report{#push-notification-report}

>[!CAUTION]
>
>Please note that you have to drag and drop the **[!UICONTROL Message type]** metrics to your tables to split your data depending on your delivery types, in this case push notification deliveries.

The **Push notification** report provides details of marketing performance of push notifications in Adobe Campaign. Este informe predeterminado le ayudará a comprender cómo interactúan los usuarios con las notificaciones push, las aplicaciones móviles y los envíos.

Some configuration is required in the mobile application to implement push tracking, refer to this [page](https://helpx.adobe.com/campaign/kb/push-tracking.html) for the detailed steps.

![](assets/dynamic_report_push.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivas configuraciones de visualización.

The first table **Push notification Engagement Summary** is split into three categories: by day, by mobile app and by delivery. Contiene los datos disponibles para la reactividad de destinatario al envío:

* **[!UICONTROL Processed/sent]**: Número total de notificaciones push enviadas.
* **[!UICONTROL Delivered]**: El número de notificaciones push se envió correctamente en relación con el número total de notificaciones push enviadas.
* **[!UICONTROL Impressions]**: Número de veces que se ha entregado una notificación Push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número entregado. Esto garantiza que el dispositivo tenga el mensaje y vuelva a enviarla al servidor.
* **[!UICONTROL Unique impressions]**: Número de impresiones por destinatario.
* **[!UICONTROL Click through rate]**: Porcentaje de usuarios que interactuaron con la notificación Push.
* **[!UICONTROL Open rate]**: Porcentaje de notificaciones push abiertas.

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. Contiene los datos disponibles para el comportamiento del destinatario por entrega:

* **[!UICONTROL Impressions]**: Total de notificaciones push que ven los destinatarios.
* **[!UICONTROL Unique impressions]**: Número de impresiones por destinatario.
* **[!UICONTROL Click]**: Número de veces que se ha entregado una notificación Push al dispositivo y que ha pulsado el usuario. El usuario desea ver la notificación, que luego se moverá para el seguimiento Push o la rechazará.
* **[!UICONTROL Unique clicks]**: Número de veces que un usuario único interactúa con la notificación push, por ejemplo, clics en la notificación o en el botón.
* **[!UICONTROL Open]**: La cantidad total de notificaciones push enviadas al dispositivo y en las que los usuarios hicieron clic, abriendo así la aplicación. Esto es similar al clic Push, excepto que la opción Push push no se activará si se ha cerrado la notificación.
* **[!UICONTROL Unique Opens]**: Número de destinatarios que abrieron el envío.


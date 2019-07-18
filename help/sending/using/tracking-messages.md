---
title: Seguimiento de mensajes
seo-title: Seguimiento de mensajes
description: Seguimiento de mensajes
seo-description: Conozca cómo rastrear el comportamiento de los destinatarios de envíos.
page-status-flag: no activado nunca
uuid: c 3721647-0663-4614-a 9 c 9-3 b 3 a 40 af 328 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: enviar y rastrear mensajes
discoiquuid: 6 fa 50 f 0 d -3 dcf -4 a 9 e-bccc -1 ecda 2 bfb 449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

Gracias a sus funcionalidades de seguimiento, Adobe Campaign permite rastrear el comportamiento de los destinatarios de envíos. Para ello, Adobe Campaign utiliza cookies de sesión y cookies permanentes.

Puede informar a los usuarios de que los sitios están equipados con herramientas de seguimiento Web a través de una solicitud de autorización (que se abre en la página, por ejemplo) con una casilla de verificación para autorizar el uso de cookies o agregar una pancarta al principio de la primera página en la que aterrizan, etc. Las ventanas emergentes deben evitarse, ya que los navegadores suelen bloquearlas.

Adobe Campaign utiliza dos tipos de cookies:

* Una cookie de sesión (nlid). Contiene el identificador del correo electrónico enviado al contacto (broadlogid) y el identificador de la plantilla de mensaje (deliveryid). Se agrega cuando el contacto hace clic en una URL incluida en un correo electrónico enviado por Adobe Campaign y le permite rastrear su comportamiento en la Web. Esta cookie de sesión se borra automáticamente cuando se cierra el explorador. El contacto puede configurar su explorador para que rechace las cookies.
* Una cookie compartida entre soluciones de Adobe Experience Cloud. Esto permite identificar a los usuarios que interactúan con las soluciones de Experience Cloud cuando visitan un sitio web. The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. Esta ficha muestra la información de seguimiento de los mensajes enviados, como todas las direcciones URL rastreadas por Adobe Campaign. La información de seguimiento de esta ficha se actualiza cada 10 minutos.

>[!NOTE]
>
>Si el seguimiento no está habilitado para una entrega, esta ficha no se muestra. Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

En el ejemplo anterior, el destinatario:

* Se abrirá el mensaje.
* Se hizo clic en el vínculo personalizado "MÁS INFORMACIÓN".
* Se hizo clic en la cancelación de suscripción y en el vínculo de página reflejada.

In the **[!UICONTROL Type]** column, the possible values are:

* **[!UICONTROL Email click]**: los destinatarios hicieron clic en un vínculo personalizado.
* **[!UICONTROL Mirror page]**: el destinatario hizo clic en un vínculo a la página reflejada.
* **[!UICONTROL Open]**: el destinatario abrió el correo electrónico.
* **[!UICONTROL Opt-out]**: el destinatario hizo clic en un vínculo de cancelación de suscripción.

>[!NOTE]
>
>For the **push notification** channel, only clicks on mobile notifications are tracked. In that case, the value will be **[!UICONTROL Click on mobile notification]**.

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

The **[!UICONTROL Tracked URLs]** tab regroups the URLs contained in the sent message, including their URL type and their source URL.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).

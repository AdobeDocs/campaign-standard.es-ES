---
title: Seguimiento de mensajes
description: Obtenga información sobre cómo rastrear el comportamiento de los destinatarios de la entrega.
page-status-flag: nunca activado
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: enviar y rastrear mensajes
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Seguimiento de mensajes{#tracking-messages}

## Acerca del seguimiento {#about-tracking}

Gracias a sus funciones de seguimiento, Adobe Campaign le permite realizar un seguimiento del comportamiento de los destinatarios de la entrega. Para ello, Adobe Campaign utiliza cookies de sesión y cookies permanentes.

Puede informar a los usuarios de que sus sitios están equipados con herramientas de seguimiento Web a través de una solicitud de autorización (que aparece sobre la página, por ejemplo) con una casilla de verificación para autorizar el uso de cookies, o agregar una pancarta al principio de la primera página en la que aterrizan, etc. Las ventanas emergentes deben evitarse, ya que los navegadores suelen bloquearlas.

Adobe Campaign utiliza dos tipos de cookies:

* Una cookie de sesión (nlid). Contiene el identificador del correo electrónico enviado al contacto (widelogId) y el identificador de la plantilla de mensaje (deliveryId). Se añade cuando el contacto hace clic en una dirección URL incluida en un correo electrónico enviado por Adobe Campaign y le permite hacer un seguimiento de su comportamiento en la web. Esta cookie de sesión se borra automáticamente cuando se cierra el explorador. El contacto puede configurar el explorador para que rechace las cookies.
* Una cookie compartida entre las soluciones de Adobe Experience Cloud. Esto le permite identificar a los usuarios que interactúan con las soluciones de Experience Cloud cuando visitan un sitio web. La descripción de esta cookie está disponible aquí: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

La información de seguimiento está disponible para cada contacto de la base de datos en **[!UICONTROL integrated customer profiles]**. Para obtener más información, consulte [esta sección](../../audiences/using/integrated-customer-profile.md).

## “Logs” de seguimiento{#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. Esta ficha muestra la información de seguimiento de los mensajes enviados, como todas las direcciones URL que Adobe Campaign ha rastreado. La información de seguimiento de esta ficha se actualiza cada 10 minutos.

>[!NOTE]
>
>Si el seguimiento no está habilitado para una entrega, esta ficha no se muestra. Los registros de seguimiento solo están disponibles para los canales de **correo electrónico** y de notificación **** push.

![](assets/tracking_logs.png)

En el ejemplo anterior, el destinatario:

* Se abrió el mensaje.
* Haga clic en el vínculo personalizado "MÁS INFORMACIÓN".
* Se ha hecho clic en el vínculo de cancelación de suscripción y de página reflejada.

En la **[!UICONTROL Type]** columna, los valores posibles son:

* **[!UICONTROL Email click]**:: los destinatarios hicieron clic en un vínculo personalizado.
* **[!UICONTROL Mirror page]**:: el destinatario hizo clic en un vínculo a la página reflejada.
* **[!UICONTROL Open]**:: el destinatario abrió el correo electrónico.
* **[!UICONTROL Opt-out]**:: el destinatario hizo clic en un vínculo de cancelación de suscripción.

>[!NOTE]
>
>Para el canal de notificaciones **** push, solo se realiza el seguimiento de los clics en notificaciones móviles. En ese caso, el valor será **[!UICONTROL Click on mobile notification]**.

Para obtener más información sobre cómo insertar vínculos de seguimiento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

## Direcciones URL rastreadas {#tracked-urls}

La **[!UICONTROL Tracked URLs]** ficha reagrupa las direcciones URL incluidas en el mensaje enviado, incluido su tipo de dirección URL y su dirección URL de origen.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).

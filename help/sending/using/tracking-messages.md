---
title: Seguimiento de mensajes
description: Obtenga información sobre cómo rastrear el comportamiento de los destinatarios de envío.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2926b916ac8e8a2605694758407c48b1db359c60

---


# Seguimiento de mensajes{#tracking-messages}

## Acerca del seguimiento {#about-tracking}

Gracias a sus funciones de seguimiento, Adobe Campaign le permite rastrear el comportamiento de sus destinatarios de envío. Para ello, Adobe Campaign utiliza cookies de sesión y cookies permanentes.

Puede informar a los usuarios de que sus sitios están equipados con herramientas de seguimiento Web a través de una solicitud de autorización (que aparece sobre la página, por ejemplo) con una casilla de verificación para autorizar el uso de cookies, o agregar una pancarta en la parte superior de la primera página en la que aterrizan, etc. Las ventanas emergentes deben evitarse, ya que los navegadores suelen bloquearlas.

La información de seguimiento está disponible para cada contacto de la base de datos en **[!UICONTROL integrated customer profiles]**. Para obtener más información, consulte [esta sección](../../audiences/using/integrated-customer-profile.md).

Adobe Campaign utiliza dos tipos de cookies:

* Una cookie de sesión (nlid). Contiene el identificador del correo electrónico enviado al contacto (widelogId) y el identificador de la plantilla de mensaje (deliveryId). Se añade cuando el contacto hace clic en una dirección URL incluida en un correo electrónico enviado por Adobe Campaign y le permite hacer un seguimiento de su comportamiento en la web. Esta cookie de sesión se borra automáticamente cuando se cierra el explorador. El contacto puede configurar el explorador para que rechace las cookies.
* Una cookie compartida entre las soluciones de Adobe Experience Cloud. Esto le permite identificar a los usuarios que interactúan con las soluciones de Experience Cloud cuando visitan un sitio web. La descripción de esta cookie está disponible aquí: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

El seguimiento con Adobe Campaign Standard le permite acceder a las siguientes funcionalidades:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="condiciones" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="condiciones" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="condiciones" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="condiciones" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="condiciones" src="assets/icon_report.png"/></a>

</tr>
<tr>
<td>Seguimiento del correo electrónico</td>
<td>Seguimiento push</td>
<td>Direcciones URL rastreadas</td>
<td>“Logs” de seguimiento</td>
<td>Informe de seguimiento</td>
</tr>

</table>

## “Logs” de seguimiento{#tracking-logs}

La pestaña **[!UICONTROL Tracking logs]** enumera el historial de seguimiento de esta entrega. Esta ficha muestra la información de seguimiento de los mensajes enviados, como todas las direcciones URL rastreadas por Adobe Campaign. La información de seguimiento de esta ficha se actualiza cada 10 minutos.

>[!NOTE]
>
>Si el seguimiento no está habilitado para un envío, esta ficha no se muestra. Solo hay Registros de seguimiento disponibles para los canales de **correo electrónico** y de notificación **** push.

![](assets/tracking_logs.png)

En el ejemplo anterior, el destinatario:

* Se abrió el mensaje.
* Haga clic en el vínculo personalizado &quot;MÁS INFORMACIÓN&quot;.
* Se hizo clic en el vínculo baja y de página espejo.

En la **[!UICONTROL Type]** columna, los valores posibles son:

* **[!UICONTROL Email click]**:: los destinatarios hicieron clic en un vínculo personalizado.
* **[!UICONTROL Mirror page]**:: el destinatario hizo clic en un vínculo a la página espejo.
* **[!UICONTROL Open]**:: el destinatario abrió el correo electrónico.
* **[!UICONTROL Opt-out]**:: el destinatario hizo clic en un vínculo baja.

>[!NOTE]
>
>Para el canal de notificaciones **** push, solo se realiza el seguimiento de los clics en las notificaciones móviles. En ese caso, el valor será **[!UICONTROL Click on mobile notification]**.

Para obtener más información sobre cómo insertar vínculos de seguimiento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

## Direcciones URL rastreadas {#tracked-urls}

La **[!UICONTROL Tracked URLs]** ficha reagrupa las direcciones URL incluidas en el mensaje enviado, incluido su tipo de dirección URL y su dirección URL de origen.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).

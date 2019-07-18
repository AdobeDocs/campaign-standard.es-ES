---
title: Acerca de las URL rastreadas
seo-title: Acerca de las URL rastreadas
description: Acerca de las URL rastreadas
seo-description: Descubra cómo administrar todas las direcciones URL del contenido que se rastrearán.
page-status-flag: no activado nunca
uuid: dfe 5146 b -5256-431 c -87 b 3-3 c 54817 eba 36
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: administración de vínculos
discoiquuid: d 9 b 0 b 3 c 2-874 b -4 cb 4-bce 9-c 0194 a 19 f 25 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

Adobe Campaign permite rastrear el comportamiento de los destinatarios cuando hacen clic en una URL incluida en un correo electrónico. For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

**[!UICONTROL Links]** El icono de la barra de acciones muestra automáticamente la lista de todas las direcciones URL del contenido que se rastrearán.

![](assets/des_links.png)

>[!NOTE]
>
>El seguimiento está activado de forma predeterminada. Esta funcionalidad solo está disponible para correos electrónicos si el seguimiento se ha activado en Adobe Campaign. For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

La dirección URL, categoría, etiqueta y tipo de seguimiento de cada vínculo se pueden modificar desde esta lista. Para editar un vínculo, haga clic en el icono de lápiz correspondiente.

![](assets/des_links_tracking.png)

Para cada URL rastreada, puede establecer el modo de seguimiento en uno de estos valores:

* **Rastreado**: activa el seguimiento en esta URL.
* **Reflejar página**: considera que esta URL es una URL de página de reflejo.
* **Nunca**: no activa nunca el seguimiento de esta URL. Esta información se guarda: Si la URL vuelve a aparecer en un mensaje futuro, su seguimiento se desactivará automáticamente.
* **Exclusión**: considera esta URL como una URL de exclusión o de cancelación de suscripción.

![](assets/des_link_tracking_type.png)

También puede desactivar o activar el seguimiento para cada URL.

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).

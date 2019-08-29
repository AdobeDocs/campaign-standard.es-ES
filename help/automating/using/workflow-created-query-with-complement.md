---
title: '" Uso del flujo de trabajo: Creación de entregas con un complemento "'
seo-title: '" Uso del flujo de trabajo: Creación de entregas con un complemento "'
description: '" Uso del flujo de trabajo: Creación de entregas con un complemento "'
seo-description: '" Uso del flujo de trabajo: Creación de entregas con un complemento "'
page-status-flag: no activado nunca
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: flujo de trabajo, uso de mayúsculas y minúsculas, segmentación
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# Uso del flujo de trabajo: Creación de entregas con un complemento {#deliveries-with-complement}

Puede enviar un correo electrónico a los clientes: Una para clientes creados hace menos de un año, una para clientes creados hace más de un año.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades del flujo de trabajo y haga clic **[!UICONTROL Create]** en.

## Crear una actividad de consulta {#create-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]**![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

## Crear una actividad de segmentación {#create-a-segmentation-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Segmentation]** actividad y haga doble clic en ella.
1. Pase el ratón sobre el segmento y luego haga clic ![](assets/edit_darkgrey-24px.png) para dirigirse a los clientes que agregaron este año en la base de datos.
1. Arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL Created]** con el tipo **[!UICONTROL Relative]** de filtro.
1. Cambie el **[!UICONTROL Level of precision]** valor y **[!UICONTROL Year]** seleccione **[!UICONTROL This year]**.
1. Haga clic **[!UICONTROL Confirm]** dos veces.
1. En **[!UICONTROL Advanced Options]**, asegúrese **[!UICONTROL Generate complement]** de crear un segmento dirigido a los destinatarios restantes.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Para observar la estructura de la regla, haga clic **[!UICONTROL Advanced Mode]** en.

## Creación de una entrega por correo electrónico {#create-an-email-delivery}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte una entrega por correo electrónico después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Single send email]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione una plantilla de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Para crear la presentación del correo electrónico, haga clic **[!UICONTROL Email Designer]** en.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas de cada entrega.
1. Haga clic para **[!UICONTROL Preview]** comprobar el diseño.
1. Click **[!UICONTROL Save]**.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

**Temas relacionados:**

* [Consulta](../../automating/using/query.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Envío por correo electrónico](../../automating/using/email-delivery.md)

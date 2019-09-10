---
title: '" Uso del flujo de trabajo: Segmentación en la ubicación "'
seo-title: '" Uso del flujo de trabajo: Segmentación en la ubicación "'
description: '" Uso del flujo de trabajo: Segmentación en la ubicación "'
seo-description: '" Uso del flujo de trabajo: Segmentación en la ubicación "'
page-status-flag: no activado nunca
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: 'flujo de trabajo, caso de uso, consulta, segmentación, entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Uso del flujo de trabajo: Segmentación en ubicación {#segmentation-on-location}

Puede enviar un correo electrónico de objetivo a los clientes con ofertas en sus tiendas locales.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades del flujo de trabajo y haga clic **[!UICONTROL Create]** en.

## Seleccionar destinatarios contactables por correo electrónico{#selecting-recipients-contactable-via-email}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]**![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Haga clic **[!UICONTROL Confirm]** dos veces.

![](assets/wf-complement-query.png)

## Creación de una actividad de segmentación{#creating-a-segmentation-activity}

1. Arrastre y suelte una **[!UICONTROL Segmentation]** actividad y haga doble clic en ella.
1. Haga clic en segmento y luego abra transición para dirigirse a personas de la primera ciudad. Aquí Boston.
1. Arrastre y suelte **[!UICONTROL Location]** y seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** y el valor **[!UICONTROL Boston]**.
Nota: Para llegar a todas las personas que ingresaron a Boston, sin relación con el caso desmarque la opción que distingue entre mayúsculas y minúsculas.
1. Click **[!UICONTROL Confirm]**.
1. En **[!UICONTROL List of outbound segments]**, haga clic **[!UICONTROL Add an element]** y haga clic ![](assets/edit_darkgrey-24px.png) para crear un segmento dirigido a personas de la segunda ciudad. Aquí Chicago.
1. Arrastre y suelte **[!UICONTROL Location]** , seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** e introduzca **[!UICONTROL Chicago]** el valor en.
1. Para llegar a todas las personas que ingresaron a chicago, sin relación con el caso desmarque la opción que distingue entre mayúsculas y minúsculas.
1. Click **[!UICONTROL Confirm]**.

## Creación de una entrega por correo electrónico{#creating-an-email-delivery}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte un **[!UICONTROL Email Delivery]** segmento después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple email]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione una plantilla de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Para crear la presentación del correo electrónico, haga clic **[!UICONTROL Email Designer]** en.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas de cada ubicación.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

1. Haga clic para **[!UICONTROL Preview]** comprobar el diseño.
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Temas relacionados:**

* [Actividad de consulta](../../automating/using/query.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Envío por correo electrónico](../../automating/using/email-delivery.md)

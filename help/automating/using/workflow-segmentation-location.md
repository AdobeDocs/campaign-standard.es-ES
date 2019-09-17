---
title: '"Caso de uso del flujo de trabajo: Segmentación en la ubicación"'
seo-title: '"Caso de uso del flujo de trabajo: Segmentación en la ubicación"'
description: '"Caso de uso del flujo de trabajo: Segmentación en la ubicación"'
seo-description: '"Caso de uso del flujo de trabajo: Segmentación en la ubicación"'
page-status-flag: nunca activado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'flujo de trabajo,caso de uso,consulta,segmentación,entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# Caso de uso del flujo de trabajo: Segmentación en la ubicación {#segmentation-on-location}

Puede enviar un correo electrónico de objetivo a los clientes con ofertas en sus tiendas locales.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Selección de los destinatarios a los que se puede contactar por correo electrónico{#selecting-recipients-contactable-via-email}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]** objeto ![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Haga clic **[!UICONTROL Confirm]** dos veces.

![](assets/wf-complement-query.png)

## Creación de una actividad de segmentación{#creating-a-segmentation-activity}

1. Arrastre y suelte una **[!UICONTROL Segmentation]** actividad y haga doble clic en ella.
1. Haga clic en el segmento y luego abra la transición para dirigirse a personas de la primera ciudad. Aquí Boston.
1. Arrastre y suelte **[!UICONTROL Location]** y seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** y el valor **[!UICONTROL Boston]**.
Nota: Para llegar a todas las personas que entraron en Boston, sin tener en cuenta el caso, desactive la opción que distingue mayúsculas de minúsculas.
1. Click **[!UICONTROL Confirm]**.
1. En **[!UICONTROL List of outbound segments]**, haga clic **[!UICONTROL Add an element]** y haga clic en ![](assets/edit_darkgrey-24px.png) para crear un segmento dirigido a personas de la segunda ciudad. Aquí Chicago.
1. Arrastre y suelte **[!UICONTROL Location]** y seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** e introduzca **[!UICONTROL Chicago]** el valor.
1. Para llegar a todas las personas que ingresaron a Chicago, sin importar el caso, desmarque la opción que distingue mayúsculas de minúsculas.
1. Click **[!UICONTROL Confirm]**.

## Creación de un envío de correo electrónico{#creating-an-email-delivery}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte una **[!UICONTROL Email Delivery]** vez finalizado cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas para cada ubicación.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Temas relacionados:**

* [Actividad de consulta](../../automating/using/query.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Envío de correo electrónico](../../automating/using/email-delivery.md)

---
title: '" Uso del flujo de trabajo: Retargeting Non-openers "'
seo-title: '" Uso del flujo de trabajo: Retargeting Non-openers "'
description: '" Uso del flujo de trabajo: Retargeting Non-openers "'
seo-description: '" Uso del flujo de trabajo: Retargeting Non-openers "'
page-status-flag: no activado nunca
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: 'flujo de trabajo, caso de uso, consulta, espera, entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# Uso del flujo de trabajo: Volver a configurar el flujo de trabajo envío de una nueva entrega a no abiertos{#retargeting-delivery-to-non-openers}

Puede enviar un correo electrónico a los clientes y, a continuación, enviar un sms a los que no hayan abierto el correo.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades del flujo de trabajo y haga clic **[!UICONTROL Create]** en.

## Creación de una actividad de consulta{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]**![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creación de una entrega por correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte una publicación[!UICONTROL Email delivery]de correo electrónico**** después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple email]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione **[!UICONTROL Add an outbound transition without the population]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione una plantilla de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Para crear la presentación del correo electrónico, haga clic **[!UICONTROL Using the Email Designer]** en.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas de cada ubicación. Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. Haga clic para **[!UICONTROL Preview]** comprobar el diseño.
1. Click **[!UICONTROL Save]**.

## Segmentación de usuarios no abiertos en una actividad de consulta{#targeting-non-openers-in-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arrastre y suelte un **[!UICONTROL Wait activity]**![](assets/wait.png).
1. En **[!UICONTROL Duration]**, haga clic ![](assets/duration-icon.png) en y seleccione un día.
1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]**![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Tracking Logs]** y con el operador **[!UICONTROL exists]**.
1. En **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL delivery]** con el operador **[!UICONTROL is equal to]** y seleccione la entrega como valor.
1. En **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL type]** y verifique **[!UICONTROL Open]** como valor.
1. Seleccione el operador entre reglas como **[!UICONTROL except]**.
1. Click **[!UICONTROL Confirm]**.

## Creación de un envío de SMS{#creating-a-sms-delivery}

1. Arrastre y suelte un envío SMS después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple sms]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione una plantilla SMS y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades sms y haga clic **[!UICONTROL Next]** en.
1. Para crear la presentación del sms, haga clic **[!UICONTROL Email Designer]** en.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su SMS con ofertas específicas de cada ubicación.
Para obtener más información, consulte [Diseño de un sms](../../channels/using/creating-an-sms-message.md).
1. Haga clic para **[!UICONTROL Preview]** comprobar el diseño.
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Temas relacionados:**

* [Consulta](../../automating/using/query.md)
* [Envío SMS](../../automating/using/sms-delivery.md)
* [Envío por correo electrónico](../../automating/using/email-delivery.md)
* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

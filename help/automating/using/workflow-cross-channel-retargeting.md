---
title: '"Caso de uso del flujo de trabajo: No abridores de redireccionamiento"'
seo-title: '"Caso de uso del flujo de trabajo: No abridores de redireccionamiento"'
description: '"Caso de uso del flujo de trabajo: No abridores de redireccionamiento"'
seo-description: '"Caso de uso del flujo de trabajo: No abridores de redireccionamiento"'
page-status-flag: nunca activado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'flujo de trabajo,caso de uso,consulta,espera,entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# Caso de uso del flujo de trabajo: Flujo de trabajo de redireccionamiento que envía una nueva entrega a no abridores{#retargeting-delivery-to-non-openers}

Puede enviar un correo electrónico a los clientes y luego un mensaje de correo electrónico a los que no lo abrieron.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creación de una actividad de consulta{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]** objeto ![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creación de un envío de correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte un **[!UICONTROL Email delivery]** después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione **[!UICONTROL Add an outbound transition without the population]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Using the Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas para cada ubicación.Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Click **[!UICONTROL Save]**.

## Establecimiento de objetivos para los no abridores en una actividad de consulta{#targeting-non-openers-in-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arrastre y suelte un **[!UICONTROL Wait activity]** objeto ![](assets/wait.png).
1. En **[!UICONTROL Duration]**, haga clic en ![](assets/duration-icon.png) y seleccione un día.
1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]** objeto ![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Tracking Logs]** y con el operador **[!UICONTROL exists]**.
1. En **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL delivery]** con el operador **[!UICONTROL is equal to]** y seleccione la entrega como valor.
1. En **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL type]** y marque **[!UICONTROL Open]** como valor.
1. Seleccione el operador entre reglas como **[!UICONTROL except]**.
1. Click **[!UICONTROL Confirm]**.

## Creación de una entrega de sms{#creating-a-sms-delivery}

1. Arrastre y suelte un envío de SMS después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Simple sms]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla sms y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de sms y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño de los mensajes de texto, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice sus SMS con ofertas específicas para cada ubicación.
Para obtener más información, consulte [Diseño de un sms](../../channels/using/creating-an-sms-message.md).
1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Temas relacionados:**

* [Consulta](../../automating/using/query.md)
* [Envío SMS](../../automating/using/sms-delivery.md)
* [Envío de correo electrónico](../../automating/using/email-delivery.md)
* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

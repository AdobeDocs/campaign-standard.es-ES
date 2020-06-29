---
title: Redirección de receptores que no abran el correo
description: Este caso de uso muestra cómo volver a dirigirse a los no abridores.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---


# Flujo de trabajo de redireccionamiento que envía un nuevo envío a los no abridores{#retargeting-delivery-to-non-openers}

Puede enviar un correo electrónico a los clientes y luego un mensaje de correo electrónico a los que no lo abrieron.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creating a query activity{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) .
1. Haga clic con el Doble en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no ]**.
1. Haga clic **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creación de una entrega de correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte un envío [de](../../automating/using/email-delivery.md) correo electrónico después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Simple email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione **[!UICONTROL Add an outbound transition without the population]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Using the Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas de cada ubicación.Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic **[!UICONTROL Save]**.

## Establecimiento de objetivos para los usuarios que no abren en una actividad de consulta{#targeting-non-openers-in-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arrastre y suelte una actividad de [espera](../../automating/using/wait.md) .
1. En **[!UICONTROL Duration]**, haga clic en ![](assets/duration-icon.png) y seleccione un día.
1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Query activity]**.
1. Haga clic con el Doble en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Tracking Logs]** y con el operador **[!UICONTROL exists]**.
1. En **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL delivery]** con el operador **[!UICONTROL is equal to]** y seleccione el envío como valor.
1. En **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL type]** y marque **[!UICONTROL Open]** como valor.
1. Seleccione el operador entre reglas como **[!UICONTROL except]**.
1. Haga clic **[!UICONTROL Confirm]**.

## Creating a sms delivery{#creating-a-sms-delivery}

1. Arrastre y suelte un envío sms después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Simple sms]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla sms y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de sms y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño de los mensajes de texto, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice sus sms con ofertas específicas de cada ubicación.
Para obtener más información, consulte la sección [Diseño de un sms](../../channels/using/creating-an-sms-message.md) .
1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Temas relacionados:**

* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

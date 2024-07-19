---
title: Redirección de receptores que no abran el correo
description: Este caso de uso muestra cómo volver a direccionar los elementos que no son abridores.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---

# Flujo de trabajo de redireccionamiento que envía una nueva entrega a receptores que no abran el mensaje{#retargeting-delivery-to-non-openers}

Puede enviar un correo electrónico a los clientes y, a continuación, un SMS a aquellos que no lo hayan abierto.

1. En **[!UICONTROL Marketing Activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creación de una actividad de consulta{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Haga clic en **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creación de una entrega de correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte un [envío de correo electrónico](../../automating/using/email-delivery.md) después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Simple email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione **[!UICONTROL Add an outbound transition without the population]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Using the Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas para cada ubicación. Para obtener más información, consulte [diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Haga clic en **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic en **[!UICONTROL Save]**.

## Segmentación de elementos que no se abren en una actividad de consulta{#targeting-non-openers-in-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arrastre y suelte una actividad de [Espera](../../automating/using/wait.md).
1. En **[!UICONTROL Duration]**, haga clic en ![](assets/duration-icon.png) y seleccione un día.
1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Query activity]**.
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Tracking Logs]** y con el operador **[!UICONTROL exists]**.
1. En **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL delivery]** con el operador **[!UICONTROL is equal to]** y seleccione la entrega como valor.
1. En **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastre y suelte **[!UICONTROL type]** y marque **[!UICONTROL Open]** como valor.
1. Seleccione el operador entre reglas como **[!UICONTROL except]**.
1. Haga clic en **[!UICONTROL Confirm]**.

## Creación de una entrega de SMS{#creating-a-sms-delivery}

1. Arrastre y suelte un envío SMS después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Simple sms]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de SMS y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del SMS y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño de su sms, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice sus SMS con ofertas específicas para cada ubicación.
Para obtener más información, consulte la sección [Diseño de un sms](../../channels/using/creating-an-sms-message.md).
1. Haga clic en **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic en **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Temas relacionados:**

* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

---
title: Creación de un envío semanal
description: Este caso de uso muestra cómo crear un envío semanal.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 5%

---


# Creación de un envío de correo electrónico todos los martes{#creating-email-every-tuesday}

Puede enviar un correo electrónico todos los martes a todos los clientes para Ofertas especiales.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creación de una actividad Planificador{#creating-a-scheduler-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arrastre y suelte una actividad de [Planificador](../../automating/using/scheduler.md) .
1. Haga clic con el Doble en la actividad.
1. Configure la ejecución del envío.
1. En **[!UICONTROL Execution frequency]**, seleccione **[!UICONTROL Weekly]**.
1. Seleccione un **[!UICONTROL Time]** y un **[!UICONTROL Repetition frequency]** para sus envíos.
1. En **[!UICONTROL Days of the week]**, seleccione **[!UICONTROL Tuesday]**.
1. Especifique un **[!UICONTROL Start]** y un **[!UICONTROL Expiration]** parámetro para el flujo de trabajo.
1. Confirme la actividad y guarde el flujo de trabajo.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para inicio del flujo de trabajo en un **[!UICONTROL Time Zone]** campo específico, en la **[!UICONTROL Execution options]** ficha , configure el huso horario del Planificador en el campo Huso horario. De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

## Creating a Query activity{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, para seleccionar destinatarios, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) y haga clic en ella con el botón de doble.
1. En **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, arrastre y suelte **[!UICONTROL Email]**.
1. Seleccione **[!UICONTROL is not empty]** como operador.
1. En **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**, agregue perfiles y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL No]**.
1. Haga clic **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Recurring email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Use Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice el correo electrónico mediante campos y vínculos.
1. Haga clic **[!UICONTROL Save]**.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Temas relacionados:**

* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

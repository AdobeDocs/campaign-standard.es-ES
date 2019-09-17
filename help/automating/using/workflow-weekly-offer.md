---
title: '"Caso de uso del flujo de trabajo: Creación de un envío semanal"'
seo-title: '"Caso de uso del flujo de trabajo: Creación de un envío semanal"'
description: '"Caso de uso del flujo de trabajo: Creación de un envío semanal"'
seo-description: '"Caso de uso del flujo de trabajo: Creación de un envío semanal"'
page-status-flag: nunca activado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: 'execute-activity '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: flujo de trabajo,caso de uso,consulta,entrega,programador
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# Caso de uso de flujo de trabajo: Crear un envío de correo electrónico todos los martes{#creating-email-every-tuesday}

Puede enviar un correo electrónico todos los martes a todos los clientes para ofertas especiales.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creación de una actividad de Programador{#creating-a-scheduler-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arrastre y suelte una **[!UICONTROL Scheduler activity]**.
1. Haga doble clic en la actividad.
1. Configure la ejecución de la entrega.
1. En **[!UICONTROL Execution frequency]**, seleccione **[!UICONTROL Weekly]**.
1. Seleccione un **[!UICONTROL Time]** y un **[!UICONTROL Repetition frequency]** para los envíos.
1. En **[!UICONTROL Days of the week]**, seleccione **[!UICONTROL Tuesday]**.
1. Especifique un **[!UICONTROL Start]** y un **[!UICONTROL Expiration]** parámetro para el flujo de trabajo.
1. Confirme la actividad y guarde el flujo de trabajo.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para iniciar el flujo de trabajo en un elemento específico **[!UICONTROL Time Zone]**, en la ficha **[!UICONTROL Execution options]**, configure el huso horario del programador en el campo Huso horario.

## Creación de una actividad de consulta{#creating-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, para seleccionar destinatarios, arrastre y suelte una **[!UICONTROL query]** actividad y haga doble clic en ella.
1. En **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**, arrastre y suelte **[!UICONTROL Email]**.
1. Seleccione **[!UICONTROL is not empty]** como operador.
1. En **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**, agregue perfiles y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL No]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creación de un envío de correo electrónico{#creating-an-email-delivery}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte una **[!UICONTROL Email delivery]**.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Recurring email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Use Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice el correo electrónico mediante campos y vínculos.
1. Click **[!UICONTROL Save]**.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Temas relacionados:**

* [Actividad de consulta](../..//automating/using/query.md)
* [Actividad del programador](../..//automating/using/scheduler.md)
* [Envío de correo electrónico](../..//automating/using/email-delivery.md)
* [Canal de correo electrónico](../..//channels/using/creating-an-email.md)

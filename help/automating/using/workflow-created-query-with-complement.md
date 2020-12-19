---
solution: Campaign Standard
product: campaign
title: Creación de entregas con un complemento
description: Este caso de uso muestra cómo crear envíos con un complemento.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# Creación de entregas con un complemento {#deliveries-with-complement}

Puede enviar un correo electrónico a los clientes: uno para clientes creados hace menos de un año, otro para clientes creados hace más de un año.

1. En **[!UICONTROL Marketing Activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Crear una actividad de Consulta {#create-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Haga clic en **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Crear una actividad de segmentación {#create-a-segmentation-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una [actividad de segmentación](../../automating/using/segmentation.md) y haga clic en ella con el doble.
1. Pase el ratón sobre el segmento y haga clic en ![](assets/edit_darkgrey-24px.png) para agregar clientes de destinatario este año a la base de datos.
1. Arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL Created]** con el tipo de filtro **[!UICONTROL Relative]**.
1. Cambie **[!UICONTROL Level of precision]** a **[!UICONTROL Year]** y seleccione **[!UICONTROL This year]**.
1. Haga clic en **[!UICONTROL Confirm]** dos veces.
1. En **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para crear un segmento dirigido a los destinatarios restantes.
1. Haga clic **[!UICONTROL Confirm]**.
1. Haga clic **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar la estructura de la regla, haga clic en **[!UICONTROL Advanced Mode]**.

## Creación de una entrega de correo electrónico {#create-an-email-delivery}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad [envío de correo electrónico](../../automating/using/email-delivery.md) después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Single send email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas de cada envío.
1. Haga clic en **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic en **[!UICONTROL Save]**.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

---
title: Creación de entregas con un complemento
description: Este caso de uso muestra cómo crear envíos con un complemento.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# Creación de entregas con un complemento {#deliveries-with-complement}

Puede enviar un correo electrónico a los clientes: uno para clientes creados hace menos de un año, otro para clientes creados hace más de un año.

1. En **[!UICONTROL Marketing Activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Create a Query activity {#create-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md).
1. Haga doble clic en la actividad.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no]**.
1. Haga clic en **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Create a Segmentation activity {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. Pase el ratón por encima del segmento y luego haga clic en ![](assets/edit_darkgrey-24px.png) los clientes de destinatario agregados este año en la base de datos.
1. Drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL Created]** with the filter type **[!UICONTROL Relative]**.
1. Change the **[!UICONTROL Level of precision]** to **[!UICONTROL Year]** and select **[!UICONTROL This year]**.
1. Haga clic en **[!UICONTROL Confirm]** dos veces.
1. En **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para crear un segmento dirigido a los destinatarios restantes.
1. Haga clic **[!UICONTROL Confirm]**.
1. Haga clic **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar la estructura de la regla, haga clic en **[!UICONTROL Advanced Mode]**.

## Creación de una entrega de correo electrónico {#create-an-email-delivery}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico después de cada segmento.
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

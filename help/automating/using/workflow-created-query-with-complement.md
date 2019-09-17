---
title: '"Caso de uso del flujo de trabajo: Creación de entregas con un complemento"'
seo-title: '"Caso de uso del flujo de trabajo: Creación de entregas con un complemento"'
description: '"Caso de uso del flujo de trabajo: Creación de entregas con un complemento"'
seo-description: '"Caso de uso del flujo de trabajo: Creación de entregas con un complemento"'
page-status-flag: nunca activado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: flujo de trabajo,caso de uso,segmentación
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# Caso de uso del flujo de trabajo: Creación de entregas con un complemento {#deliveries-with-complement}

Puede enviar un correo electrónico a los clientes: uno para clientes creados hace menos de un año, otro para clientes creados hace más de un año.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Crear una actividad de consulta {#create-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte un **[!UICONTROL Query activity]** objeto ![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Crear una actividad de segmentación {#create-a-segmentation-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Segmentation]** actividad y haga doble clic en ella.
1. Pase el ratón sobre el segmento y haga clic en ![](assets/edit_darkgrey-24px.png) para dirigirse a los clientes agregados este año en la base de datos.
1. Arrastre y suelte **[!UICONTROL Profiles]** y seleccione **[!UICONTROL Created]** con el tipo de filtro **[!UICONTROL Relative]**.
1. Cambie **[!UICONTROL Level of precision]** a **[!UICONTROL Year]** y seleccione **[!UICONTROL This year]**.
1. Haga clic **[!UICONTROL Confirm]** dos veces.
1. En **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para crear un segmento dirigido a los destinatarios restantes.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar la estructura de la regla, haga clic en **[!UICONTROL Advanced Mode]**.

## Creación de un envío de correo electrónico {#create-an-email-delivery}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte un envío de correo electrónico después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Single send email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas para cada entrega.
1. Haga clic **[!UICONTROL Preview]** para comprobar el diseño.
1. Click **[!UICONTROL Save]**.

Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Temas relacionados:**

* [Consulta](../../automating/using/query.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Envío de correo electrónico](../../automating/using/email-delivery.md)

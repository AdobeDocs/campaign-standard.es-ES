---
title: Segmentación en la ubicación"
description: Este caso de uso muestra cómo realizar la segmentación en una ubicación.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,segmentation,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: feedc2f5-63da-44a5-b8f0-15afdfd47daa
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 80%

---

# Segmentación en la ubicación {#segmentation-on-location}

Puede enviar un correo electrónico de segmentación a los clientes con ofertas en sus tiendas locales.

1. En **[!UICONTROL Marketing Activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Selección de destinatarios contactables por correo electrónico{#selecting-recipients-contactable-via-email}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad [Consulta](../../automating/using/query.md) ![](assets/query.png).
1. Haga doble clic en la actividad.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL email]** con el operador **[!UICONTROL is not empty]**.
1. En **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profiles]** y seleccione el campo **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.
1. Haga clic en **[!UICONTROL Confirm]** dos veces.

![](assets/wf-complement-query.png)

## Creación de una actividad de segmentación{#creating-a-segmentation-activity}

1. Arrastre y suelte una actividad [Segmentation](../../automating/using/segmentation.md) y haga doble clic en ella.
1. Haga clic en el segmento y luego abra la transición para dirigirse a las personas en la primera ciudad. Aquí Boston.
1. Arrastre y suelte **[!UICONTROL Location]** y seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** y el valor **[!UICONTROL Boston]**.
Nota: Para llegar a todas las personas introducidas en Boston, sin tener en cuenta las mayúsculas o minúsculas, desactive la opción que distingue mayúsculas de minúsculas.
1. Haga clic en **[!UICONTROL Confirm]**.
1. En **[!UICONTROL List of outbound segments]**, haga clic en **[!UICONTROL Add an element]** y haga clic en ![](assets/edit_darkgrey-24px.png) para crear un segmento dirigido a personas de la segunda ciudad. Aquí Chicago.
1. Arrastre y suelte **[!UICONTROL Location]** y seleccione **[!UICONTROL City]** con el operador **[!UICONTROL equals to]** e introduzca **[!UICONTROL Chicago]** en el valor.
1. Para llegar a todas las personas introducidas en Chicago, sin tener en cuenta el caso, desactive la opción que distingue mayúsculas de minúsculas.
1. Haga clic en **[!UICONTROL Confirm]**.

## Creación de una entrega de correo electrónico{#creating-an-email-delivery}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad de [envío de correo electrónico](../../automating/using/email-delivery.md) después de cada segmento.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Simple email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico con ofertas específicas para cada ubicación.

   Para obtener más información, consulte [diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Haga clic en **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic en **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

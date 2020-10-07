---
title: Creación de envíos en la fecha de creación del perfil
description: Este caso de uso muestra cómo crear envíos en la fecha de creación del perfil.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# Creación de envíos en la fecha de creación de los perfiles {#creation-date-query}

Puede enviar una oferta por correo electrónico en el aniversario de la creación de perfiles del cliente.

1. En **[!UICONTROL Marketing Activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

## Creación de una actividad de planificador {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. Haga doble clic en la actividad.
1. Configure la ejecución del envío.
1. En **[!UICONTROL Execution frequency]**, seleccione **[!UICONTROL Daily]**.
1. Seleccione un **[!UICONTROL Time]** y el orden **[!UICONTROL Repetition frequency]** de ejecución para el flujo de trabajo.
1. Seleccione una **[!UICONTROL Start]** fecha y **[!UICONTROL Expiration]** para el flujo de trabajo.
1. Confirme la actividad y guarde el flujo de trabajo.

>[!NOTE]
>
>To start your workflow at a specific time zone, in the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. De forma predeterminada, el huso horario seleccionado es el definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Creación de una actividad de consulta {#creating-a-query-activity}

1. To select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. Añada **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.

### Recuperación de perfiles creados el mismo día de la ejecución {#retriving-profiles-created-on-the-same-day}

1. En **[!UICONTROL Profile]**, arrastre y suelte el **[!UICONTROL Created]** campo. y haga clic en **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. En el **[!UICONTROL list of functions]**, haga clic con el doble **[!UICONTROL Day]** desde el **[!UICONTROL Date]** nodo.
1. A continuación, inserte el campo **[!UICONTROL Created]** como argumento.
1. Select **[!UICONTROL equals to (=)]** as the operator.
1. En Valor, seleccione **[!UICONTROL Day]** en el **[!UICONTROL Date]** nodo de la **[!UICONTROL List of functions]**.
1. Inserte la **[!UICONTROL GetDate()]** función como argumento.

Se recuperaron los perfiles cuyo día de creación es igual al día actual.

Debería terminar con:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Haga clic en **[!UICONTROL Confirm]**.

### Recuperación de perfiles creados el mismo mes del mes de ejecución{#retriving-profiles-created-on-the-same-month}

1. En el **[!UICONTROL Query]** editor, seleccione la primera consulta y duplicado.
1. Abra el duplicado.
1. Reemplazar **[!UICONTROL Day]** por **[!UICONTROL Month]** en la consulta.
1. Haga clic en **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Debería terminar con esto:

``` Month(@created) = Month(GetDate()) ```

La consulta final muestra:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creación de una entrega de correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Recurring email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Email Designer]**.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice el correo electrónico mediante campos y vínculos.
Para obtener más información, consulte [diseño de un correo electrónico](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Haga clic en **[!UICONTROL Preview]** para comprobar el diseño.
1. Haga clic en **[!UICONTROL Save]**.

**Temas relacionados:**

* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

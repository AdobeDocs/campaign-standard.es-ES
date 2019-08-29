---
title: '" Uso del flujo de trabajo: Creación de entregas en la fecha de creación del perfil "'
seo-title: '" Uso del flujo de trabajo: Creación de entregas en la fecha de creación del perfil "'
description: '" Uso del flujo de trabajo: Creación de entregas en la fecha de creación del perfil "'
seo-description: '" Uso del flujo de trabajo: Creación de entregas en la fecha de creación del perfil "'
page-status-flag: no activado nunca
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: 'ejecución actividades '
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: flujo de trabajo, caso de uso, consulta
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Caso de uso del flujo de trabajo: Crear entregas en la fecha de creación de perfiles {#creation-date-query}

Puede enviar una oferta por correo electrónico en el aniversario de la creación de perfiles del cliente.

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades del flujo de trabajo y haga clic **[!UICONTROL Create]** en.

## Creación de una actividad de programador {#creating-a-scheduler-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arrastre y suelte un **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. Haga doble clic en la actividad.
1. Configurar la ejecución de la entrega.
1. En **[!UICONTROL Execution frequency]**, seleccione **[!UICONTROL Daily]**.
1. Seleccione un **[!UICONTROL Time]** y el **[!UICONTROL Repetition frequency]** de ejecución para el flujo de trabajo.
1. Seleccione una **[!UICONTROL Start]** fecha y **[!UICONTROL Expiration]** el flujo de trabajo.

>[!NOTE]
>
>Para iniciar el flujo de trabajo en una zona horaria específica, en **[!UICONTROL Execution options]** la ficha, configure el huso horario del programador en **[!UICONTROL Time zone]** el campo.

![](assets/time_zone.png)

1. Confirme su actividad y guarde el flujo de trabajo.

## Creación de una actividad de consulta {#creating-a-query-activity}

1. Para seleccionar destinatarios, arrastre y suelte un **[!UICONTROL Query activity]** elemento y haga doble clic en él.
1. Agregue **[!UICONTROL Profiles]** y seleccione **[!UICONTROL no longer contact by email]** con el valor **[!UICONTROL no]**.

### Recuperación de perfiles creados el mismo día que el día de ejecución {#retriving-profiles-created-on-the-same-day}

1. En **[!UICONTROL Profile]**, arrastre y suelte el **[!UICONTROL Created]** campo. y haga clic **[!UICONTROL Advanced Mode]**en.
   ![](assets/advanced_mode.png)
1. En **[!UICONTROL list of functions]**, haga doble clic **[!UICONTROL Day]** desde el **[!UICONTROL Date]** nodo.
1. A continuación, inserte el campo **[!UICONTROL Created]** como argumento.
1. Seleccione **[!UICONTROL equals to (=)]** como operador.
1. En Valor, seleccione **[!UICONTROL Day]** del **[!UICONTROL Date]** nodo del **[!UICONTROL List of functions]**.
1. Inserte la **[!UICONTROL GetDate()]** función como argumento.

Recuperó los perfiles que el día de creación es igual al día actual.

Debe terminar con:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### Recuperación de perfiles creados el mismo mes que el mes de ejecución{#retriving-profiles-created-on-the-same-month}

1. En **[!UICONTROL Query]** el editor, seleccione la primera consulta y duplíquela.
1. Abra el duplicado.
1. Reemplace **[!UICONTROL Day]** por **[!UICONTROL Month]** en la consulta.
Debe finalizar con esto:

``` Month(@created) = Month(GetDate()) ```

1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Se muestra la consulta final:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creación de una entrega por correo electrónico{#creating-an-email-delivery}

1. Arrastre y suelte una entrega por correo electrónico.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) editar.
1. Seleccione **[!UICONTROL Recurring email]** y haga clic **[!UICONTROL Next]** en.
1. Seleccione una plantilla de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Introduzca las propiedades de correo electrónico y haga clic **[!UICONTROL Next]** en.
1. Para crear la presentación del correo electrónico, haga clic **[!UICONTROL Email Designer]** en.
1. Inserte elementos o seleccione una plantilla existente.
1. Personalice su correo electrónico mediante campos y vínculos.
Para obtener más información, consulte [Diseño de un correo electrónico](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. Haga clic para **[!UICONTROL Preview]** comprobar el diseño.
1. Click **[!UICONTROL Save]**.

**Temas relacionados:**

* [Consulta](../../automating/using/query.md)
* [Programador](../../automating/using/scheduler.md)
* [Envío por correo electrónico](../../automating/using/email-delivery.md)
* [Canal de correo electrónico](../../channels/using/creating-an-email.md)

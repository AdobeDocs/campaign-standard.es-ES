---
title: Planificador
description: La actividad Programador le permite programar cuándo se inicia un flujo de trabajo o una actividad.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 41ba6fa44807541dd749f4effca44ae2b4d147ae

---


# Planificador{#scheduler}

## Descripción {#description}

![](assets/scheduler.png)

La **[!UICONTROL Scheduler]**actividad le permite programar cuándo se inicia un flujo de trabajo o una actividad.

## Contexto de uso {#context-of-use}

The **[!UICONTROL Scheduler]**activity should be considered as a scheduled start. The activity positioning rules within the chart are the same as for the**[!UICONTROL Start]** activity. Esta actividad no debe tener una transición entrante.

Al crear el flujo de trabajo, utilice solo una **[!UICONTROL Scheduler]**actividad por rama y recuerde establecer un huso horario. Esto le permite iniciar el flujo de trabajo en un huso horario específico; de lo contrario, el flujo de trabajo se ejecutará en el huso horario definido en las propiedades del flujo de trabajo (consulte[Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>La duración **[!UICONTROL Repetition frequency]**de la actividad no puede ser inferior a 10 minutos. Esto significa que un flujo de trabajo no se puede ejecutar automáticamente más de una vez cada 10 minutos.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Scheduler]**actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Especifique el **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**:: el flujo de trabajo se ejecuta una sola vez.
   * **[!UICONTROL Several times a day]**:: el flujo de trabajo se ejecuta regularmente varias veces al día. Puede configurar ejecuciones en momentos específicos o de forma periódica.
   * **[!UICONTROL Daily]**:: el flujo de trabajo se ejecuta a una hora específica, una vez al día.
   * **[!UICONTROL Weekly]**:: el flujo de trabajo se ejecuta en un momento determinado, una o varias veces por semana.
   * **[!UICONTROL Monthly]**:: el flujo de trabajo se ejecuta en un momento determinado, una o varias veces al mes. Puede seleccionar meses cuando necesite que se ejecute el flujo de trabajo. También puede configurar ejecuciones en un día de semana del mes especificado, como el segundo martes del mes.
   * **[!UICONTROL Yearly]**:: el flujo de trabajo se ejecuta en un momento determinado, una o varias veces al año.

1. Defina los detalles de ejecución según la frecuencia seleccionada. Los campos de detalle pueden variar según la frecuencia utilizada (tiempo, frecuencia de repetición, días especificados, etc.).

   >[!NOTE]
   >
   >El **[!UICONTROL Repetition frequency]**campo permite reducir el espacio de tiempo en que se activa el flujo de trabajo. Por ejemplo, si selecciona un período de ejecución diario y la frecuencia de repetición se establece en** 2 **(días), el flujo de trabajo se activará cada dos días. No puede ser inferior a 10 minutos. Si la frecuencia de repetición está establecida en** 0 **(también el valor predeterminado), esta opción no se tiene en cuenta y el flujo de trabajo se ejecutará según la frecuencia de ejecución especificada.

1. Especifique cuándo caducará la ejecución:

   * **[!UICONTROL Never]**:: el flujo de trabajo se ejecutará según la frecuencia especificada, sin límites de tiempo ni número de iteraciones.
   * **[!UICONTROL After a certain number of iterations]**:: el flujo de trabajo se ejecutará según la frecuencia especificada, hasta que se alcance el límite de** X **. Por lo tanto,**[!UICONTROL Number of iterations]** será necesario especificar el valor.
   * **[!UICONTROL On a specific date]**:: el flujo de trabajo se ejecutará según la frecuencia especificada, hasta una fecha específica. Por lo tanto, será necesario especificar el plazo de ejecución.

1. Haga clic en **[!UICONTROL Preview next executions]**para comprobar la programación de las siguientes diez ejecuciones del flujo de trabajo.

1. En la **[!UICONTROL Execution options]**ficha, configure el huso horario del programador en el**[!UICONTROL Time zone]** campo.

   Para obtener más información sobre el envío en función del huso horario del destinatario, consulte esta [sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) o este [ejemplo](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) de un flujo de trabajo recurrente.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

En el ejemplo siguiente, la actividad se configura de modo que inicie el flujo de trabajo semanalmente, todos los lunes a las 7 de la mañana, durante un período de tiempo indeterminado.

![](assets/wkf_scheduler_example.png)


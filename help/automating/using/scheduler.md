---
title: Planificador
description: La actividad Planificador le permite programar cuándo se inicia un flujo de trabajo o una actividad.
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
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 97%

---


# Planificador{#scheduler}

## Descripción {#description}

![](assets/scheduler.png)

La actividad **[!UICONTROL Scheduler]** le permite programar cuándo se inicia un flujo de trabajo o una actividad.

## Contexto de uso {#context-of-use}

La actividad del **[!UICONTROL Scheduler]** debe considerarse como un inicio programado. Las reglas de colocación de actividad dentro del gráfico son las mismas que para la actividad **[!UICONTROL Start]**. Esta actividad no debe tener una transición entrante.

Al crear el flujo de trabajo, utilice solamente una actividad **[!UICONTROL Scheduler]** por rama y recuerde definir el huso horario. Esto le permite iniciar el flujo de trabajo en un huso horario específico; de lo contrario, el flujo de trabajo se ejecutará en el huso horario definido en las propiedades del flujo de trabajo (consulte [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>La **[!UICONTROL Repetition frequency]** de la actividad no puede ser inferior a 10 minutos. Esto significa que un flujo de trabajo no se puede ejecutar automáticamente más de una vez cada 10 minutos.

**Temas relacionados:**

* [Caso de uso: Creación de envíos en la fecha de creación de perfiles](../../automating/using/workflow-creation-date-query.md)
* [Caso de uso: Creación de un envío de correo electrónico todos los martes](../../automating/using/workflow-weekly-offer.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Scheduler]** en su flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Especifique la **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: el flujo de trabajo se ejecuta una sola vez.
   * **[!UICONTROL Several times a day]**: el flujo de trabajo se ejecuta regularmente varias veces al día. Puede configurar ejecuciones en momentos específicos o de forma periódica.
   * **[!UICONTROL Daily]**: el flujo de trabajo se ejecuta a una hora específica una vez al día.
   * **[!UICONTROL Weekly]**: el flujo de trabajo se ejecuta en un momento determinado una o varias veces a la semana.
   * **[!UICONTROL Monthly]**: el flujo de trabajo se ejecuta en un momento determinado una o varias veces al mes. Puede seleccionar meses cuando necesite que se ejecute el flujo de trabajo. También puede configurar ejecuciones en un día de semana del mes específico, como el segundo martes de cada mes.
   * **[!UICONTROL Yearly]**: el flujo de trabajo se ejecuta en un momento determinado una o varias veces al año.

1. Defina los detalles de ejecución según la frecuencia seleccionada. Los campos de detalle pueden variar según la frecuencia utilizada (tiempo, frecuencia de repetición, días especificados, etc.).

   >[!NOTE]
   >
   >El campo **[!UICONTROL Repetition frequency]** le permite ampliar el espacio de tiempo de activación del flujo de trabajo. Por ejemplo, si selecciona un período de ejecución diario y define la frecuencia de repetición en **2** (días), el flujo de trabajo se activará cada dos días. No puede ser inferior a 10 minutos. Si la frecuencia de repetición está definida en **0** (valor predeterminado), esta opción no se tiene en cuenta y el flujo de trabajo se ejecutará según la frecuencia de ejecución especificada.

1. Especifique cuándo caduca la ejecución:

   * **[!UICONTROL Never]**: el flujo de trabajo se ejecutará según la frecuencia especificada, sin límites en el lapso de tiempo ni número de iteraciones.
   * **[!UICONTROL After a certain number of iterations]**: el flujo de trabajo se ejecutará según la frecuencia especificada, hasta que se alcance el límite de **X**. Por lo tanto, se debe especificar el valor del **[!UICONTROL Number of iterations]**.
   * **[!UICONTROL On a specific date]**: el flujo de trabajo se ejecutará según la frecuencia especificada, hasta una fecha específica. Por lo tanto, se debe especificar el valor de la fecha límite de ejecución.

1. Haga clic en **[!UICONTROL Preview next executions]** para comprobar la programación de las siguientes diez ejecuciones del flujo de trabajo.

1. En la pestaña **[!UICONTROL Execution options]**, configure el huso horario de Planificador en el campo **[!UICONTROL Time zone]**.

   Para obtener más información sobre la entrega de envíos en función del huso horario del destinatario, consulte esta [sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) o este [ejemplo](../../automating/using/recurring-push-notifications.md) de un flujo de trabajo recurrente.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

En el ejemplo siguiente, la actividad se configura de modo que se inicie el flujo de trabajo de forma semanal todos los lunes a las 07:00 h durante un tiempo indeterminado.

![](assets/wkf_scheduler_example.png)


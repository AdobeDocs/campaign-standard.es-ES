---
title: Señal externa
description: La actividad Señal externa activa un flujo de trabajo cuando se cumplen correctamente algunas condiciones en otro flujo de trabajo.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: a4fbd6b5-7cfb-44ad-bf3a-f3aabc122b77
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 96%

---

# Señal externa{#external-signal}

## Descripción {#description}

![](assets/signal.png)

La actividad **[!UICONTROL External signal]** desencadena un flujo de trabajo cuando algunas condiciones se cumplen correctamente en otro flujo de trabajo o desde una llamada a la API de REST.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL External signal]** se utiliza para organizar y orquestar diferentes procesos que forman parte del mismo recorrido del cliente a diferentes flujos de trabajo. Permite el inicio de un flujo de trabajo desde otro, lo que permite recorridos de clientes más complejos, mientras que se puede supervisar y reaccionar mejor en caso de problemas.

La actividad **[!UICONTROL External signal]** está diseñada para colocarse como la primera actividad de un flujo de trabajo. Se puede activar a partir de la actividad **[!UICONTROL End]** de otro flujo de trabajo o de una llamada de API de REST (para obtener más información, consulte la [documentación de la API](../../api/using/triggering-a-signal-activity.md)).

Al activarse, los parámetros externos se pueden definir y estar disponibles en las variables de eventos de flujo de trabajo. El proceso para llamar a un flujo de trabajo con parámetros externos se detalla en [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>La actividad no se puede activar con más frecuencia que cada 10 minutos.

Tenga en cuenta que una actividad de **[!UICONTROL External signal]** se puede activar desde varios eventos diferentes. En ese caso, la **[!UICONTROL External signal]** se activa en cuanto se ejecuta uno de los flujos de trabajo de origen o la llamada de API. No requiere que todos los flujos de trabajo de origen hayan finalizado.

**Temas relacionados**

* [Caso de uso: Actividad de señales externas e importación](../../automating/using/external-signal-data-import.md) de datos.
* [Caso de uso: Invocación de un flujo de trabajo para crear una audiencia a partir de un archivo utilizando parámetros externos](../../automating/using/use-case-calling-workflow.md)

## Configuración {#configuration}

Al configurar una señal externa, es importante configurar primero la actividad **[!UICONTROL External signal]** en el flujo de trabajo de destino. Una vez que se haya realizado esta configuración, la actividad **[!UICONTROL External signal]** de este flujo de trabajo está disponible para configurar la actividad **[!UICONTROL End]** del flujo de trabajo de origen.

1. Arrastre y suelte una actividad de **[!UICONTROL External signal]** en el flujo de trabajo de destino.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Edite la etiqueta de la actividad. Se necesita esta etiqueta para configurar el flujo de trabajo de origen que activa la **[!UICONTROL External signal]**.

   Si desea llamar al flujo de trabajo con parámetros, utilice el área **[!UICONTROL Parameters]** para declararlos. Para obtener más información, consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).

   ![](assets/external_signal_configuration.png)

1. Confirme la configuración de la actividad, añada cualquier otra actividad que necesite y guarde el flujo de trabajo.

   >[!NOTE]
   >
   >Si desea activar el flujo de trabajo de destino desde otro flujo de trabajo, siga los pasos siguientes. Si desea activar el flujo de trabajo de destino desde una llamada a la API de REST, consulte la [documentación de la API](../../api/using/triggering-a-signal-activity.md) para obtener más información.

1. Abra el flujo de trabajo de origen y seleccione una actividad de **[!UICONTROL End]**. Si no hay ninguna actividad de **[!UICONTROL End]** disponible, añada una tras la última actividad de una rama del flujo de trabajo.

   Algunas actividades no tienen ninguna transición de salida de forma predeterminada. Desde la pestaña **[!UICONTROL Properties]** de estas actividades, puede añadir una transición de salida.

   Por ejemplo, en una actividad de **[!UICONTROL Update data]**, vaya a la pestaña **[!UICONTROL Transitions]** y marque la opción **[!UICONTROL Add an outbound transition without the population]**. Esta opción permite añadir una transición que no contenga datos y que no consuma espacio innecesario en el sistema. Solo se utiliza para conectar la actividad **[!UICONTROL End]** adicional que activa el flujo de trabajo de destino.

   ![](assets/external_signal_empty_transition.png)

1. En la pestaña **[!UICONTROL External signal]** de la actividad **[!UICONTROL End]**, seleccione el flujo de trabajo de destino, así como la actividad **[!UICONTROL External signal]** que se debe activar en dicho flujo de trabajo.

   Cuando se establece una actividad de **[!UICONTROL End]** para activar otro flujo de trabajo, este se actualiza con un símbolo de señal adicional.

   Si desea llamar al flujo de trabajo con parámetros, utilice el área **[!UICONTROL Parameters and values]**. Para obtener más información, consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md).

   ![](assets/external_signal_end.png)

1. Guarde el flujo de trabajo de origen.

Una vez ejecutada la actividad **[!UICONTROL End]** del flujo de trabajo de origen o la llamada a la API de REST, el flujo de trabajo de destino se activa automáticamente desde la actividad **[!UICONTROL External signal]**.

>[!NOTE]
>
>El flujo de trabajo de destino debe iniciarse manualmente para poder activarse. Cuando se inicia, la **[!UICONTROL External activity]** se activa y espera la señal desde el flujo de trabajo de origen.

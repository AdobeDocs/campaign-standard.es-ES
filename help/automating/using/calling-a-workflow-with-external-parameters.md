---
solution: Campaign Standard
product: campaign
title: Información general
description: En esta sección se explica cómo llamar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 05b6a9caebdd65f20357070af8bd44cb8ba146c7
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Información general {#calling-a-workflow-with-external-parameters}

Campaign Standard le permite llamar a un flujo de trabajo con parámetros (un nombre de audiencia a destinatario, un nombre de archivo para importar, una parte del contenido del mensaje, etc.). De este modo, puede integrar fácilmente sus automatizaciones de Campaña con su sistema externo.

Veamos el siguiente ejemplo, donde queremos enviar correos electrónicos directamente desde un CMS. En ese caso, puede configurar el sistema para que seleccione la audiencia y el contenido del correo electrónico en el CMS. Al hacer clic en Enviar, se llamará a un flujo de trabajo de Campaña con estos parámetros, lo que le permitirá utilizarlos en el flujo de trabajo para definir la audiencia y el contenido URL que se utilizarán en el envío.

El proceso para llamar a un flujo de trabajo con parámetros es el siguiente:

1. Declare los parámetros en la actividad **[!UICONTROL External signal]**. Consulte [Declaración de los parámetros en la actividad de señal externa](../../automating/using/declaring-parameters-external-signal.md).
1. Configure la actividad **[!UICONTROL End]** o la llamada de API para definir los parámetros y el déclencheur de la actividad **[!UICONTROL External signal]** del flujo de trabajo. Consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)
1. Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos del flujo de trabajo y se pueden utilizar dentro del mismo. Consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)

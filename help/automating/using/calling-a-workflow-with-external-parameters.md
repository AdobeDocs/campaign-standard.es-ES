---
title: Información general
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---


# Información general {#calling-a-workflow-with-external-parameters}

Campaign Standard le permite llamar a un flujo de trabajo con parámetros (un nombre de audiencia a destinatario, un nombre de archivo para importar, una parte del contenido del mensaje, etc.). De este modo, puede integrar fácilmente sus automatizaciones de Campaña con su sistema externo.

Veamos el siguiente ejemplo, donde queremos enviar correos electrónicos directamente desde un CMS. En ese caso, puede configurar el sistema para que seleccione la audiencia y el contenido del correo electrónico en el CMS. Al hacer clic en Enviar, se llamará a un flujo de trabajo de Campaña con estos parámetros, lo que le permitirá utilizarlos en el flujo de trabajo para definir la audiencia y el contenido URL que se utilizarán en el envío.

El proceso para llamar a un flujo de trabajo con parámetros es el siguiente:

1. Declare los parámetros en la **[!UICONTROL External signal]** actividad. Consulte [Declaración de los parámetros en la actividad](../../automating/using/declaring-parameters-external-signal.md)de señal externa.
1. Configure la **[!UICONTROL End]** actividad o la llamada de API para definir los parámetros y activar la **[!UICONTROL External signal]** actividad de flujo de trabajo.

Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos del flujo de trabajo y se pueden utilizar dentro del mismo. Consulte [](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)

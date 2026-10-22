---
title: Información general
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
TQID: 'https://experienceleague.adobe.com/Pin9vFRMMylFFKw6VSvQowwXvzAn1Ihg76e2cSoaeyw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%
---
# Información general {#calling-a-workflow-with-external-parameters}

Campaign Standard permite llamar a un flujo de trabajo con parámetros (un nombre de audiencia para el destino, un nombre de archivo para importar, una parte del contenido del mensaje, etc.). De este modo, puede integrar fácilmente las automatizaciones de Campaign con su sistema externo.

Veamos el siguiente ejemplo, donde queremos enviar correos electrónicos directamente desde un CMS. En ese caso, puede configurar el sistema para que seleccione la audiencia y el contenido del correo electrónico en CMS. Al hacer clic en Enviar, se llama a un flujo de trabajo de Campaign con estos parámetros, lo que permite utilizarlos en el flujo de trabajo para definir la audiencia y el contenido de la URL que se utilizarán en la entrega.

El proceso para llamar a un flujo de trabajo con parámetros es el siguiente:

1. Declare los parámetros en la actividad **[!UICONTROL External signal]**. Vea [Declarar los parámetros en la actividad Señal externa](../../automating/using/declaring-parameters-external-signal.md).
1. Configure la actividad **[!UICONTROL End]** o la llamada de API para definir los parámetros y almacenar en déclencheur la actividad **[!UICONTROL External signal]** del flujo de trabajo. Ver [esta página](../../automating/using/defining-parameters-calling-workflow.md)
1. Una vez activado el flujo de trabajo, los parámetros se incorporan a las variables de eventos del flujo de trabajo y se pueden utilizar en él. Consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)

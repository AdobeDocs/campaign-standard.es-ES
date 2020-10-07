---
title: Configuración de la integración de Campaign-Analytics
description: Obtenga información sobre cómo configurar la integración de Adobe Analytics en inicio para medir el éxito de sus envíos de correo electrónico.
page-status-flag: never-activated
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---


# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir los datos del indicador de rendimiento clave directamente de Adobe Campaign a Adobe Analytics Standard o Premium.

Para inicio de la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

Las cuentas externas y flujos de trabajo técnicos sólo pueden ser administradas por el administrador funcional de la plataforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleccione la cuenta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique el **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el **[!UICONTROL Connection]** campo.

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Haga clic en el botón **[!UICONTROL Refresh report suites]**.
1. Seleccione en la **[!UICONTROL Analytics default report suite]** lista desplegable el grupo de informes de Adobe Analytics que desee enriquecer con los datos de Adobe Campaign.

   Su cuenta externa ya está lista y vinculada con Adobe Analytics. Puede desactivarlo en cualquier momento marcando la **[!UICONTROL Enabled]** casilla.

   ![](assets/analytics.png)

El flujo de trabajo **[!UICONTROL Share KPIs with Adobe Analytics]** técnico ahora se iniciará automáticamente y se puede ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico se ejecutará automáticamente cada 15 minutos y enviará datos de hasta 6 meses de antigüedad en Adobe Analytics.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para vídeo de sistema de informes](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) de Campaña integrado


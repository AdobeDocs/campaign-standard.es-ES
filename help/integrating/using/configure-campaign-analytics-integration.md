---
solution: Campaign Standard
product: campaign
title: Configuración de la integración de Campaign-Analytics
description: Obtenga información sobre cómo configurar la integración de Adobe Analytics en inicio para medir el éxito de sus envíos de correo electrónico.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---


# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir los datos del indicador de rendimiento clave directamente de Adobe Campaign a Adobe Analytics Standard o Premium.

Para inicio de la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

Las cuentas externas y flujos de trabajo técnicos sólo pueden ser administradas por el administrador funcional de la plataforma.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleccione la cuenta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el campo **[!UICONTROL Connection]**.

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Haga clic en el botón **[!UICONTROL Refresh report suites]**.
1. Seleccione en la lista desplegable **[!UICONTROL Analytics default report suite]** el grupo de informes de Adobe Analytics que desee enriquecer con los datos de Adobe Campaign.

   Su cuenta externa ya está lista y vinculada con Adobe Analytics. Puede deshabilitarlo en cualquier momento marcando la casilla **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

El flujo de trabajo técnico **[!UICONTROL Share KPIs with Adobe Analytics]** ahora se iniciará automáticamente y se puede ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico se ejecutará automáticamente cada 15 minutos y enviará datos de hasta 6 meses de antigüedad en Adobe Analytics.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para ](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) informes de Campaña integrados


---
title: Configuración de la integración de Campaign-Analytics
description: Aprenda a configurar la integración de Adobe Analytics para que empiece a medir el éxito de los envíos de correo electrónico.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---

# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir sus datos de Indicador de rendimiento clave directamente de Adobe Campaign a Adobe Analytics Standard o Premium.

Para iniciar la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

El administrador funcional de la plataforma solo puede administrar las cuentas externas y los flujos de trabajo técnicos.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleccione la cuenta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el campo **[!UICONTROL Connection]**.

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Haga clic en el botón **[!UICONTROL Refresh report suites]**.
1. Seleccione en la lista desplegable **[!UICONTROL Analytics default report suite]** el grupo de informes de Adobe Analytics que desea enriquecer con los datos de Adobe Campaign.

   La cuenta externa ya está lista y vinculada a Adobe Analytics. Puede deshabilitarlo en cualquier momento marcando la casilla **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

El flujo de trabajo técnico **[!UICONTROL Share KPIs with Adobe Analytics]** ahora se iniciará automáticamente y se puede ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico se ejecutará automáticamente cada 15 minutos e insertará datos de hasta 6 meses de antigüedad en Adobe Analytics.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para el vídeo integrado de ](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) informes de Campaign

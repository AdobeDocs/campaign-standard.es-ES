---
title: Configuración de la integración de Campaign-Analytics
seo-title: Configuración de la integración de Campaign-Analytics
description: Configuración de la integración de Campaign-Analytics
seo-description: Descubra cómo configurar la integración de Adobe Analytics para comenzar a medir el éxito de sus entregas de correo electrónico.
page-status-flag: no activado nunca
uuid: bdaa 00 b 0-7445-469 c -8268-9 d 06 c 53 ce 2 b 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92 b 9004 c-cba 0-41 fd-a 035-32 bee 1 d 6 a 42 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

Esta integración le permite compartir los datos de indicador de rendimiento clave directamente de Adobe Campaign a Adobe Analytics Standard o Premium.

Para iniciar la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

Las cuentas externas y los flujos de trabajo técnicos solo pueden gestionarlos el administrador funcional de la plataforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   Su cuenta externa está lista y vinculada con Adobe Analytics. You can disable it at any time by checking the **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

The **[!UICONTROL Share KPIs with Adobe Analytics]** technical workflow will now automatically launch and can be viewed from the advanced menu by selecting **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico se ejecutará automáticamente cada 15 minutos y se almacenarán hasta 6 meses de datos antiguos en Adobe Analytics.

![](assets/analytics_3.png)

Ahora los datos están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para informes de informes](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) de campaña integrados


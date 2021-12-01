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
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 10%

---

# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir sus datos de Indicador de rendimiento clave directamente de Adobe Campaign a Adobe Analytics Standard o Premium.

Para iniciar la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

El administrador funcional de la plataforma solo puede administrar las cuentas externas y los flujos de trabajo técnicos.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleccione la cuenta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique la **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el **[!UICONTROL Connection]** campo .

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Haga clic en el botón **[!UICONTROL Refresh report suites]**.
1. Seleccione en el **[!UICONTROL Analytics default report suite]** desplegable del grupo de informes de Adobe Analytics que desea enriquecer con los datos de Adobe Campaign.

   La cuenta externa ya está lista y vinculada a Adobe Analytics. Puede deshabilitarlo en cualquier momento comprobando la variable **[!UICONTROL Enabled]** en la ventana

   ![](assets/analytics.png)

La variable **[!UICONTROL Share KPIs with Adobe Analytics]** el flujo de trabajo técnico ahora se iniciará automáticamente y se puede ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico puede retener registros generales de hasta 6 meses de antigüedad. Tenga en cuenta que este flujo de trabajo es incremental y push de datos del día anterior.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para la creación de informes de Campaign integrada](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) video

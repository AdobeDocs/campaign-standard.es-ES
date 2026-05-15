---
title: Configuración de la integración de Campaign-Analytics
description: Obtenga información sobre cómo configurar la integración de Adobe Analytics para empezar a medir el éxito de los envíos de correo electrónico.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
TQID: https://experienceleague.adobe.com/bt1FQbafwhEuRao-YFhynO-ecg5EaiUDskSFvxuFv-k
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 12%

---

# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir sus datos de indicadores de rendimiento clave directamente desde Adobe Campaign a Adobe Analytics Standard o Premium.

Para iniciar la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

Solo el administrador funcional de la plataforma puede administrar las cuentas externas y los flujos de trabajo técnicos.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleccione la cuenta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique sus **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el campo **[!UICONTROL Connection]**.

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Haga clic en el botón **[!UICONTROL Refresh report suites]**.
1. Seleccione en la lista desplegable **[!UICONTROL Analytics default report suite]** el grupo de informes de Adobe Analytics que desee enriquecer con datos de Adobe Campaign.

   La cuenta externa ya está lista y vinculada con Adobe Analytics. Puede deshabilitarlo en cualquier momento marcando la casilla **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

El flujo de trabajo técnico **[!UICONTROL Share KPIs with Adobe Analytics]** se iniciará automáticamente y se podrá ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico puede conservar broadlogs de hasta 6 meses de antigüedad. Tenga en cuenta que este flujo de trabajo es incremental y enviará datos del día anterior.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para la creación de informes de Campaign integrada](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html) vídeo

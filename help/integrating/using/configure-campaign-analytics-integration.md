---
title: Configuración de la integración de Campaign-Analytics
description: Obtenga información sobre cómo configurar la integración de Adobe Analytics para empezar a medir el éxito de los envíos de correo electrónico.
page-status-flag: nunca activado
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y análisis
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configuración de la integración de Campaign-Analytics{#configure-campaign-analytics-integration}

Esta integración le permite compartir los datos del indicador de rendimiento clave directamente desde Adobe Campaign a Adobe Analytics Standard o Premium.

Para iniciar la integración entre Adobe Campaign Standard y Adobe Analytics, primero debe configurar la cuenta externa vinculada a Adobe Analytics.

Las cuentas externas y los flujos de trabajo técnicos solo pueden ser administrados por el administrador funcional de la plataforma.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Especifique el **[!UICONTROL Web services user name]** y **[!UICONTROL Web services share secret]** en el **[!UICONTROL Connection]** campo.

   Estos parámetros se pueden encontrar en Analytics seleccionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Seleccione en la **[!UICONTROL Analytics default report suite]** lista desplegable el grupo de informes de Adobe Analytics que desea enriquecer con los datos de Adobe Campaign.

   Su cuenta externa ya está lista y vinculada con Adobe Analytics. Puede desactivarlo en cualquier momento marcando la **[!UICONTROL Enabled]** casilla.

   ![](assets/analytics.png)

El flujo de trabajo **[!UICONTROL Share KPIs with Adobe Analytics]** técnico ahora se iniciará automáticamente y se puede ver desde el menú avanzado seleccionando **[!UICONTROL Administration > Application settings > Workflow]**. Este flujo de trabajo técnico se ejecuta automáticamente cada 15 minutos y enviará datos de hasta 6 meses de antigüedad en Adobe Analytics.

![](assets/analytics_3.png)

Los datos ya están disponibles en Adobe Analytics.

**Temas relacionados:**

* [Cuentas externas](../../administration/using/external-accounts.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Compartir KPI para vídeo de informes](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) de campañas integrados


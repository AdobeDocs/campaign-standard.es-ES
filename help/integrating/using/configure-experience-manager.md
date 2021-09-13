---
title: Configuración de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 18%

---

# Configuración de la integración de Campaign-Experience Manager {#configuration-aem}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Con este caso de uso, aprenderá a crear y administrar el contenido de los correos electrónicos en Adobe Experience Manager y, a continuación, a utilizarlos para sus campañas de marketing importándolos en sus correos electrónicos a Adobe Campaign Standard.

## Requisitos previos {#prerequisites}

Asegúrese de tener los siguientes elementos previamente:

* Una instancia **creación** de Adobe Experience Manager
* Una instancia **publicación** de Adobe Experience Manager
* Una instancia de Adobe Campaign

## Configuración en Adobe Campaign Standard {#config-acs}

Para utilizar estas dos soluciones juntas, debe configurarlas para que se conecten entre sí.
Para configurar Adobe Campaign:

1. Primero debe configurar la cuenta externa **[!UICONTROL Adobe Experience Manager instance]** en **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configure la cuenta externa de tipo Adobe Experience Manager con la dirección URL **[!UICONTROL Server]**, **[!UICONTROL Account]** y **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Compruebe que la opción **[!UICONTROL AEMResourceTypeFilter]** se haya configurado correctamente. Acceda al menú **[!UICONTROL Options]** en el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

1. En el campo **[!UICONTROL Value (text)]**, compruebe que la siguiente sintaxis sea correcta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. A continuación, en el menú avanzado en **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplique una de las plantillas existentes para crear una plantilla de correo electrónico específica de Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Haga clic en el icono **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. En la lista desplegable **[!UICONTROL Content]**, seleccione **[!UICONTROL Adobe Experience Manager]** en el campo **[!UICONTROL Content source]** y, a continuación, la cuenta externa creada anteriormente en **[!UICONTROL Adobe Experience Manager account]**.

Ahora necesita configurar la integración en Adobe Experience Manager.

## Configuración en Adobe Experience Manager {#config-aem}

Para configurar Adobe Experience Manager con Adobe Campaign Standard, debe seguir estos pasos:

1. Primero debe configurar la replicación entre las instancias de creación y publicación de Adobe Experience Manager. Consulte esta [sección](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. A continuación, conecte Adobe Experience Manager a Adobe Campaign configurando un **[!UICONTROL Cloud Service]** dedicado. Consulte esta [sección](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Ahora debe configurar el externalizador en Adobe Experience Manager en la instancia de autor. Consulte esta [sección](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

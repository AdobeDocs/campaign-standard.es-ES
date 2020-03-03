---
title: Configuración de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Configuración de la integración de Campaign-Experience Manager {#configuration-aem}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Con este caso de uso aprenderá a crear y administrar el contenido del correo electrónico en Adobe Experience Manager y, a continuación, a utilizarlo para sus campañas de marketing importándolo en sus correos electrónicos a Adobe Campaign Standard.

## Requisitos previos {#prerequisites}

Asegúrese de que tiene los siguientes elementos de antemano:

* Una instancia **creación** de Adobe Experience Manager
* Una instancia **publicación** de Adobe Experience Manager
* Una instancia de Adobe Campaign

## Configuración en Adobe Campaign Standard {#config-acs}

Para utilizar estas dos soluciones juntas, debe configurarlas para que se conecten entre sí.
Para configurar Adobe Campaign:

1. En primer lugar, debe configurar la cuenta **[!UICONTROL Adobe Experience Manager instance]** externa en **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configure la cuenta externa de tipo Adobe Experience Manager con su **[!UICONTROL Server]** dirección URL **[!UICONTROL Account]** y **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Compruebe que la **[!UICONTROL AEMResourceTypeFilter]** opción se ha configurado correctamente. Acceda al **[!UICONTROL Options]** menú en **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

1. En el **[!UICONTROL Value (text)]** campo, compruebe que la sintaxis es correcta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. A continuación, en el menú avanzado en **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplique una de las plantillas existentes para crear una plantilla de correo electrónico específica de Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Haga clic en el **[!UICONTROL Edit properties]** icono.

   ![](assets/aem_4.png)

1. En la **[!UICONTROL Content]** lista desplegable, seleccione **[!UICONTROL Adobe Experience Manager]** en el **[!UICONTROL Content source]** campo y luego la cuenta externa creada anteriormente en la **[!UICONTROL Adobe Experience Manager account]**.

Ahora debe configurar la integración en Adobe Experience Manager.

## Configuration in Adobe Experience Manager {#config-aem}

Para configurar Adobe Experience Manager con Adobe Campaign Standard, debe seguir estos pasos:

1. En primer lugar, debe configurar la replicación entre las instancias de creación y publicación de Adobe Experience Manager. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Then, connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Ahora debe configurar el externalizador en Adobe Experience Manager en la instancia de creación. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).


---
solution: Campaign Standard
product: campaign
title: Configuración de la integración Campaign Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 17%

---


# Configuración de la integración Campaign Experience Manager {#configuration-aem}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Con este caso de uso aprenderá a crear y administrar el contenido del correo electrónico en Adobe Experience Manager y, a continuación, a usarlo para sus campañas de marketing importándolo en sus correos electrónicos a Adobe Campaign Standard.

## Requisitos previos {#prerequisites}

Asegúrese de que tiene los siguientes elementos de antemano:

* Una instancia **creación** de Adobe Experience Manager
* Una instancia **publicación** de Adobe Experience Manager
* Una instancia de Adobe Campaign

## Configuración en Adobe Campaign Standard {#config-acs}

Para utilizar estas dos soluciones juntas, debe configurarlas para que se conecten entre sí.
Para configurar Adobe Campaign:

1. Primero debe configurar la cuenta externa **[!UICONTROL Adobe Experience Manager instance]** en **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configure la cuenta externa de tipo Adobe Experience Manager con la dirección URL **[!UICONTROL Server]**, **[!UICONTROL Account]** y **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Compruebe que la opción **[!UICONTROL AEMResourceTypeFilter]** se ha configurado correctamente. Acceda al menú **[!UICONTROL Options]** en el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

1. En el campo **[!UICONTROL Value (text)]**, compruebe que la siguiente sintaxis es correcta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. A continuación, en el menú avanzado en **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplicado una de las plantillas existentes para crear una plantilla de correo electrónico específica para Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Haga clic en el icono **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. En la lista desplegable **[!UICONTROL Content]**, seleccione **[!UICONTROL Adobe Experience Manager]** en el campo **[!UICONTROL Content source]** y luego la cuenta externa creada anteriormente en **[!UICONTROL Adobe Experience Manager account]**.

Ahora debe configurar la integración en Adobe Experience Manager.

## Configuración en Adobe Experience Manager {#config-aem}

Para configurar Adobe Experience Manager con Adobe Campaign Standard, debe seguir estos pasos:

1. En primer lugar, debe configurar la replicación entre las instancias de creación y publicación de Adobe Experience Manager. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. A continuación, conecte Adobe Experience Manager a Adobe Campaign configurando un **[!UICONTROL Cloud Service]** dedicado. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Ahora debe configurar el externalizador en Adobe Experience Manager en la instancia de creación. Consulte esta [sección](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).


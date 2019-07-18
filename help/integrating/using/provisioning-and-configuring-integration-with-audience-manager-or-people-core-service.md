---
title: Aprovisionamiento y configuración de la integración con los servicios principales de Audience Manager o Personas
seo-title: Aprovisionamiento y configuración de la integración con los servicios principales de Audience Manager o Personas
description: Aprovisionamiento y configuración de la integración con los servicios principales de Audience Manager o Personas
seo-description: 'Aprenda a configurar la integración del servicio principal de Audience Manager/Personas para empezar a compartir audiencias o segmentos con las distintas soluciones de Adobe Experience Cloud. '
page-status-flag: no activado nunca
uuid: e 7329644-0033-4729-b 4 a 7-61 bef 137 f 4 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb 24 f 4 ea -325 f -433 a -91 a 0-c 45906320 bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Provisioning and configuring integration with Audience Manager or People core service{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

The provisioning and configuring of Audience Manager and People core in Adobe Campaign take two steps: [Submitting request to Adobe](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) then [Configuring the integration in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign).

## Submitting request to Adobe {#submitting-request-to-adobe}

La integración de servicios principales de Audience Manager (AAM) o Personas permite importar y exportar audiencias o segmentos en Adobe Campaign.

Primero debe configurarse esta integración. To request provisioning of this integration, write an email to [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) with the following information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo de solicitud:</strong><br /> </td> 
   <td> Configurar la integración entre los servicios principales de AAM y personas </td> 
  </tr> 
  <tr> 
   <td> <strong>Nombre de la organización:</strong><br /> </td> 
   <td> Nombre de su organización </td> 
  </tr> 
  <tr> 
   <td> <strong>ID de organización de IMS</strong><br /> </td> 
   <td> ID de organización de IMS * </td> 
  </tr> 
  <tr> 
   <td> <strong>Entorno:</strong><br /> </td> 
   <td> Ejemplo: Producción </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM o servicio Personas</strong><br /> </td> 
   <td> Ejemplo: Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>ID declarado o ID de visitante</strong><br /> </td> 
   <td> Ejemplo: ID declarado </td> 
  </tr> 
  <tr> 
   <td> <strong>Información adicional</strong><br /> </td> 
   <td> Cualquier información o comentario útil que pueda tener </td> 
  </tr> 
 </tbody> 
</table>

* You can find your IMS Org ID on the Experience Cloud, in the **Administration** menu. También se facilita al conectarse por primera vez a Adobe Experience Cloud.

## Configuring the integration in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Después de enviar esta solicitud, Adobe llevará a cabo el aprovisionamiento de la integración para ponerse en contacto con usted para proporcionar detalles e información que tiene que completar para finalizar la configuración:

* [Paso 1: Configurar o comprobar las cuentas externas en Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Paso 2: Configurar las fuentes de datos](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [Paso 3: Configurar el servidor de seguimiento de campaña](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [Paso 4: Configuración del servicio de ID de visitante](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primero es necesario configurar o comprobar las cuentas externas en Adobe Campaign. Adobe debe haber configurado estas cuentas y debería haberle comunicado la información necesaria.

Para ello:

1. From the advanced menu, select **Administration &gt; Application settings &gt; External accounts**.

   Seleccione una de las siguientes cuentas externas disponibles para esta integración:

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in following format
1. Enter the **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** and **[!UICONTROL AWS Region]**.

Las cuentas externas ahora se configuran para esta integración.

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

Los dos orígenes de datos siguientes se crean dentro de Audience Manager: Adobe Campaign (MID) y Adobe Campaign (declaredid). Al mismo tiempo, estas dos fuentes de datos están disponibles en Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Se trata de una fuente de datos predeterminada configurada de forma predeterminada para ID de visitante. Los segmentos creados desde Campaign formarán parte de esta fuente de datos.
* **Fuente de** datos de ID declarado: Esta fuente de datos debe crearse y asignarse a la **[!UICONTROL DeclaredId]** definición de fuente de datos desde Audience Manager.

Tenga en cuenta que, en el caso de varios sitios web con dominios diferentes, Adobe Campaign no admite la reconciliación basada en ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Enter the **[!UICONTROL AAM Destination ID]** provided by Adobe.

   ![](assets/integration_aam_3.png)

1. In the **[!UICONTROL Reconciliation process]** category, we advise you not to change the reconciliation criteria and always use the **[!UICONTROL Visitor ID]**.
1. Click **[!UICONTROL Save]**.

To create the **[!UICONTROL Declared ID]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, click the **[!UICONTROL Create]** button.
1. Edit the **[!UICONTROL Label]** of your data source.
1. In the **[!UICONTROL Data Source/ Alias]** drop-down, choose the Data Source corresponding to the **[!UICONTROL DeclaredID]** data source from Audience Manager.
1. Configure your data source by entering the **[!UICONTROL Data Source / Alias]** and **[!UICONTROL AAM Destination ID]** provided by Adobe.
1. Set the **[!UICONTROL Reconciliation process]** as needed.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>The **[!UICONTROL AAM Destination ID]** field is not required if you are configuring the shared data source for the [Campaign-Triggers integration](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** solo es necesario al configurar Activadores - Integración de campañas. La prioridad decide qué fuente de datos se configurará primero. La prioridad puede ser cualquier número como 1 o 100. Cuanto mayor sea la prioridad, mayor será la preferencia durante la reconciliación.

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

Para configurar la integración con el servicio Personas Core o Audience Manager, también necesitamos configurar el servidor de seguimiento de campaña.

Aquí, debe asegurarse de que el servidor de seguimiento de campaña esté registrado en el dominio (CNAME). You can find more information about domain name delegation in [this article](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

In the case that your Visitor ID service has never been configured on your web properties or websites, refer to the following [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) to learn how to configure your service or the following [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

La configuración y el aprovisionamiento se han completado, la integración ahora se puede utilizar para importar y exportar audiencias o segmentos.

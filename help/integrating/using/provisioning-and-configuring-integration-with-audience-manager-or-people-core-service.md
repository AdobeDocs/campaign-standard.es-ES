---
title: Aprovisionamiento y configuración de la integración con Audience Manager o el servicio principal People
description: 'Obtenga información sobre cómo configurar la integración de servicios principales Audience Manager/Personas para audiencias o segmentos de uso compartido de inicios con las distintas soluciones de Adobe Experience Cloud. '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 41%

---


# Aprovisionamiento y configuración de la integración con Audience Manager o el servicio principal People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

El aprovisionamiento y la configuración del núcleo de Audience Manager y personas en Adobe Campaign realizan dos pasos: [Enviando la solicitud a Adobe](#submitting-request-to-adobe) y luego [configurando la integración en Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envío de la solicitud a Adobe {#submitting-request-to-adobe}

La integración de servicios principales de Audience Manager (AAM) o Personas le permite importar y exportar audiencias o segmentos en Adobe Campaign.

Esta integración debe configurarse primero. Para solicitar esta integración, escriba un correo electrónico a [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) con la siguiente información:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo de solicitud:</strong><br /> </td> 
   <td> Configuración de la integración AAM/servicio principal Personas de Campaign </td> 
  </tr> 
  <tr> 
   <td> <strong>Nombre de la organización</strong><br /> </td> 
   <td> Nombre de su organización </td> 
  </tr> 
  <tr> 
   <td> <strong>ID de organización IMS</strong><br /> </td> 
   <td> Su ID de la organización IMS. <br> Puede encontrar la ID de la organización IMS en Experience Cloud, en el menú Administration. También se proporciona al conectarse por primera vez a Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Entorno:</strong><br /> </td> 
   <td> Ejemplo: Producción </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM o servicio Personas</strong><br /> </td> 
   <td> Ejemplo: Adobe Audience Manager. Asegúrese de mencionar al equipo de aprovisionamiento si posee o no una licencia de Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>ID declarada o ID de visitante</strong><br /> </td> 
   <td> Ejemplo: ID declarado </td> 
  </tr> 
  <tr> 
   <td> <strong>Información adicional</strong><br /> </td> 
   <td> Cualquier información o comentario útil que pueda tener </td> 
  </tr> 
 </tbody> 
</table>

## Configuración de la integración en Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Después de enviar esta solicitud, Adobe procederá al aprovisionamiento de la integración y se pondrá en contacto con usted para proporcionarle los detalles y la información que necesita para finalizar la configuración:

* [Paso 1: Configuración o verificación de las cuentas externas en Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Paso 2: Configurar las fuentes de datos](#step-2--configure-the-data-sources)
* [Paso 3: Configuración del servidor de seguimiento de campaña](#step-3--configure-campaign-tracking-server)
* [Paso 4: Configuración del servicio de ID de visitante](#step-4--configure-the-visitor-id-service)

### Paso 1: Configuración o verificación de las cuentas externas en Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primero necesitamos configurar o comprobar las cuentas externas en Adobe Campaign. Estas cuentas deberían haber sido configuradas por Adobe y la información necesaria debería haberle sido comunicada.

Para ello:

1. En el menú avanzado, seleccione **Administración > Ajustes de aplicación > Cuentas externas**.

   Seleccione una de las siguientes cuentas externas disponibles para esta integración:

   ![](assets/integration_aam_1.png)

1. Intro **[!UICONTROL Receiver server]** en el siguiente formato
1. Introduzca **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** y **[!UICONTROL AWS Region]**.

Sus cuentas externas ahora están configuradas para esta integración.

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

Las dos fuentes de datos siguientes se crean dentro del administrador de Audiencias: Adobe Campaign (MID) y Adobe Campaign (DeclaredId). Al mismo tiempo, estas dos fuentes de datos están disponibles en Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Constituye una fuente de datos de serie y configurada de forma predeterminada para la ID del visitante. Los segmentos creados con Campaign forman parte de esta fuente de datos.
* **Origen de datos de ID** declarado: Esta fuente de datos debe crearse y asignarse con la definición de fuente de datos **[!UICONTROL DeclaredId]** de Audience Manager.

Tenga en cuenta que en el caso de varios sitios web con diferentes dominios, Adobe Campaign no admite la reconciliación basada en ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Introduzca el valor **[!UICONTROL AAM Destination ID]** proporcionado por el Adobe.

   ![](assets/integration_aam_3.png)

1. En la **[!UICONTROL Reconciliation process]** categoría, le aconsejamos que no cambie los criterios de reconciliación y que siempre utilice el **[!UICONTROL Visitor ID]**.
1. Haga clic en **[!UICONTROL Save]**.

Para crear la fuente de **[!UICONTROL Declared ID]** datos:

1. En **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, haga clic en el **[!UICONTROL Create]** botón.
1. Edite el **[!UICONTROL Label]** origen de datos.
1. En la **[!UICONTROL Data Source/ Alias]** lista desplegable, elija la fuente de datos correspondiente a la fuente de datos desde el Audience Manager **[!UICONTROL DeclaredID]** .
1. Configure la fuente de datos ingresando el **[!UICONTROL Data Source / Alias]** y **[!UICONTROL AAM Destination ID]** proporcionado por Adobe.
1. Configure los **[!UICONTROL Reconciliation process]** valores según sea necesario.
1. Haga clic en **[!UICONTROL Save]**.

>[!NOTE]
>
>El **[!UICONTROL AAM Destination ID]** campo no es obligatorio si está configurando el origen de datos compartido para la integración [de](../../integrating/using/configuring-triggers-in-experience-cloud.md)Campañas-activadores. **[!UICONTROL Priority]** solo se necesita al configurar los activadores: integración de Campaña. Priority decide qué fuente de datos se configurará primero. La prioridad puede ser cualquier número, como 1 o 100. Cuanto mayor sea la prioridad, mayor será la preferencia durante la reconciliación.

### Paso 3: Configuración del servidor de seguimiento de campaña {#step-3--configure-campaign-tracking-server}

Para la configuración de la integración con el servicio principal Personas o Audience Manager, también es necesario configurar el servidor de seguimiento de campañas.

Aquí, debe asegurarse de que el servidor de seguimiento de Campaña está registrado en el dominio (CNAME). Se puede encontrar más información sobre la delegación de nombres de dominio en [este artículo](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Paso 4: Configuración del servicio de ID de visitante {#step-4--configure-the-visitor-id-service}

En caso de que el servicio de ID de visitante no se haya configurado en las propiedades web o sitios web, consulte el siguiente [documento](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html) o el siguiente [vídeo](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html#step-two) para aprender a configurar el servicio.

La configuración y el suministro han finalizado, la integración ya puede utilizarse para importar y exportar audiencias o segmentos.

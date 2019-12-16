---
title: Aprovisionamiento y configuración de la integración con Audience Manager o el servicio principal People
description: 'Obtenga información sobre cómo configurar la integración del servicio principal Audience Manager/Personas para empezar a compartir audiencias o segmentos con las distintas soluciones de Adobe Experience Cloud. '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e887fff76660dcb0369d4222e1ab3ac391c3a2d

---


# Aprovisionamiento y configuración de la integración con Audience Manager o el servicio principal People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

El aprovisionamiento y la configuración del núcleo de Audience Manager y Personas en Adobe Campaign lleva a cabo dos pasos: [Envío de una solicitud a Adobe](#submitting-request-to-adobe) y, a continuación, [Configuración de la integración en Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envío de la solicitud a Adobe {#submitting-request-to-adobe}

La integración de servicio principal de Audience Manager (AAM) o Personas le permite importar y exportar audiencias o segmentos en Adobe Campaign.

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
   <td> Su ID de organización de IMS. <br> Puede encontrar la ID de la organización IMS en Experience Cloud, en el menú
        Administration. También se proporciona al conectarse
      por primera vez a Adobe Experience Cloud. </td> 
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

Después de enviar esta solicitud, Adobe procederá al aprovisionamiento de la integración para usted y se pondrá en contacto con usted para proporcionarle los detalles y la información necesarios para finalizar la configuración:

* [Paso 1: Configuración o comprobación de cuentas externas en Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Paso 2: Configurar las fuentes de datos](#step-2--configure-the-data-sources)
* [Paso 3: Configuración del servidor de seguimiento de campaña](#step-3--configure-campaign-tracking-server)
* [Paso 4: Configuración del servicio de ID de visitante](#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primero debemos configurar o comprobar las cuentas externas en Adobe Campaign. Estas cuentas deberían haber sido configuradas por Adobe y se debería haber comunicado la información necesaria.

Para ello:

1. En el menú avanzado, seleccione **Administración &gt; Ajustes de aplicación &gt; Cuentas** externas.

   Seleccione una de las siguientes cuentas externas disponibles para esta integración:

   ![](assets/integration_aam_1.png)

1. Intro **[!UICONTROL Receiver server]** en el siguiente formato
1. Introduzca **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** y **[!UICONTROL AWS Region]**.

Sus cuentas externas ahora están configuradas para esta integración.

### Paso 2: Configurar las fuentes de datos {#step-2--configure-the-data-sources}

Las dos fuentes de datos siguientes se crean dentro de Audience Manager: Adobe Campaign (MID) y Adobe Campaign (DeclaredId). Al mismo tiempo, estas dos fuentes de datos están disponibles en Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Constituye una fuente de datos de serie y configurada de forma predeterminada para la ID del visitante. Los segmentos creados con Campaign forman parte de esta fuente de datos.
* **Origen de datos de ID** declarado: Esta fuente de datos debe crearse y asignarse con la definición de fuente de datos de Audience Manager. **[!UICONTROL DeclaredId]**

Tenga en cuenta que, en el caso de varios sitios web con distintos dominios, Adobe Campaign no admite la reconciliación basada en ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. En **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, seleccione **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Elija **[!UICONTROL Adobe Campaign]** en la **[!UICONTROL Data Source/ Alias]** lista desplegable.
1. Introduzca el valor **[!UICONTROL AAM Destination ID]** proporcionado por Adobe.

   ![](assets/integration_aam_3.png)

1. En la **[!UICONTROL Reconciliation process]** categoría, le recomendamos que no cambie los criterios de reconciliación y que siempre utilice el **[!UICONTROL Visitor ID]**.
1. Click **[!UICONTROL Save]**.

Para crear la fuente de **[!UICONTROL Declared ID]** datos:

1. En **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, haga clic en el **[!UICONTROL Create]** botón.
1. Edite el **[!UICONTROL Label]** origen de datos.
1. En la **[!UICONTROL Data Source/ Alias]** lista desplegable, elija la fuente de datos correspondiente a la fuente de datos en Audience Manager **[!UICONTROL DeclaredID]** .
1. Para configurar la fuente de datos, ingrese el **[!UICONTROL Data Source / Alias]** y **[!UICONTROL AAM Destination ID]** proporcionado por Adobe.
1. Configure los **[!UICONTROL Reconciliation process]** valores según sea necesario.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>El **[!UICONTROL AAM Destination ID]** campo no es obligatorio si está configurando el origen de datos compartido para la integración [](../../integrating/using/configuring-triggers-in-experience-cloud.md)Campaña-Desencadenadores. **[!UICONTROL Priority]** solo es necesario cuando se configura la integración Desencadenadores - Campaña. Priority decide qué fuente de datos se configurará primero. La prioridad puede ser cualquier número, como 1 o 100. Cuanto mayor sea la prioridad, mayor será la preferencia durante la reconciliación.

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

Para la configuración de la integración con el servicio principal Personas o Audience Manager, también es necesario configurar el servidor de seguimiento de campañas.

Aquí debe asegurarse de que el servidor de seguimiento de campañas está registrado en el dominio (CNAME). Se puede encontrar más información sobre la delegación de nombres de dominio en [este artículo](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

En caso de que el servicio de ID de visitante no se haya configurado en las propiedades web o sitios web, consulte el siguiente [documento](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) o el siguiente [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) para aprender a configurar el servicio.

La configuración y el suministro han finalizado, la integración ya puede utilizarse para importar y exportar audiencias o segmentos.

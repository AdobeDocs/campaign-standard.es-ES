---
title: Configuración de Adobe Developer para la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo configurar la integración de Adobe Developer para Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Configuración de Adobe Campaign Standard y Adobe Developer para la integración con Microsoft Dynamics 365

En este artículo se explica cómo configurar Adobe Campaign Standard y el Adobe I/O para que la aplicación de integración acceda a los datos.

## Configuración de Adobe Campaign Standard {#campaign-standard}

### Extensiones de perfil

Habilite las &quot;extensiones de perfil&quot; en Adobe Campaign Standard.   Esto es necesario para que los campos personalizados del recurso de perfil se sincronicen desde Microsoft Dynamics 365.   Los pasos para habilitarlos son los siguientes:

1. Vaya a Configuración -> Administración -> Desarrollo -> Publicación.
1. Haga clic en &quot;Preparar publicación&quot; para preparar una publicación.
1. Una vez finalizada la preparación, marque &quot;Crear la API de salida de perfiles y servicios&quot; y haga clic en &quot;Publicar&quot;.

## Configuración del Adobe I/O {#adobe-io}

El Adobe I/O le permite habilitar el acceso de API a Adobe Campaign Standard, así como a otros productos de Adobe.   Este artículo detallará cómo configurar el Adobe I/O para proporcionar a la integración de Adobe Campaign Standard con Microsoft Dynamics 365 acceso para sincronizar los datos.

### Información general

Antes de realizar la configuración de preintegración que se describe en este artículo, se da por hecho que ya se ha aprovisionado y tiene acceso de administrador a la instancia de Campaign Standard de su organización.  Si no es así, debe ponerse en contacto con el Servicio de atención al cliente de Adobe para completar el aprovisionamiento de Campaign.

>[!CAUTION]
>
>Los pasos que se describen a continuación deben ser realizados por un administrador.

### Configuración

Debe crear un nuevo proyecto de Adobe Developer y configurarlo para la integración.

#### Creación de un nuevo proyecto

Para lograr esto, siga el procedimiento a continuación:

1. Vaya a [Consola de Adobe Developer](https://console.adobe.io/home#) y seleccione su ID de organización de Adobe en el menú desplegable situado en la parte superior derecha de la pantalla.

1. Luego haga clic en **[!UICONTROL Create new project]** bajo **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. En **[!UICONTROL Get started with your new project]**, haga clic en **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleccione el Adobe Campaign y haga clic en **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. En la siguiente pantalla tendrá la opción de elegir el tipo de autenticación. Puede elegir OAuth Server-to-Server o Service Account (JWT). Tenga en cuenta que las credenciales de la cuenta de servicio (JWT) ya no se recomiendan para los nuevos proyectos y han quedado obsoletas en favor de las nuevas credenciales de servidor a servidor OAuth. Las instrucciones proporcionadas en esta guía solo se aplicarán a la autenticación de servidor a servidor OAuth.

   ![](assets/adobeIO4.png)

1. En la siguiente pantalla, seleccione los perfiles de producto que desea asociar a este proyecto. Seleccione el perfil de producto que contiene en el título: El ID de inquilino de la instancia de Campaign - [!UICONTROL Administrators]

   Ejemplo: Campaign Standard - your-campaign-tenantID - Administradores

1. Haga clic en **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. En la siguiente pantalla verá los detalles del nuevo proyecto de Adobe Developer. Clic **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** de la lista desplegable.

   ![](assets/adobeIO6.png)

1. En la siguiente pantalla, debe seleccionar la API de eventos de I/O y, a continuación, haga clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.  Volverá a la pantalla de detalles del proyecto.

1. Ahora haga clic en **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** de la lista desplegable, como lo hizo anteriormente.

1. En la siguiente pantalla, debe seleccionar la API de administración de E/S y hacer clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.

Ya se ha completado la configuración de preintegración en Campaign.

**Temas relacionados**

* [Configuración de Adobe Developer para la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) es el siguiente paso para configurar la integración
* [Descripción general de la aplicación de autoservicio de integración](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene la lista completa de pasos para poner en marcha la integración.
* [Adobe Developer: integración de cuenta de servicio](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuración de acceso a API](../../api/using/setting-up-api-access.md)
* [Campaign Standard: integración con Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [Migrar credenciales de JWT a servidor a servidor OAuth](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) contiene los pasos para migrar credenciales de JWT a OAuth Server-to-Server.

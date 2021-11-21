---
title: Configuración de Adobe IO para integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo configurar la integración de Adobe IO para Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: 7c34df594d4f649f259fb7edd946477f7b8d92d7
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 3%

---

# Configuración de Adobe Campaign Standard y Adobe I/O para la integración con Microsoft Dynamics 365

En este artículo se explica cómo configurar Adobe Campaign Standard y Adobe I/O para que la aplicación de integración tenga acceso a los datos.

## Configuración de Adobe Campaign Standard {#campaign-standard}

### Extensiones de perfil

Habilite &quot;extensiones de perfil&quot; en Adobe Campaign Standard.   Esto es necesario para que los campos personalizados del recurso Perfil se sincronicen desde Microsoft Dynamics 365.   Los pasos para habilitarlos son:

1. Vaya a Configuración -> Administración -> Desarrollo -> Publicación.
1. Haga clic en &quot;Preparar publicación&quot; para preparar una publicación.
1. Una vez finalizada la preparación, marque &quot;Create the Profiles &amp; Services Ext API&quot; y haga clic en &quot;Publish&quot;.

## Configuración de Adobe I/O {#adobe-io}

Adobe I/O le permite habilitar el acceso de API a Adobe Campaign Standard, así como a otros productos de Adobe.   Este artículo detalla cómo configurar el Adobe I/O para que la integración de Adobe Campaign Standard con Microsoft Dynamics 365 tenga acceso a la sincronización de datos.

### Información general

Antes de realizar la configuración previa a la integración en este artículo, se da por hecho que ya ha sido aprovisionado y tiene acceso de administrador a la instancia de Campaign Standard de su organización.  Si esto no ha sucedido, tendrá que ponerse en contacto con el Servicio de atención al cliente de Adobe para completar el aprovisionamiento de Campaign.

>[!CAUTION]
>
>Un administrador debe realizar los pasos que se describen a continuación.

### Configuración

Deberá crear un nuevo proyecto de IO de Adobe y configurarlo para la integración.

#### Crear un nuevo proyecto

Para lograrlo, siga el procedimiento a continuación:

1. Vaya a [Consola de IO de Adobe](https://console.adobe.io/home#) y seleccione su ID de organización de Adobe IMS en el menú desplegable situado en la parte superior derecha de la pantalla.

1. A continuación, haga clic en **[!UICONTROL Create new project]** under **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. En **[!UICONTROL Get started with your new project]**, haga clic en **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleccione la API de Adobe Campaign (puede que necesite desplazarse hacia abajo) y haga clic en **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. En la siguiente pantalla tendrá la opción de cargar su propia clave pública o dejar que Adobe IO genere el par de claves por usted. Estas instrucciones siguen esta última opción. Si decide dejar que Adobe IO genere el par de claves, haga clic en la opción 1; a continuación, haga clic en el **[!UICONTROL Generate keypair]** botón.

   ![](assets/adobeIO4.png)

1. En la siguiente pantalla, se le pedirá que asigne un nombre al archivo zip del par de claves y que seleccione la ubicación de descarga.

Una vez descargado, puede descomprimir el archivo para mostrar las claves pública y privada. Adobe IO ya ha aplicado la clave pública al proyecto de IO de Adobe. Necesitará conservar la clave privada para más adelante; la clave privada se utilizará durante la configuración previa a la integración de la herramienta de integración.

1. Haga clic en **[!UICONTROL Next]** para continuar

   ![](assets/adobeIO5.png)

1. En la siguiente pantalla, puede seleccionar perfiles de producto para asociarlos a este proyecto. Seleccione el perfil de producto que contiene el título: El ID de inquilino de la instancia de Campaign: [!UICONTROL Administrators]

   Ejemplo: Campaign Standard - your-campaign-tenantID - Administradores

1. Haga clic en **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. En la siguiente pantalla verá los detalles del nuevo proyecto de IO de Adobe. Haga clic en **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** en la lista desplegable .

   ![](assets/adobeIO7.png)

1. En la siguiente pantalla tendrá que seleccionar la API de eventos de E/S y, a continuación, hacer clic en **[!UICONTROL Next]**.

1. En la siguiente pantalla, haga clic en **[!UICONTROL Save the configured API]**.  Volverá a la pantalla de detalles del proyecto.

1. Ahora haga clic en **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** de la lista desplegable, como lo hizo anteriormente.

1. En la siguiente pantalla tendrá que seleccionar la API de administración de E/S y hacer clic en **[!UICONTROL Next]**.

1. En la siguiente pantalla, haga clic en **[!UICONTROL Save the configured API]**.

La configuración de preintegración en Campaign ya ha finalizado.

**Temas relacionados**

* [Configuración de Adobe IO para la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) es el siguiente paso para configurar la integración
* [Información general sobre la aplicación de autoservicio de integración](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene la lista completa de pasos para poner en marcha la integración.


* [Adobe IO: integración de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard: configuración de acceso a API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integración con Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)

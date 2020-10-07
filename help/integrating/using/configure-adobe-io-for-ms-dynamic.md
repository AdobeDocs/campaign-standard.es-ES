---
title: Configuración de Adobe IO para integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo configurar la E/S de Adobe para la integración con Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 3%

---


# Configuración de Adobe IO para integración con Microsoft Dynamics 365

Active los datos de CRM en la comunicación entre canales: aprenda los pasos necesarios durante la configuración previa a la integración para crear un nuevo proyecto de E/S de Adobe y configurarlo para la integración de Microsoft Dynamics 365.

## Información general

La integración de Adobe Campaign Standard - Microsoft Dynamics 365 se describe en [esta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Antes de realizar la configuración previa a la integración en este artículo, se da por hecho que ya ha sido aprovisionado y tiene acceso de administrador a la instancia de Campaign Standard de su organización.  Si esto no ha sucedido, deberá ponerse en contacto con el Servicio de atención al cliente de Adobe para completar el aprovisionamiento de Campañas.

>[!CAUTION]
>
>Un administrador debe realizar los pasos que se describen a continuación.

## Configuración

Deberá crear un nuevo proyecto de E/S de Adobe y configurarlo para la integración.

### Crear un nuevo proyecto

Para lograrlo, siga el procedimiento siguiente:

1. Vaya a la consola [de E/S de](https://console.adobe.io/home#) Adobe y seleccione el ID de organización de IMS de Adobe en el menú desplegable situado en la parte superior derecha de la pantalla.

1. A continuación, haga clic en **[!UICONTROL Create new project]** debajo de **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. En **[!UICONTROL Get started with your new project]**, haga clic en **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleccione la API de Adobe Campaign (es posible que deba desplazarse hacia abajo) y haga clic en **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. En la siguiente pantalla tendrá la opción de cargar su propia clave pública o permitir que Adobe IO genere el par de claves por usted. Estas instrucciones seguirán esta última opción. Si decide permitir que Adobe IO genere el par de claves, haga clic en la opción 1; a continuación, haga clic en el **[!UICONTROL Generate keypair]** botón.

   ![](assets/adobeIO4.png)

1. En la siguiente pantalla se le pedirá que asigne un nombre al archivo zip del par de claves y que seleccione la ubicación de descarga del mismo.

Una vez descargado, puede descomprimir el archivo para revelar las claves pública y privada. La E/S de Adobe ya ha aplicado la clave pública al proyecto de E/S de Adobe. Tendrá que conservar su clave privada para más adelante; la clave privada se utilizará durante la configuración previa a la integración de la herramienta de integración.

1. Haga clic **[!UICONTROL Next]** para continuar

   ![](assets/adobeIO5.png)

1. En la siguiente pantalla, seleccionará los perfiles de producto para asociarlos a este proyecto. Seleccione el perfil del producto que contiene el título: El ID de inquilino de la instancia de Campaña: [!UICONTROL Administrators]

   Ejemplo: Campaign Standard - su-campaña-inquilinoID - Administradores

1. Haga clic en **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. En la siguiente pantalla verá los detalles del nuevo proyecto de E/S de Adobe. Haga clic en **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** en la lista desplegable.

   ![](assets/adobeIO7.png)

1. En la siguiente pantalla tendrá que seleccionar la API de Eventos de E/S y, a continuación, hacer clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.  Volverá a la pantalla de detalles del proyecto.

1. Haga clic **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** en la lista desplegable, como lo hizo anteriormente.

1. En la siguiente pantalla, deberá seleccionar la API de administración de E/S y hacer clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.

Ya se ha completado la configuración previa a la integración en Campaña.  Continúe con la configuración [previa a la integración de Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Temas relacionados**

* [E/S de Adobe: integración de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard: configuración de acceso a API](../../api/using/setting-up-api-access.md)
* [Campaign Standard: integración de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
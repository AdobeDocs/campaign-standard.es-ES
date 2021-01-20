---
title: Configuración de Adobe IO para integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo configurar la E/S de Adobe para la integración con Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 3%

---


# Configuración de Adobe Campaign Standard y Adobe I/O para la integración de Microsoft Dynamics 365

En este artículo se explica cómo configurar Adobe Campaign Standard y Adobe I/O para que la aplicación de integración tenga acceso a los datos.

## Configurar Adobe Campaign Standard {#campaign-standard}

### Extensiones de perfil

Active &quot;Extensiones de perfil&quot; en Adobe Campaign Standard.   Esto es necesario para que los campos personalizados del recurso de Perfil se sincronicen desde Microsoft Dynamics 365.   Los pasos para habilitarlos son:

1. Vaya a Configuración -> Administración -> Desarrollo -> Publicación.
1. Haga clic en &quot;Preparar publicación&quot; para preparar una publicación.
1. Una vez finalizado el proceso de preparación, marque &quot;Crear la API de salida de Perfiles y servicios&quot; y haga clic en &quot;Publicar&quot;.

## Configuración de Adobe I/O {#adobe-io}

Adobe I/O le permite habilitar el acceso de API a Adobe Campaign Standard, así como a otros productos de Adobe.   En este artículo se explica cómo configurar Adobe I/O para que la integración de Adobe Campaign Standard con Microsoft Dynamics 365 tenga acceso a la sincronización de datos.

### Información general

Antes de realizar la configuración previa a la integración en este artículo, se da por hecho que ya ha sido aprovisionado y tiene acceso de administrador a la instancia de Campaign Standard de su organización.  Si esto no ha sucedido, deberá ponerse en contacto con el Servicio de atención al cliente de Adobe para completar el aprovisionamiento de Campañas.

>[!CAUTION]
>
>Un administrador debe realizar los pasos que se describen a continuación.

### Configuración

Deberá crear un nuevo proyecto de E/S de Adobe y configurarlo para la integración.

#### Crear un nuevo proyecto

Para lograrlo, siga el procedimiento siguiente:

1. Vaya a [Consola de E/S de Adobe](https://console.adobe.io/home#) y seleccione el identificador de organización de IMS de Adobe en el menú desplegable en la parte superior derecha de la pantalla.

1. A continuación, haga clic en **[!UICONTROL Create new project]** en **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. En **[!UICONTROL Get started with your new project]**, haga clic en **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Seleccione la API de Adobe Campaign (es posible que deba desplazarse hacia abajo) y haga clic en **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. En la siguiente pantalla tendrá la opción de cargar su propia clave pública o permitir que Adobe IO genere el par de claves por usted. Estas instrucciones seguirán esta última opción. Si decide permitir que Adobe IO genere el par de claves, haga clic en la opción 1; a continuación, haga clic en el botón **[!UICONTROL Generate keypair]**.

   ![](assets/adobeIO4.png)

1. En la siguiente pantalla se le pedirá que asigne un nombre al archivo zip del par de claves y que seleccione la ubicación de descarga del mismo.

Una vez descargado, puede descomprimir el archivo para revelar las claves pública y privada. La E/S de Adobe ya ha aplicado la clave pública al proyecto de E/S de Adobe. Tendrá que conservar su clave privada para más adelante; la clave privada se utilizará durante la configuración previa a la integración de la herramienta de integración.

1. Haga clic **[!UICONTROL Next]** para continuar

   ![](assets/adobeIO5.png)

1. En la siguiente pantalla, seleccionará los perfiles de producto para asociarlos a este proyecto. Seleccione el perfil del producto que contiene el título: El ID de inquilino de la instancia de Campaña: [!UICONTROL Administrators]

   Ejemplo: Campaign Standard - su-campaña-inquilinoID - Administradores

1. Haga clic en **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. En la siguiente pantalla verá los detalles del nuevo proyecto de E/S de Adobe. Haga clic **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** en la lista desplegable.

   ![](assets/adobeIO7.png)

1. En la siguiente pantalla tendrá que seleccionar la API de Eventos de E/S y luego hacer clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.  Volverá a la pantalla de detalles del proyecto.

1. Ahora haga clic **[!UICONTROL Add to Project]** en la parte superior izquierda de la pantalla y seleccione **API** en la lista desplegable, como lo hizo anteriormente.

1. En la siguiente pantalla tendrá que seleccionar la API de administración de E/S y hacer clic en **[!UICONTROL Next]**.

1. En la pantalla siguiente, haga clic en **[!UICONTROL Save the configured API]**.

Ya se ha completado la configuración previa a la integración en Campaña.

**Temas relacionados**

* [La configuración de la ](../../integrating/using/d365-acs-configure-adobe-io.md) integración de Adobe IO para Microsoft Dynamics 365 es el siguiente paso en la configuración de la integración
* [La ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) descripción general de la aplicación de autoservicio de integración contiene la lista completa de los pasos para lograr que la integración se ponga en marcha.


* [E/S de Adobe: integración de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard: configuración de acceso a API](../../api/using/setting-up-api-access.md)
* [Campaign Standard: integración de Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)

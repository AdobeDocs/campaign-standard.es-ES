---
title: Configuración de Microsoft Dynamics 365 para integración con Campaign
description: Obtenga información sobre cómo configurar Microsoft Dynamics 365 para la integración de Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 1%

---

# Configuración de Microsoft Dynamics 365 para la integración con Adobe Campaign Standard

Obtenga información sobre cómo configurar la integración con Microsoft Dynamics 365 y activar los datos CRM en la comunicación entre canales con Adobe Campaign Standard.

## Información general

La descripción general de la integración de Adobe Campaign Standard con Microsoft Dynamics 365 se describe en [esta página](../../integrating/using/d365-acs-get-started.md).

Será necesario configurar varias aplicaciones para habilitar la integración. Sin embargo, este artículo se centrará en los pasos necesarios en Dynamics 365.

## Requisitos previos

Antes de realizar la configuración de preintegración en este documento, se da por hecho que ya ha aprovisionado y tiene acceso de administrador a la instancia de Microsoft Dynamics 365 de su organización.  Si esto no ha sucedido, tendrá que ponerse en contacto con el servicio de asistencia al cliente de Microsoft para completar el aprovisionamiento de Dynamics 365.

Si está configurando la integración para entornos de ensayo y producción, debe realizar los pasos siguientes tanto para las instancias de ensayo como de producción de Dynamics 365. Algunas instrucciones a continuación varían ligeramente dependiendo de si está configurando una instancia de Dynamics 365 de fase o producción (por ejemplo, para la instancia de producción, seleccione &quot;prod&quot; para `<stage or prod>`)

## Configuración de aplicaciones y permisos

Un token de acceso de OAuth permite que la herramienta de integración se autentique con la instancia de Microsoft Dynamics 365 a través de API web para anunciar eventos de experiencia de Campaign Standard en la vista de cronología de la interfaz de Microsoft Dynamics 365.

Los pasos principales se describen en el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para generar el token de acceso de OAuth, siga los pasos descritos a continuación.

### Registrar una nueva aplicación {#register-a-new-app}

1. Bajo el inicio de sesión del administrador, inicie sesión en portal.azure.com.

1. Haga clic en **[!UICONTROL Azure Active Directory]** en el menú de la izquierda; a continuación, haga clic en **[!UICONTROL App registrations]** en el submenú que aparece.

1. Haga clic en **[!UICONTROL New registration]** en la parte superior de la pantalla.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Complete la pantalla de registro de la aplicación:

   * Nombre: adobe campaign `<stage or prod>`
   * Tipo de cuenta compatible: **[!UICONTROL Accounts in this organizational directory only]** (valor predeterminado)

Para obtener más información sobre la creación de una nueva aplicación, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Microsoft Azure Directory asigna un ID de aplicación (cliente) único a su aplicación. Necesitará este ID más adelante al configurar Dynamics 365, así como al configurar la herramienta de integración.

### Generar secreto de cliente {#generate-a-client-secret}

1. En la pantalla de información general de la aplicación, en el submenú de la izquierda, haga clic en **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Introduzca una descripción, establezca la duración y haga clic en **[!UICONTROL OK]**.

Se ha creado el secreto de cliente. Mantenga el valor temporalmente para completar la configuración previa a la integración de la herramienta de integración.

>[!CAUTION]
>
>Mantenga este valor tal y como lo necesitará para completar la configuración previa a la integración de la herramienta de integración. No se puede recuperar posteriormente.


### Permisos de configuración

1. Desde esta pantalla o la pantalla de información general de la aplicación, haga clic en **[!UICONTROL API permissions]** en el submenú de la izquierda.  Después de hacer clic en **[!UICONTROL Add a permission]**, debe seleccionar **[!UICONTROL Dynamics CRM]** en el menú.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. A continuación, marque la casilla **[!UICONTROL user_impersonation]** y haga clic en el botón **[!UICONTROL Add permissions]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Para obtener más información sobre la configuración de permisos, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creación del usuario de la aplicación

Este nuevo usuario es un usuario genérico. La aplicación lo usará: este usuario realizará cualquier cambio en Microsoft Dynamics 365 mediante la API. Para crearlo, siga los pasos a continuación:

1. Vaya a la instancia de Dynamics 365 e inicie sesión como administrador.

1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En el banner superior, haga clic en la lista desplegable junto a **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Security > Users]**.

1. Haga clic en el menú desplegable y vaya a **[!UICONTROL Application Users]**. Haga clic en **[!UICONTROL New]**.

1. Asegúrese de que la lista desplegable junto al icono del usuario indica **[!UICONTROL USER:APPLICATION USER]**.

   Complete la pantalla del nuevo usuario.  Sugerencias de parámetros:

   * **[!UICONTROL User Name]** (correo electrónico): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (p. ej., adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID de la aplicación que registró en Azure AD (esto es obligatorio)
   * Puede dejar en blanco **[!UICONTROL Application ID URI]** y **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API de Adobe  `<stage or prod>`
   * **[!UICONTROL Email]**: igual que  **[!UICONTROL User Name]** (o el correo electrónico del administrador si lo desea)

   Para obtener más información sobre la creación de usuarios de la aplicación, consulte [esta sección](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Haga clic en el icono de usuario y cargue un icono de Adobe Campaign; este es el icono que se mostrará en la vista Cronología cuando aparezcan nuevos eventos de Adobe en Dynamics 365.

1. Abra la lista de funciones de usuario haciendo clic en **[!UICONTROL MANAGE ROLES]** en la cinta superior.

1. Desplácese hacia abajo y seleccione **[!UICONTROL System administrator]** acceso para este usuario.

1. Haga clic en **[!UICONTROL OK]**.

### Obtención del ID del inquilino {#get-the-tenant-id}

Siga las instrucciones [de esta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para encontrar su ID de inquilino.  Necesitará este ID durante la configuración previa a la integración en la herramienta de integración.

## Campaign Standard de instalación para Microsoft Dynamics 365 {#install-appsource-app}

Para integrar la aplicación Dynamics 365 en el entorno de Campaign Standard, siga los pasos a continuación:

1. Vaya al siguiente vínculo: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) y busque _Adobe Campaign para Dynamics 365_ en la barra de búsqueda.
Alternativamente, puede navegar a este [vínculo](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Siga las instrucciones para instalar la aplicación para su instancia de Dynamics 365.
1. Una vez instalada, vaya a la instancia de Dynamics 365 e inicie sesión como administrador.
1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En el banner superior, haga clic en la lista desplegable junto a **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Processes]** en **[!UICONTROL Process Center]**.
1. Busque la tarea **[!UICONTROL Adobe Campaign Email Bounce]** y haga clic en ella.
1. En la pestaña **[!UICONTROL Administration]**, cambie el propietario al usuario de la aplicación de API de Adobe creado anteriormente haciendo clic en **[!UICONTROL Actions]** en la cinta superior y, a continuación, seleccione la opción **[!UICONTROL Assign to another User]**, seleccione **[!UICONTROL Adobe API application user]** en la lista desplegable que desee asignar.
1. Reactive el proceso.
1. Haga lo mismo para la tarea **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Si en cualquier momento desea desactivar estos procesos, puede hacerlo en esta **[!UICONTROL Processes]** pantalla.

**Temas relacionados**

* [La configuración de Adobe IO para la ](../../integrating/using/d365-acs-configure-adobe-io.md) integración con Microsoft Dynamics 365 es el siguiente paso para configurar la integración
* [Introducción a la aplicación de integración de autoservicio ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene la lista completa de pasos para poner en marcha la integración.

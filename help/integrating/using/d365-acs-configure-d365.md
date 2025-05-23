---
title: Configuración de Microsoft Dynamics 365 para integración con Campaign
description: Obtenga información sobre cómo configurar la integración de Microsoft Dynamics 365 para Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# Configuración de Microsoft Dynamics 365 para la integración con Adobe Campaign Standard

Obtenga información sobre cómo configurar la integración de Microsoft Dynamics 365 y activar los datos de CRM en la comunicación entre canales con Adobe Campaign Standard.

## Información general

La descripción general de la integración de Adobe Campaign Standard con Microsoft Dynamics 365 se describe en [esta página](../../integrating/using/d365-acs-get-started.md).

Se deberán configurar varias aplicaciones para habilitar la integración; sin embargo, este artículo se centrará en los pasos necesarios dentro de Dynamics 365.

## Requisitos previos

Antes de realizar la configuración de preintegración en este documento, se da por hecho que ya se ha aprovisionado y tiene acceso de administrador a la instancia de Microsoft Dynamics 365 de su organización.  Si no es así, tendrá que ponerse en contacto con el servicio de atención al cliente de Microsoft para completar el aprovisionamiento de Dynamics 365.

Si está configurando la integración para los entornos de ensayo y producción, deberá realizar los pasos siguientes para las instancias de Dynamics 365 de ensayo y producción. Algunas instrucciones a continuación varían ligeramente según si está configurando una instancia de Dynamics 365 de fase o producción (por ejemplo, para la instancia de producción, seleccione &quot;prod&quot; para `<stage or prod>`)

## Configuración de la aplicación y los permisos

Un token de acceso de OAuth permite a la herramienta de integración autenticarse con la instancia de Microsoft Dynamics 365 a través de las API web para publicar eventos de experiencia del Campaign Standard en la vista de cronología de la interfaz de Microsoft Dynamics 365.

Los pasos principales se describen en el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/34835?captions=spa)

Para generar el token de acceso de OAuth, siga los pasos descritos a continuación.

### Registrar una nueva aplicación {#register-a-new-app}

1. En su inicio de sesión como administrador, inicie sesión en [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Haga clic en **[!UICONTROL Azure Active Directory]** en el menú de la izquierda; a continuación, haga clic en **[!UICONTROL App registrations]** en el submenú que aparece.

1. Haga clic en **[!UICONTROL New registration]** en la parte superior de la pantalla.

1. Rellene la pantalla de registro de la aplicación:

   * Nombre: adobe campaign `<stage or prod>`
   * Tipo de cuenta admitido: **[!UICONTROL Accounts in this organizational directory only]** (valor predeterminado)

Para obtener más información sobre cómo crear una aplicación nueva, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory asigna un ID único de aplicación (cliente) a su aplicación. Necesitará este ID más adelante en la configuración de Dynamics 365, así como al configurar la herramienta de integración.

### Generar secreto de cliente {#generate-a-client-secret}

1. En la pantalla de información general de la aplicación, en el submenú de la izquierda, haga clic en **[!UICONTROL Certificates and Secrets > New client secret]**

1. Escriba una descripción, establezca la duración y haga clic en **[!UICONTROL OK]**.

Se ha creado el secreto de cliente. Conserve el valor temporalmente para completar la configuración previa a la integración de la herramienta de integración.

>[!CAUTION]
>
>Mantenga este valor tal como lo necesita para completar la configuración previa a la integración de la herramienta de integración. No se puede recuperar posteriormente.


### Permisos de configuración

1. Desde esta pantalla o desde la pantalla de información general de la aplicación, haga clic en **[!UICONTROL API permissions]** en el submenú de la izquierda.  Después de hacer clic en **[!UICONTROL Add a permission]**, debe seleccionar **[!UICONTROL Dynamics CRM]** en el menú.

1. Luego marque la casilla de **[!UICONTROL user_impersonation]** y haga clic en el botón **[!UICONTROL Add permissions]**.

Para obtener más información sobre la configuración de permisos, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Creación del usuario de la aplicación

Este nuevo usuario es un usuario genérico. La utilizará la aplicación: cualquier cambio en Microsoft Dynamics 365 mediante la API lo realizará este usuario. Para crearlo, siga los pasos a continuación:

1. Vaya a la instancia de Dynamics 365 e inicie sesión como administrador.

1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En el banner superior, haga clic en el menú desplegable situado junto a **[!UICONTROL Settings]** y luego haga clic en **[!UICONTROL Security > Users]**.

1. Haga clic en el menú desplegable para ir a **[!UICONTROL Application Users]**. Haga clic en **[!UICONTROL New]**.

1. Asegúrese de que la lista desplegable junto al icono de usuario indica **[!UICONTROL USER:APPLICATION USER]**.

   Rellene la pantalla del nuevo usuario.  Sugerencias de parámetros:

   * **[!UICONTROL User Name]** (correo electrónico): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (por ejemplo, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID de la aplicación que registró en Azure AD (obligatorio)
   * Puede dejar en blanco **[!UICONTROL Application ID URI]** y **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API de Adobe `<stage or prod>`
   * **[!UICONTROL Email]**: igual que **[!UICONTROL User Name]** (o correo electrónico del administrador si lo desea)

   Para obtener más información sobre la creación de usuarios de la aplicación, consulte [esta sección](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Haga clic en el icono de usuario y cargue un icono de Adobe Campaign; este es el icono que se mostrará en la vista Cronología cuando aparezcan nuevos eventos de Adobe en Dynamics 365.

1. Abra la lista de funciones de usuario al hacer clic en **[!UICONTROL MANAGE ROLES]** en la cinta de opciones superior.

1. Desplácese hacia abajo y seleccione **[!UICONTROL System administrator]** acceso para este usuario.

1. Haga clic en **[!UICONTROL OK]**.

### Obtener el ID de inquilino {#get-the-tenant-id}

Siga las instrucciones [de esta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para encontrar su ID de inquilino.  Necesitará este ID durante la configuración previa a la integración en la herramienta de integración.

## Campaign Standard de instalación para Microsoft Dynamics 365 {#install-appsource-app}

Para integrar la aplicación de Dynamics 365 en su entorno de Campaign Standard, siga los pasos a continuación:

1. Vaya a [Aplicaciones empresariales de Microsoft](https://appsource.microsoft.com/en-us/marketplace/apps) y busque _Adobe Campaign Standard_ en la barra de búsqueda.
También puede navegar a este [vínculo](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}.
1. Siga las instrucciones para instalar la aplicación en la instancia de Dynamics 365.
1. Una vez instalada, vaya a la instancia de Dynamics 365 e inicie sesión como administrador.
1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En el banner superior, haga clic en el menú desplegable situado junto a **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Processes]** en **[!UICONTROL Process Center]**.
1. Busque **[!UICONTROL Adobe Campaign Email Bounce]** tarea y haga clic en ella.
1. En la ficha **[!UICONTROL Administration]**, cambie el propietario al usuario de la aplicación API de Adobe creado anteriormente haciendo clic en **[!UICONTROL Actions]** en la cinta de opciones superior, luego seleccione la opción **[!UICONTROL Assign to another User]** y seleccione **[!UICONTROL Adobe API application user]** en el menú desplegable para asignar.
1. Reactive el proceso.
1. Haga lo mismo para la tarea **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Si en cualquier momento desea desactivar estos procesos, puede hacerlo en esta pantalla de **[!UICONTROL Processes]**.

**Temas relacionados**

* [Configurar Adobe Developer para la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) es el siguiente paso para configurar la integración
* [Introducción a la aplicación de integración de autoservicio](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contiene la lista completa de pasos para poner en marcha la integración.

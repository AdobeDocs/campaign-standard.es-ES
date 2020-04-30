---
title: Configuración de Microsoft Dynamics 365 para la integración de Campañas
description: Obtenga información sobre cómo configurar Microsoft Dynamics 365 para la integración de Campañas.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# Configuración de Microsoft Dynamics 365 para la integración de Campañas

Obtenga información sobre cómo configurar la integración de Microsoft Dynamics 365 y activar los datos CRM en la comunicación entre canales con Adobe Campaign Standard.

## Información general

Adobe Campaign Standard: la integración de Microsoft Dynamics 365 se describe en [esta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Tres sistemas que deben aprovisionarse para esta integración:

1. Adobe Campaign Standard: [Más información](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales: se describe a continuación
1. Unifi: [Más información](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

Una vez aprovisionados, estos sistemas deben ser configurados por un administrador.

En este artículo se destacan los pasos necesarios para permitir que un cliente utilice la integración de Adobe Campaign Standard - Microsoft Dynamics 365 en el lado de Microsoft Dynamics 365 durante el postaprovisionamiento.

## Requisitos previos

Antes de realizar los pasos posteriores al aprovisionamiento en este documento, se da por hecho que ya ha aprovisionado y tiene acceso de administrador a la instancia de Microsoft Dynamics 365 de su organización.  Si esto no ha sucedido, deberá ponerse en contacto con el servicio de asistencia al cliente de Microsoft para completar el aprovisionamiento de Dynamics 365.

## Configuración de aplicaciones y permisos

Un token de acceso OAuth permite que Unifi se autentique con la instancia de Microsoft Dynamics 365 mediante API web para publicar eventos de experiencia de Campaign Standard en la vista de línea de tiempo de la interfaz de Microsoft Dynamics 365.

Los pasos principales se describen en el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para generar el token de acceso OAuth, siga los pasos que se describen a continuación.

### Registrar una nueva aplicación

1. Bajo el inicio de sesión del administrador, inicie sesión en portal.azure.com.

1. Haga clic en **[!UICONTROL Azure Active Directory]** en el menú del lado izquierdo; a continuación, haga clic **[!UICONTROL App registrations]** en el submenú que aparece.

1. Haga clic **[!UICONTROL New registration]** en en la parte superior de la pantalla.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Complete la pantalla de registro de la aplicación:

   * Nombre: campaña de Adobe
   * Tipo de cuenta admitido: **[!UICONTROL Accounts in this organizational directory only]** (valor predeterminado)

For more information about creating a new application, refer to [this section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD asigna un ID de aplicación (cliente) único a su aplicación. Necesitará este ID más adelante al configurar Dynamics 365, así como al realizar los pasos de postaprovisionamiento de Unifi.

### Generar secreto de cliente

1. En la pantalla de información general de la aplicación, en el submenú de la izquierda, haga clic en **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Introduzca una descripción, defina la duración y haga clic en **[!UICONTROL OK]**.

Se ha creado el secreto de cliente.  Conservar el valor para completar los pasos posteriores al aprovisionamiento de Unifi.

>[!CAUTION]
>
>Mantenga este valor como lo necesitará para completar el paso posterior al aprovisionamiento de Unifi. No se puede recuperar posteriormente.

Para obtener más información sobre la generación de un secreto de cliente, consulte esta sección.

### Permisos de configuración

1. En esta pantalla o en la pantalla de información general de la aplicación, haga clic en **[!UICONTROL API permissions]** en el submenú de la izquierda.  Después de hacer clic **[!UICONTROL Add a permission]**, debe seleccionar **[!UICONTROL Dynamics CRM]** en el menú.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. A continuación, marque la casilla de verificación **[!UICONTROL user_impersonation]** y haga clic en el **[!UICONTROL Add permissions]** botón.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Para obtener más información sobre la configuración de permisos, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creación del usuario de la aplicación

Este nuevo usuario es un usuario genérico. Será utilizado por la aplicación: este usuario realizará cualquier cambio en Microsoft Dynamics 365 mediante la API. Para crearla, siga los pasos a continuación:

1. Vaya a la instancia de Dynamics 365 e inicie sesión como administrador.

1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En la pancarta superior, haga clic en la lista desplegable situada junto a **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Security > Users]**.

1. Haga clic en el menú desplegable para ir a **[!UICONTROL Application Users]**. Haga clic **[!UICONTROL New]**.

1. Asegúrese de que el menú desplegable situado junto al icono del usuario indica **[!UICONTROL USER:APPLICATION USER]**.

   Complete la pantalla del nuevo usuario.  Sugerencias de parámetros:

   * **[!UICONTROL User Name]** (correo electrónico): adobeapi@`<hostname>`, donde `<hostname>` es el nombre de host de la instancia de Dynamics 365
   * **[!UICONTROL Application ID]**:: ID de la aplicación que registró en Azure AD (esto es obligatorio)
   * Puede dejar en blanco **[!UICONTROL Application ID URI]** y **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:: Adobe API
   * **[!UICONTROL Email]**:: igual que **[!UICONTROL User Name]** (o el correo electrónico del administrador si lo desea)
   Para obtener más información sobre la creación de usuarios de la aplicación, consulte [esta sección](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Haga clic en el icono de usuario y cargue un icono de Adobe Campaign; este es el icono que se mostrará en la vista Línea de tiempo cuando aparezcan nuevos eventos de Adobe en Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Abra la lista de funciones de usuario haciendo clic en **[!UICONTROL MANAGE ROLES]** en la cinta superior.

1. Desplácese hacia abajo y seleccione **[!UICONTROL System administrator]** acceso para este usuario.

1. Haga clic **[!UICONTROL OK]**.

### Obtención del ID del inquilino

Siga las instrucciones del siguiente vínculo para encontrar su ID de inquilino.  Necesitará este ID durante el postaprovisionamiento en Unifi: [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id).

## Instalar Campaign Standard para Microsoft Dynamics 365

Para integrar la aplicación Dynamics 365 en el entorno de Campaign Standard, siga los pasos a continuación:

1. Vaya al siguiente vínculo: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) y busque _Adobe Campaign para Dynamics 365_ en la barra de búsqueda.
También puede navegar a este [vínculo](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Siga las instrucciones para instalar la aplicación para su instancia de Dynamics 365.
1. Una vez instalada, vaya a la instancia de Dynamics 365 e inicie sesión como administrador.
1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En la pancarta superior, haga clic en la lista desplegable al lado de **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Processes]** debajo de **[!UICONTROL Process Center]**.
1. Busque la **[!UICONTROL Adobe Campaign Email Bounce]** tarea y haga clic en ella.
1. En la **[!UICONTROL Administration]** ficha, cambie el propietario al usuario de la aplicación API de Adobe creado anteriormente haciendo clic **[!UICONTROL Actions]** en la cinta superior y, a continuación, seleccione **[!UICONTROL Assign to another User]** , seleccione **[!UICONTROL Adobe API application user]** en la lista desplegable que desee asignar.
1. Reactive el proceso.
1. Haga lo mismo con la **[!UICONTROL Adobe Campaign Email Click]** tarea.

>[!NOTE]
>
>Si en cualquier momento desea desactivar estos procesos, puede hacerlo en esta **[!UICONTROL Processes]** pantalla.

Una vez finalizada esta configuración, puede configurar la configuración Unifi. Para obtener más información, consulte [esta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

**Temas relacionados**

* [Campaign Standard: integración de Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuración de la integración de E/S de Adobe para Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Configurar Unifi para Campaña: integración con Microsoft Dynamics 365](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

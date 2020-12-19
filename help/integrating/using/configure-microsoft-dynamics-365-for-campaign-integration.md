---
solution: Campaign Standard
product: campaign
title: Configuración de Microsoft Dynamics 365 para integración con Campaign
description: Obtenga información sobre cómo configurar Microsoft Dynamics 365 para la integración de Campañas.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# Configuración de Microsoft Dynamics 365 para integración con Campaign

Obtenga información sobre cómo configurar la integración de Microsoft Dynamics 365 y activar los datos de CRM en la comunicación entre canales con Adobe Campaign Standard.

## Información general

La integración de Adobe Campaign Standard - Microsoft Dynamics 365 se describe en [esta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Tres sistemas que deben aprovisionarse para esta integración:

1. Adobe Campaign Standard - [Más información](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales: se describe a continuación
1. Herramienta de integración: propiedad del equipo de consultoría de Adobe

Una vez aprovisionados, estos sistemas deben ser configurados por un administrador.

En este artículo se destacan los pasos necesarios para permitir que un cliente utilice la integración Adobe Campaign Standard - Microsoft Dynamics 365 en el lado de Microsoft Dynamics 365 durante la configuración previa a la integración.

>[!NOTE]
>
>Hasta que la interfaz de usuario de la herramienta de autoservicio esté disponible más adelante este año, el equipo de integración le ayudará a configurar la integración.

## Requisitos previos

Antes de realizar la configuración previa a la integración en este documento, se da por hecho que ya ha aprovisionado y tiene acceso de administrador a la instancia de Microsoft Dynamics 365 de su organización.  Si esto no ha sucedido, deberá ponerse en contacto con el servicio de asistencia al cliente de Microsoft para completar el aprovisionamiento de Dynamics 365.

Si está configurando la integración tanto para entornos de ensayo como de producción, deberá realizar los pasos siguientes para las instancias de ensayo y producción de Dynamics 365. Algunas instrucciones a continuación varían ligeramente en función de si está configurando una etapa o una instancia de producción de Dynamics 365 (por ejemplo, para la instancia de producción, seleccione &quot;prod&quot; para `<stage or prod>`)

## Configuración de aplicaciones y permisos

Un token de acceso OAuth permite que la herramienta de integración se autentique con la instancia de Microsoft Dynamics 365 mediante API web para publicar eventos de experiencia de Campaign Standard en la vista de línea de tiempo de la interfaz de Microsoft Dynamics 365.

Los pasos principales se describen en el siguiente vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para generar el token de acceso OAuth, siga los pasos que se describen a continuación.

### Registrar una nueva aplicación

1. Bajo el inicio de sesión del administrador, inicie sesión en portal.azure.com.

1. Haga clic en **[!UICONTROL Azure Active Directory]** en el menú de la izquierda; a continuación, haga clic en **[!UICONTROL App registrations]** en el submenú que aparece.

1. Haga clic **[!UICONTROL New registration]** en la parte superior de la pantalla.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Complete la pantalla de registro de la aplicación:

   * Nombre: campaña de Adobe `<stage or prod>`
   * Tipo de cuenta admitido: **[!UICONTROL Accounts in this organizational directory only]** (valor predeterminado)

Para obtener más información sobre cómo crear una nueva aplicación, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD asigna un ID de aplicación (cliente) único a su aplicación. Necesitará este ID más adelante al configurar Dynamics 365, así como al realizar la configuración previa a la integración para la herramienta de integración.

### Generar secreto de cliente

1. En la pantalla de información general de la aplicación, en el submenú de la izquierda, haga clic en **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Escriba una descripción, establezca la duración y haga clic en **[!UICONTROL OK]**.

Se ha creado el secreto de cliente. Mantenga el valor temporalmente para completar la configuración previa a la integración de la herramienta de integración.

>[!CAUTION]
>
>Mantenga este valor tal y como lo necesitará para completar la configuración previa a la integración de la herramienta de integración. No se puede recuperar posteriormente.


### Permisos de configuración

1. En esta pantalla o en la pantalla de información general de la aplicación, haga clic en **[!UICONTROL API permissions]** en el submenú de la izquierda.  Después de hacer clic en **[!UICONTROL Add a permission]**, debe seleccionar **[!UICONTROL Dynamics CRM]** en el menú.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. A continuación, marque la casilla **[!UICONTROL user_impersonation]** y haga clic en el botón **[!UICONTROL Add permissions]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Para obtener más información sobre la configuración de permisos, consulte [esta sección](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Creación del usuario de la aplicación

Este nuevo usuario es un usuario genérico. Será utilizado por la aplicación: este usuario realizará cualquier cambio en Microsoft Dynamics 365 mediante la API. Para crearla, siga los pasos a continuación:

1. Vaya a la instancia de Dynamics 365 e inicie sesión como administrador.

1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En la pancarta superior, haga clic en la lista desplegable al lado de **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Security > Users]**.

1. Haga clic en el menú desplegable para ir a **[!UICONTROL Application Users]**. Haga clic en **[!UICONTROL New]**.

1. Asegúrese de que la lista desplegable junto al icono de usuario diga **[!UICONTROL USER:APPLICATION USER]**.

   Complete la pantalla del nuevo usuario.  Sugerencias de parámetros:

   * **[!UICONTROL User Name]** (correo electrónico): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (por ejemplo: adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**:: ID de la aplicación que registró en Azure AD (esto es obligatorio)
   * Puede dejar en blanco **[!UICONTROL Application ID URI]** y **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**:: API de Adobe  `<stage or prod>`
   * **[!UICONTROL Email]**:: igual que  **[!UICONTROL User Name]** (o el correo electrónico del administrador si lo desea)

   Para obtener más información sobre la creación de usuarios de la aplicación, consulte [esta sección](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Haga clic en el icono de usuario y cargue un icono de Adobe Campaign; este es el icono que se mostrará en la vista Línea de tiempo cuando aparezcan nuevos eventos de Adobe en Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Abra la lista de funciones de usuario haciendo clic en **[!UICONTROL MANAGE ROLES]** en la cinta superior.

1. Desplácese hacia abajo y seleccione **[!UICONTROL System administrator]** acceso para este usuario.

1. Haga clic en **[!UICONTROL OK]**.

### Obtención del ID del inquilino

Siga las instrucciones [de esta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para encontrar su ID de inquilino.  Necesitará este ID durante la configuración previa a la integración en la herramienta de integración.

## Instalar Campaign Standard para Microsoft Dynamics 365

Para integrar la aplicación Dynamics 365 en el entorno de Campaign Standard, siga los pasos a continuación:

1. Vaya al siguiente vínculo: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) y busque _Adobe Campaign para Dynamics 365_ en la barra de búsqueda.
También puede navegar a este [vínculo](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Siga las instrucciones para instalar la aplicación para su instancia de Dynamics 365.
1. Una vez instalada, vaya a la instancia de Dynamics 365 e inicie sesión como administrador.
1. Haga clic en el icono de engranaje en la esquina superior derecha y haga clic en **[!UICONTROL Advanced Settings]**. En la pancarta superior, haga clic en la lista desplegable junto a **[!UICONTROL Settings]**, haga clic en **[!UICONTROL Processes]** en **[!UICONTROL Process Center]**.
1. Busque la tarea **[!UICONTROL Adobe Campaign Email Bounce]** y haga clic en ella.
1. En la ficha **[!UICONTROL Administration]**, cambie el propietario al usuario de la aplicación API de Adobe creado anteriormente haciendo clic en **[!UICONTROL Actions]** desde la cinta superior y, a continuación, seleccione la opción **[!UICONTROL Assign to another User]**, seleccione **[!UICONTROL Adobe API application user]** en la lista desplegable que desee asignar.
1. Reactive el proceso.
1. Haga lo mismo con la tarea **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Si en cualquier momento desea desactivar estos procesos, puede hacerlo en esta **[!UICONTROL Processes]** pantalla.

**Temas relacionados**

* [Campaign Standard: integración de Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuración de Adobe IO para integración con Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)

---
title: Administración de usuarios
seo-title: Administración de usuarios
description: Administración de usuarios
seo-description: 'Los usuarios de Adobe Campaign tienen funciones específicas. Descubrir los tipos de usuarios principales. '
page-status-flag: no activado nunca
uuid: 8 c 4 cc 74 a -815 f -4815-af 66-a 7 c 21 bc 754 f 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: usuarios y seguridad
discoiquuid: 08 c 8712 a -0066-4 b 8 b -8471-2656 b 8 fb 23 ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ab329af94dc4e28651aaef17f4588d894fb48b74

---


# Users management{#users-management}

## About users {#about-users}

Adobe Campaign permite asignar un conjunto de funciones a los usuarios para definir qué parte de la interfaz puede tener acceso.

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Los administradores pueden administrar usuarios desde la Consola de administración. A continuación, los usuarios se sincronizan automáticamente con Adobe Campaign. For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Temas relacionados:**

* [Administración de vídeo de permisos](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) de usuario
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Lista de autorizaciones](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Type of users {#type-of-users}

Esta segmentación de usuarios no es obligatoria, es sólo una representación del uso más común de Adobe Campaign.

Esta sección le ayudará a comprender los tipos principales de usuarios de Adobe Campaign. En este caso, no se introducirán todas las funciones específicas que un usuario pueda albergar (iniciar envíos, exportar, preparar entregas, etc.). For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

Preferiremos centrarse en cómo se dividen las distintas tareas de Adobe Campaign entre tres tipos de usuarios principales:

* [Administradores funcionales](../../administration/using/users-management.md#functional-administrators): entre todos los usuarios de su organización, son los más técnicos.
* [Usuarios avanzados](../../administration/using/users-management.md#advanced-users): configuran todos los elementos que los especialistas en marketing necesitan enviar y monitorean sus envíos.
* [Usuarios básicos](../../administration/using/users-management.md#basic-users): son los especialistas en mercadotecnia que personalizan, envían y monitorean sus campañas.

>[!NOTE]
>
>Los administradores funcionales son diferentes de los administradores técnicos de Adobe. Los administradores técnicos de Adobe tienen una función interna de Adobe que ningún cliente puede utilizar. Administran el aprovisionamiento de instancias, el alojamiento, la supervisión y supervisión de infraestructuras, la solución de problemas técnicos.

### Functional administrators {#functional-administrators}

Los administradores funcionales son usuarios que pueden acceder a las partes más técnicas de la interfaz. They hold the **[!UICONTROL Administration]** role and make sure that the platform is all set up so that marketers only have to focus on delivering their campaigns.

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Administrar usuarios y permisos](../../administration/using/about-access-management.md): administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad, unidades).
* [Configure los distintos canales](../../administration/using/about-channel-configuration.md): configure los distintos canales de plataforma, así como la tipología y administración de cuarentena.
* [Configure la configuración general de la aplicación](../../administration/using/external-accounts.md): configure los distintos elementos de aplicación (cuentas externas, opciones, flujos de trabajo técnicos).
* [Desarrolle nuevas funciones para mejorar las funcionalidades integradas](../../developing/using/data-model-concepts.md): administrar sus recursos personalizados y las herramientas de diagnóstico de acceso.
* [Configure los parámetros de instancia](../../administration/using/branding.md): defina las distintas marcas y configure su configuración (logotipo, administrar seguimiento, dominio URL para acceder a las páginas de aterrizaje, etc.).
* [Exportar e importar paquetes de datos](../../automating/using/managing-packages.md): intercambiar recursos entre distintas instancias de Adobe Campaign a través de archivos XML estructurados.
* [Exportar registros](../../automating/using/exporting-logs.md) y [definir plantillas de importación](../../automating/using/defining-import-templates.md).

### Advanced users {#advanced-users}

Los usuarios avanzados son usuarios de marketing que realizan los casos de uso más técnicos en Adobe Campaign. Preconfigure todos los elementos que utilizan los comerciantes para enviar y supervisar sus envíos.

Este tipo de usuario requiere funciones más generales que los administradores funcionales, pero aún debería poder realizar algunas operaciones técnicas. To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Cree y ejecute flujos de trabajo complejos de administración de datos](../../automating/using/about-data-management-activities.md): importe, enriquezca y transforme datos para alimentar la base de datos, o exporte los datos que necesita en archivos externos para procesarlos en sus propias herramientas.
* [Administrar plantillas](../../start/using/about-templates.md): administre sus plantillas para preconfigurar determinados parámetros de sus actividades de marketing según sus necesidades.
* [Cree consultas](../../automating/using/editing-queries.md#about-query-editor) y [administre sus audiencias](../../audiences/using/about-audiences.md): crear las audiencias manualmente mediante consultas o utilizando automáticamente flujos de trabajo dedicados.
* [Realizar edición avanzada de expresiones](../../automating/using/editing-queries.md#about-query-editor): utilizar funciones avanzadas para manipular los valores utilizados para realizar consultas específicas como fechas, cadenas, campos numéricos, ordenación, etc.
* [Exportar listas](../../automating/using/exporting-lists.md) e [importar datos utilizando plantillas de importación existentes](../../automating/using/importing-data-with-import-templates.md).

### Basic users {#basic-users}

Gracias a los administradores funcionales y a los usuarios avanzados, los especialistas en marketing pueden personalizar, enviar y supervisar sus campañas sin tener que preocuparse de la configuración técnica. To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Administre programas y campañas](../../start/using/programs-and-campaigns.md): crear campañas de marketing que incluyan diferentes tipos de actividades (correos electrónicos, mensajes SMS, notificaciones push, flujos de trabajo, páginas de aterrizaje).
* Manage [profiles](../../audiences/using/about-profiles.md) and [test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md): manage the identified and test recipients that will be targeted by your deliveries. Agregue información como nombre, apellidos, información de contacto, suscripciones, correos electrónicos, etc.
* [Cree y envíe mensajes](../../sending/using/confirming-the-send.md): cree su mensaje, seleccione la audiencia, defina el contenido del mensaje y sus elementos de personalización, envíe pruebas y envíe el mensaje final a su audiencia.
* [Crear y publicar páginas de aterrizaje](../../channels/using/about-landing-pages.md): cree y administre un conjunto de servicios que desee ofrecer a sus clientes, por ejemplo, formularios de suscripción o cancelación de suscripción.
* [Cree y ejecute flujos de trabajo de campañas](../../automating/using/building-a-workflow.md): automatice los procesos de campaña mediante flujos de trabajo.
* Monitor your marketing activities through the [available reports](../../reporting/using/defining-the-report-period.md).

## Creating a user {#creating-a-user}

Para agregar un usuario a su instancia, primero debe crearlo en Admin Console antes de administrarlo en Adobe Campaign Standard.

1. From the advanced menu, select **[!UICONTROL Administration > Users & Security > Users]** and click **[!UICONTROL User administration]** to access the admin console.

   ![](assets/user_management_5.png)

1. In the **[!UICONTROL Admin Console]**, click on the **[!UICONTROL Users]** tab.

1. Click **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. From the **[!UICONTROL User details]** tab, fill in the user's details such as email address, name and surname.

   ![](assets/create_user_3.png)

1. From the **[!UICONTROL Assign products]** tab, assign one or multiple security group to your user. For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   Click **[!UICONTROL Save]** when done configuring.

   ![](assets/create_user_4.png)

Ahora se crea su usuario y debe recibir un redireccionamiento por correo electrónico a la siguiente ventana, donde el usuario tiene que establecer una contraseña y aceptar el contrato de uso. Este usuario podrá conectarse a su instancia de Adobe Campaign Standard.

![](assets/create_user_5.png)

El usuario se sincronizará con Adobe Campaign Standard en cuanto inicie sesión en su instancia.

Puede comprobar si el usuario se ha sincronizado correctamente con Adobe Campaign:

1. From the advanced menu **[!UICONTROL Administration > Users & Security > Users]** select your previously created user.

1. Update the **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** or **[!UICONTROL Regional settings]** if needed.

1. Compruebe el grupo de seguridad del usuario. Here, you can see that the user has been assigned the **[!UICONTROL Administrators]** security group.

   >[!Note]
   >
   >Los grupos de seguridad sólo pueden eliminarse o agregarse a un usuario de la Consola de administración.

   ![](assets/create_user_6.png)

1. Check **[!UICONTROL Account disabled]** if you want to deactivate this user.

1. In the **[!UICONTROL Authorized connection zone]** field, select through which way your user will connect to this instance, e.g. internal network or VPN.

1. Click **[!UICONTROL Save]**.

El usuario está listo para usar Adobe Campaign Standard.

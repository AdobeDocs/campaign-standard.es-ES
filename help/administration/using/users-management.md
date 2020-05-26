---
title: Administración de usuarios
description: 'Los usuarios de Adobe Campaign tienen funciones específicas. Descubrir los tipos de usuarios principales. '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 3%

---


# Administración de usuarios{#users-management}

## Acerca de los usuarios {#about-users}

Adobe Campaign permite asignar un conjunto de funciones a los usuarios para definir a qué parte de la interfaz pueden acceder.

Las funciones específicas y las autorizaciones correspondientes se detallan en las secciones siguientes: [comprensión de funciones](../../administration/using/list-of-roles.md) y [autorizaciones](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Los administradores pueden administrar usuarios desde la consola de administración. Los usuarios se sincronizan automáticamente con Adobe Campaign. For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

Para vista de los usuarios en Adobe Campaign, haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la esquina superior izquierda, y seleccione **[!UICONTROL Administration > Users & Security > Users]**.

Para acceder a la interfaz de administración de usuarios desde Adobe Campaign, haga clic en **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Temas relacionados:**

* [Vídeo sobre la administración de permisos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html) de usuario
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Lista de autorizaciones](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Tipo de usuarios {#type-of-users}

Esta segmentación de usuarios no es obligatoria, solo representa el uso más común de Adobes Campaign.

Esta sección le ayudará a comprender los principales tipos de usuarios de Adobe Campaign. Aquí, no vamos a entrar en todas las funciones específicas que puede tener un usuario (envíos de inicio, exportación, preparación de envíos, etc.). Para obtener más información sobre las funciones, consulte [Lista de funciones](../../administration/using/list-of-roles.md) y [Administración de grupos y páginas de usuarios](../../administration/using/managing-groups-and-users.md) .

Preferiremos centrarnos en cómo las diferentes tareas en Adobe Campaign se dividen entre tres tipos de usuarios principales:

* [Administradores](#functional-administrators)funcionales: entre todos los usuarios de su organización, son los más técnicos.
* [Usuarios](#advanced-users)avanzados: configuran todos los elementos que los especialistas en marketing necesitan para enviar y supervisar sus envíos.
* [Usuarios](#basic-users)básicos: son los especialistas en marketing que personalizan, entregan y supervisan sus campañas.

>[!NOTE]
>
>Los administradores funcionales son diferentes de los administradores técnicos de Adobe. Los administradores técnicos de Adobe tienen una función interna de Adobe que ningún cliente puede utilizar. Administran el aprovisionamiento de instancias, el alojamiento, la supervisión y supervisión de la infraestructura, la solución técnica de problemas.

### Administradores funcionales {#functional-administrators}

Los administradores funcionales son usuarios que pueden acceder a las partes más técnicas de la interfaz. Ellos tienen la **[!UICONTROL Administration]** función y se aseguran de que la plataforma esté configurada para que los especialistas en mercadotecnia solo tengan que centrarse en ofrecer sus campañas.

Los administradores funcionales son los únicos usuarios que pueden acceder al **[!UICONTROL Administration]** menú en la interfaz de Adobe Campaign. Dado que estos usuarios necesitan acceder a los recursos técnicos, se les deben asignar funciones más avanzadas, como las funciones **[!UICONTROL Administration]** y las funciones **[!UICONTROL Datamodel]** integradas. Estas funciones se combinan en el grupo de seguridad **[!UICONTROL Administrators]** integrado. Para obtener más información, consulte [esta sección](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Administrar usuarios y permisos](../../administration/using/about-access-management.md): administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad, unidades).
* [Configure los diferentes canales](../../administration/using/about-channel-configuration.md): configure los diferentes canales de plataforma, así como la administración de la tipología y la cuarentena.
* [Configure las opciones](../../administration/using/external-accounts.md)generales de la aplicación: configure los diferentes elementos de la aplicación (cuentas externas, opciones, flujos de trabajo técnicos).
* [Desarrollar nuevas funciones para mejorar las funcionalidades](../../developing/using/data-model-concepts.md)integradas: administre sus recursos personalizados y acceda a las herramientas de diagnóstico.
* [Configure los parámetros](../../administration/using/branding.md)de instancia: defina las diferentes marcas y configure sus opciones (logotipo, administración del seguimiento, dominio de URL para acceder a las páginas de aterrizaje, etc.).
* [Exportar e importar paquetes de datos](../../automating/using/managing-packages.md): intercambiar recursos entre distintas instancias de Adobe Campaign a través de archivos XML estructurados.
* [Exporte registros](../../automating/using/exporting-logs.md) y [defina plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Usuarios avanzados {#advanced-users}

Los usuarios avanzados son usuarios de marketing que realizan los casos de uso más técnicos en Adobe Campaign. Preconfiguran todos los elementos que utilizan los especialistas en marketing para enviar y supervisar sus envíos.

Este tipo de usuario requiere funciones más generales que los administradores funcionales, pero debe poder realizar algunas operaciones técnicas. Para ello, se les deben asignar, por ejemplo, las funciones **[!UICONTROL Export]**, **[!UICONTROL Generic import]** o **[!UICONTROL Workflow]** integradas. Para obtener más información, consulte [esta sección](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Crear y ejecutar flujos de trabajo](../../automating/using/about-data-management-activities.md)de gestión de datos complejos: importe, enriquezca y transforme datos para alimentar la base de datos, o exporte los datos que necesite en archivos externos para procesarlos en sus propias herramientas.
* [Administrar plantillas](../../start/using/marketing-activity-templates.md): administre las plantillas para preconfigurar ciertos parámetros de sus actividades de mercadotecnia según sus necesidades.
* [Cree consultas](../../automating/using/editing-queries.md#about-query-editor) y [administre sus audiencias](../../audiences/using/about-audiences.md): cree sus audiencias manualmente con consultas o automáticamente con flujos de trabajo dedicados.
* [Realizar edición](../../automating/using/editing-queries.md#about-query-editor)avanzada de expresiones: utilice funciones avanzadas para manipular los valores utilizados para llevar a cabo consultas específicas como fechas, cadenas, campos numéricos, ordenación, etc.
* [Exportar listas](../../automating/using/exporting-lists.md) e [importar datos mediante plantillas de importación](../../automating/using/importing-data-with-import-templates.md)existentes.

### Usuarios básicos {#basic-users}

Gracias al administrador funcional y a los usuarios avanzados, los especialistas en marketing pueden personalizar, entregar y supervisar sus campañas sin tener que preocuparse por la configuración técnica. Para ello, se les deben asignar, por ejemplo, las funciones **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** y **[!UICONTROL Start deliveries]** listas para usar. Estas funciones se combinan en el grupo de seguridad **[!UICONTROL Standard Users]** integrado. Para obtener más información, consulte [esta sección](../../administration/using/list-of-roles.md).

Estas son las principales tareas que pueden realizar:

* [Administrar programas y campañas](../../start/using/programs-and-campaigns.md): cree campañas de marketing que incluyan distintos tipos de actividades (correos electrónicos, mensajes SMS, notificaciones push, flujos de trabajo, páginas de aterrizaje).
* Administrar [perfiles](../../audiences/using/about-profiles.md) y perfiles [de prueba](../../audiences/using/managing-test-profiles.md): administre los destinatarios identificados y de prueba que serán el objetivo de sus envíos. Añada información como nombre, apellidos, información de contacto, suscripciones, correos electrónicos, etc.
* [Crear y enviar mensajes](../../sending/using/confirming-the-send.md): cree su mensaje, seleccione la audiencia, defina el contenido del mensaje y sus elementos de personalización, envíe pruebas y envíe el mensaje final a su audiencia.
* [Crear y publicar páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md): cree y administre un conjunto de servicios que desee que tengan oferta con sus clientes, por ejemplo, formularios bajas o de suscripción.
* [Crear y ejecutar flujos de trabajo de la campaña](../../automating/using/building-a-workflow.md): automatice los procesos de campaña mediante flujos de trabajo.
* Monitoree sus actividades de mercadotecnia a través de los informes [](../../reporting/using/defining-the-report-period.md)disponibles.

## Creación de un usuario {#creating-a-user}

Para agregar un usuario a su instancia, primero debe crearlo en la consola de administración antes de administrarlo en Adobe Campaign Standard.

1. En el menú avanzado, seleccione **[!UICONTROL Administration > Users & Security > Users]** y haga clic en **[!UICONTROL User administration]** para acceder a la consola de administración.

   ![](assets/user_management_5.png)

1. En la **[!UICONTROL Admin Console]**, haga clic en la **[!UICONTROL Users]** ficha.

1. Haga clic **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. En la **[!UICONTROL User details]** ficha, rellene los detalles del usuario, como la dirección de correo electrónico, el nombre y los apellidos.

   ![](assets/create_user_3.png)

1. En la **[!UICONTROL Assign products]** ficha, asigne uno o varios grupos de seguridad al usuario. For more information on security groups, refer to this [page](../../administration/using/managing-groups-and-users.md).

   Haga clic **[!UICONTROL Save]** cuando termine de configurar.

   ![](assets/create_user_4.png)

El usuario se ha creado y debe recibir una redirección por correo electrónico a la siguiente ventana donde el usuario debe establecer una contraseña y luego aceptar el contrato de términos de uso. Este usuario podrá conectarse a su instancia de Adobe Campaign Standard.

![](assets/create_user_5.png)

El usuario se sincronizará con Adobe Campaign Standard en cuanto inicie sesión en su instancia.

A continuación, puede comprobar si el usuario se ha sincronizado correctamente con Adobe Campaign:

1. En el menú avanzado, **[!UICONTROL Administration > Users & Security > Users]** seleccione el usuario creado anteriormente.

1. Actualice **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** o **[!UICONTROL Regional settings]** si es necesario.

1. Compruebe el grupo de seguridad del usuario. Aquí puede ver que al usuario se le ha asignado el grupo de **[!UICONTROL Administrators]** seguridad.

   >[!Note]
   >
   >Los grupos de seguridad solo se pueden eliminar o agregar a un usuario en la Consola de administración.

   ![](assets/create_user_6.png)

1. Compruebe **[!UICONTROL Account disabled]** si desea desactivar este usuario.

1. En el **[!UICONTROL Authorized connection zone]** campo, seleccione la forma en que el usuario se conectará a esta instancia, por ejemplo, red interna o VPN.

1. Haga clic **[!UICONTROL Save]**.

El usuario ya está listo para usar Adobe Campaign Standard.

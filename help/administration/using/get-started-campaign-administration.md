---
title: Introducción a la administración de Campaign Standard
description: Obtenga más información acerca la administración de usuarios y permisos, las pautas de monitorización, las configuraciones específicas de canal y las pautas de configuración de aplicaciones
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 13%

---

# Introducción a la administración de Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menú Administración</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuarios y seguridad</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuración de canales</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Configuración de aplicación</a></p></td></tr>
</table>

Como solución basada en la nube, Adobe Campaign ofrece a los administradores diferentes formas de configurar la aplicación. Aunque la configuración de la infraestructura la realiza el Adobe, los administradores funcionales pueden realizar diversas operaciones de configuración detalladas a continuación.

>[!NOTE]
>
>Si tiene preguntas o solicitudes acerca de cuestiones de implementación y configuración, póngase en contacto con su administrador de cuentas de Adobe.

Tenga en cuenta que los usuarios administradores también pueden aprovechar el Panel de control de Campaign de Campaign para administrar la configuración y rastrear los usos de cada una de las instancias. Para obtener más información, consulte la [documentación dedicada](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es).

## Menú Administración {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Las diferentes operaciones de administración de Adobe Campaign se llevan a cabo mediante la variable **[!UICONTROL Administration]** al hacer clic en el logotipo de Adobe Campaign, en la esquina superior izquierda. Solo los administradores funcionales de la plataforma pueden acceder a esta parte de la interfaz.

Los diferentes menús disponibles son:

* [Usuarios y seguridad](../../administration/using/about-access-management.md): Este menú le permite administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad y unidades).
* [Canales](../../administration/using/about-channel-configuration.md): Este menú reagrupa los parámetros técnicos vinculados a los diferentes canales de la plataforma (correo electrónico, móvil), así como la administración de tipología y cuarentena.
* [Configuración de aplicación](../../administration/using/external-accounts.md): Este menú permite configurar diferentes elementos de la aplicación (cuentas externas, opciones y flujos de trabajo técnicos).
* [Desarrollo](../../developing/using/data-model-concepts.md): este menú le permite administrar sus recursos personalizados y acceder a las herramientas de diagnóstico.
* [Configuración de instancia](../../administration/using/branding.md): En este menú se definen las diferentes marcas y se establece su configuración (logotipo, administración del seguimiento y dominio de URL para acceder a las páginas de aterrizaje, etc.).
* [Implementación](../../automating/using/managing-packages.md): Este menú reagrupa las opciones de importación y exportación del paquete.
* [Métricas del cliente](../../audiences/using/active-profiles.md): Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación.
* [Herramientas de privacidad](../../start/using/privacy-management.md): Este menú le permite crear solicitudes de eliminación y acceso de RGPD, y rastrear su evolución.

## Usuarios y seguridad {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invitar a usuarios a acceder a la aplicación y administrar **grupos de seguridad**, que son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de la organización. De forma predeterminada, Adobe Campaign ofrece un conjunto de **funciones** que le permite definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios. Combinado con **unidades organizativas**, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Campaign Standard también le permite supervisar la información relacionada con la seguridad. Puede recuperar información sobre las exportaciones de datos realizadas por los usuarios a través del **[!UICONTROL Export audits]** y aproveche la función **[!UICONTROL Licenses]** para monitorizar todas las licencias de Campaign instaladas en su organización, así como información diferente como el número de compilación, la versión de lanzamiento y los términos del acuerdo.

Más información:

* [Administración de usuarios](../../administration/using/users-management.md)
* [Unidades organizativas](../../administration/using/organizational-units.md)
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
* [Auditoría de registros de exportación](../../administration/using/auditing-export-logs.md)
* [Licencias](../../administration/using/licenses.md)

## Configuración de canales {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos los canales de comunicación de Adobe Campaign deben estar correctamente configurados para poder enviar mensajes de forma eficaz.,El **[!UICONTROL Channel]**  permite administrar los parámetros técnicos vinculados a los diferentes canales.

Configurar varios **email** parámetros: reglas de procesamiento para rechazos, cuarentena, propiedades de correo electrónico y parámetros de enrutamiento, reglas de tipología. Defina las configuraciones y propiedades de enrutamiento para **SMS** , así como la codificación y los formatos SMS.

Configuración de **aplicaciones móviles** para poder enviar mensajes en la aplicación y notificaciones push mediante los SDK de Adobe Experience Platform.

Más información:

* [Acerca de la configuración de canales](../../administration/using/about-channel-configuration.md)
* [Configuración de canales de correo electrónico](../../administration/using/configuring-email-channel.md)
* [Configuración de canales de SMS](../../administration/using/configuring-sms-channel.md)
* [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)

## Configuración de aplicación {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene con diferentes elementos de aplicación que se pueden configurar para que coincidan con sus necesidades.

Configuración de **cuentas externas**, que se utilizan para conectar Adobe Campaign a servidores externos. Acceda a las asignaciones de destino del Campaign Standard y monitorice su plataforma mediante **flujos de trabajo técnicos**.

Defina una o varias **marcas** para su organización y configure el envío de **notificaciones en tiempo real** dentro de la aplicación en caso de actividades importantes del sistema.

Más información:

* [Acerca de la configuración de Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Cuentas externas](../../administration/using/external-accounts.md)
* [Asignaciones de objetivos en Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Promoción de la marca](../../administration/using/branding.md)
* [Envío de notificaciones internas](../../administration/using/sending-internal-notifications.md)

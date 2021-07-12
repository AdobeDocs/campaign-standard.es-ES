---
solution: Campaign Standard
product: campaign
title: Introducción a la administración de Campaign Standard
description: Descubra la administración de usuarios y permisos, las pautas de supervisión, configuraciones específicas de canal y pautas de configuración de aplicaciones.
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
feature: Administración de acceso
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 15%

---

# Introducción a la administración de Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menú Administración</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuarios y seguridad</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuración de canales</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Configuración de la aplicación</a></p></td></tr>
</table>

Como solución basada en la nube, Adobe Campaign ofrece a los administradores diferentes formas de configurar la aplicación. Aunque la configuración de la infraestructura la realiza Adobe, los administradores funcionales pueden realizar varias operaciones de configuración detalladas a continuación.

>[!NOTE]
>
>Si tiene preguntas o solicitudes sobre cuestiones de implementación y configuración, póngase en contacto con el administrador de cuentas de Adobe.

Tenga en cuenta que los usuarios administradores también pueden aprovechar el Panel de control de Campaign de Campaign para administrar la configuración y rastrear los usos de cada una de sus instancias. Para obtener más información, consulte la [documentación dedicada](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es).

## Menú Administración {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Las distintas operaciones de administración de Adobe Campaign se realizan mediante el menú **[!UICONTROL Administration]** al que se puede acceder al hacer clic en el logotipo de Adobe Campaign en la esquina superior izquierda. Solo los administradores funcionales de la plataforma pueden acceder a esta parte de la interfaz.

Los diferentes menús disponibles son:

* [Usuarios y seguridad](../../administration/using/about-access-management.md): Este menú le permite administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad y unidades).
* [Canales](../../administration/using/about-channel-configuration.md): Este menú reagrupa los parámetros técnicos vinculados a los diferentes canales de la plataforma (correo electrónico, móvil), así como la administración de la tipología y la cuarentena.
* [Ajustes](../../administration/using/external-accounts.md) de la aplicación: Este menú permite configurar diferentes elementos de la aplicación (cuentas externas, opciones y flujos de trabajo técnicos).
* [Desarrollo](../../developing/using/data-model-concepts.md): Este menú le permite administrar sus recursos personalizados y acceder a las herramientas de diagnóstico.
* [Configuración de instancia](../../administration/using/branding.md): En este menú se definen las diferentes marcas y se configuran los ajustes (logotipo, administración del seguimiento, dominio de URL para acceder a las páginas de aterrizaje, etc.).
* [Implementación](../../automating/using/managing-packages.md): Este menú reagrupa las opciones de importación y exportación del paquete.
* [Métricas](../../audiences/using/active-profiles.md) del cliente: Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación.
* [Herramientas de privacidad](../../start/using/privacy-management.md): Este menú le permite crear solicitudes de acceso y eliminación del RGPD y rastrear su evolución.

## Usuarios y seguridad {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invite a los usuarios a acceder a la aplicación y administre **grupos de seguridad**, que son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de la organización. De forma predeterminada, Adobe Campaign ofrece un conjunto de **roles** que le permite definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios. Combinadas con **unidades organizativas**, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

El estándar de Campaign también le permite supervisar la información relacionada con la seguridad. Puede recuperar información relacionada con las exportaciones de datos realizadas por los usuarios a través de la pantalla **[!UICONTROL Export audits]** y aprovechar la pantalla **[!UICONTROL Licenses]** para monitorizar todas las licencias de Campaign instaladas dentro de su organización, así como información diferente como el número de compilación, la versión de lanzamiento y los términos de acuerdo.

Más información:

* [Administración de usuarios](../../administration/using/users-management.md)
* [Unidades organizativas](../../administration/using/organizational-units.md)
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
* [Auditoría de registros de exportación](../../administration/using/auditing-export-logs.md)
* [Licencias](../../administration/using/licenses.md)

## Configuración de canales {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos los canales de comunicación en Adobe Campaign deben estar correctamente configurados para poder enviar mensajes de forma eficaz., El menú **[!UICONTROL Channel]** le permite administrar los parámetros técnicos vinculados a los diferentes canales.

Configure varios parámetros **email**: reglas de procesamiento para devoluciones, cuarentena, propiedades de correo electrónico y parámetros de enrutamiento, reglas de tipología. Defina las configuraciones y propiedades de enrutamiento para el canal **SMS**, así como la codificación y los formatos SMS.

Configure **aplicaciones móviles** para poder enviar mensajes en la aplicación y notificaciones push mediante los SDK para Adobe Experience Platform.

Más información:

* [Acerca de la configuración de canales](../../administration/using/about-channel-configuration.md)
* [Configuración de canales de correo electrónico](../../administration/using/configuring-email-channel.md)
* [Configuración de canales de SMS](../../administration/using/configuring-sms-channel.md)
* [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)

## Configuración de la aplicación {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene con diferentes elementos de la aplicación que se pueden configurar para adaptarlos a sus necesidades.

Configure **cuentas externas**, que se utilizan para conectar Adobe Campaign a servidores externos. Acceda a asignaciones de destino de Campaign Standard y supervise la plataforma mediante **flujos de trabajo técnicos**.

Defina una o varias **marcas** para su organización y configure el envío de **notificaciones en tiempo real** dentro de la aplicación en caso de actividades importantes del sistema.

Más información:

* [Acerca de la configuración de Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Cuentas externas](../../administration/using/external-accounts.md)
* [Asignaciones de objetivos en Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Promoción de la marca](../../administration/using/branding.md)
* [Envío de notificaciones internas](../../administration/using/sending-internal-notifications.md)

---
title: Introducción a la administración de Campaign Standard
description: Adobe Campaign le proporciona un conjunto completo de herramientas de administración. Obtenga información sobre cómo administrar los usuarios y configurar sus canales.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 14%

---


# Introducción a la administración de Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menú Administración</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuarios y seguridad</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuración de Canales</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Ajustes de la aplicación</a></p></td></tr>
</table>

Como solución basada en la nube, Adobe Campaign oferta a los administradores de diferentes maneras de configurar la aplicación. Aunque Adobe realiza la configuración de la infraestructura, los administradores funcionales pueden realizar diversas operaciones de configuración que se detallan a continuación.

>[!NOTE]
>
>Si tiene preguntas o solicitudes sobre cuestiones de implementación y configuración, póngase en contacto con el ejecutivo de cuentas de Adobe.

## Menú Administración {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Las diferentes operaciones de administración de Adobe Campaign se realizan a través del **[!UICONTROL Administration]** menú al que se puede acceder haciendo clic en el logotipo de Adobe Campaign en la esquina superior izquierda. Solo los administradores funcionales de la plataforma pueden acceder a esta parte de la interfaz.

Los diferentes menús disponibles son:

* [Usuarios y seguridad](../../administration/using/about-access-management.md): Este menú le permite administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad, unidades).
* [Canales](../../administration/using/about-channel-configuration.md): Este menú reagrupa los parámetros técnicos vinculados a los diferentes canales de la plataforma (correo electrónico, SMS), así como la administración de la tipología y la cuarentena.
* [Ajustes](../../administration/using/external-accounts.md)de la aplicación: Este menú le permite configurar diferentes elementos de la aplicación (cuentas externas, opciones, flujos de trabajo técnicos).
* [Desarrollo](../../developing/using/data-model-concepts.md): Este menú le permite administrar sus recursos personalizados y acceder a las herramientas de diagnóstico.
* [Configuración](../../administration/using/branding.md)de instancia: En este menú se definen las distintas marcas y se configuran las opciones (logotipo, gestión del seguimiento, dominio de URL para acceder a las páginas de aterrizaje, etc.).
* [Implementación](../../automating/using/managing-packages.md): Este menú reagrupa las opciones de importación y exportación de paquetes.
* [Métricas](../../audiences/using/active-profiles.md)del cliente: Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación.
* [Herramientas](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html)de privacidad: Este menú le permite crear solicitudes de acceso y eliminación de RGPD y rastrear su evolución.

## Usuarios y seguridad {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invite a los usuarios a acceder a la aplicación y administrar grupos **de** seguridad, que son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de la organización. By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

El estándar de Campaña también le permite supervisar la información relacionada con la seguridad. Puede recuperar información sobre las exportaciones de datos realizadas por los usuarios a través de la **[!UICONTROL Export audits]** pantalla y aprovechar la pantalla para **[!UICONTROL Licenses]** supervisar todas las licencias de Campaña instaladas dentro de la organización, así como información diferente como el número de compilación, la versión de lanzamiento y los términos de acuerdo.

Más información:

* [Administración de usuarios](../../administration/using/users-management.md)
* [Unidades organizativas](../../administration/using/organizational-units.md)
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
* [Auditoría de registros de exportación](../../administration/using/auditing-export-logs.md)
* [Licencias](../../administration/using/licenses.md)

## Configuración de Canales {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos los canales de comunicación de Adobe Campaign deben estar correctamente configurados para poder enviar mensajes de forma eficaz., **[!UICONTROL Channel]** El menú le permite administrar los parámetros técnicos vinculados a los diferentes canales.

Configure varios parámetros **de correo electrónico** : reglas de procesamiento para devoluciones, cuarentenas, propiedades de correo electrónico y parámetros de enrutamiento, reglas de tipo. Defina las configuraciones y propiedades de enrutamiento para el canal **SMS** , así como la codificación y los formatos SMS.

Configure aplicaciones **** móviles para poder enviar mensajes en la aplicación y notificaciones push mediante SDK de Adobe Experience Platform, y configure la mensajería **** transaccional creando y configurando eventos.

Más información:

* [Acerca de la configuración de canales](../../administration/using/about-channel-configuration.md)
* [Configuración de canales de correo electrónico](../../administration/using/configuring-email-channel.md)
* [Configuración de canales de SMS](../../administration/using/configuring-sms-channel.md)
* [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)
* [Configuración de la mensajería transaccional](../../administration/using/configuring-transactional-messaging.md)

## Ajustes de la aplicación {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene con diferentes elementos de la aplicación que pueden configurarse para satisfacer sus necesidades.

Configure **cuentas externas**, que se utilizan para conectar Adobe Campaign a servidores externos. Acceda a asignaciones de destino de Campaign Standard y supervise la plataforma mediante **flujos de trabajo técnicos**.

Defina una o varias **marcas** para su organización y configure el envío de notificaciones **en tiempo** real dentro de la aplicación en caso de actividades importantes del sistema.

Más información:

* [Acerca de la configuración de Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Cuentas externas](../../administration/using/external-accounts.md)
* [Asignaciones de objetivos en Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Marcas](../../administration/using/branding.md)
* [Envío de notificaciones internas](../../administration/using/sending-internal-notifications.md)

## Recursos adicionales

* [Administración de los derechos de acceso de los usuarios (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Documentación del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/control-panel-home.html)

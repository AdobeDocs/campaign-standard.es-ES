---
solution: Campaign Standard
product: campaign
title: Introducción a la administración de Campaign Standard
description: Descubra la administración de usuarios y permisos, las pautas de supervisión, configuraciones específicas de canal y pautas de configuración de aplicaciones.
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 15%

---


# Introducción a la administración de Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menú Administración</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuarios y seguridad</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuración de canales</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Ajustes de la aplicación</a></p></td></tr>
</table>

Como solución basada en la nube, Adobe Campaign oferta a los administradores de diferentes maneras de configurar la aplicación. Aunque Adobe realiza la configuración de la infraestructura, los administradores funcionales pueden realizar diversas operaciones de configuración que se detallan a continuación.

>[!NOTE]
>
>Si tiene preguntas o solicitudes sobre cuestiones de implementación y configuración, póngase en contacto con el ejecutivo de cuentas de Adobe.

Tenga en cuenta que, si la instancia está alojada en AWS, los usuarios administradores también pueden aprovechar el Panel de control de Campaign de Campaña para administrar la configuración y rastrear los usos de cada una de las instancias. Para obtener más información, consulte la [documentación dedicada](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es).

## Menú Administración {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Las distintas operaciones de administración de Adobe Campaign se realizan mediante el menú **[!UICONTROL Administration]** al que se puede acceder al hacer clic en el logotipo de Adobe Campaign en la esquina superior izquierda. Solo los administradores funcionales de la plataforma pueden acceder a esta parte de la interfaz.

Los diferentes menús disponibles son:

* [Usuarios y seguridad](../../administration/using/about-access-management.md): Este menú le permite administrar el acceso a la plataforma (usuarios, funciones, grupos de seguridad, unidades).
* [Canales](../../administration/using/about-channel-configuration.md): Este menú reagrupa los parámetros técnicos vinculados a los diferentes canales de plataforma (Correo electrónico, móvil), así como la administración de la tipología y la cuarentena.
* [Ajustes](../../administration/using/external-accounts.md) de la aplicación: Este menú le permite configurar diferentes elementos de la aplicación (cuentas externas, opciones, flujos de trabajo técnicos).
* [Desarrollo](../../developing/using/data-model-concepts.md): Este menú le permite administrar sus recursos personalizados y acceder a las herramientas de diagnóstico.
* [Configuración](../../administration/using/branding.md) de instancia: En este menú se definen las distintas marcas y se configuran las opciones (logotipo, gestión del seguimiento, dominio de URL para acceder a las páginas de aterrizaje, etc.).
* [Implementación](../../automating/using/managing-packages.md): Este menú reagrupa las opciones de importación y exportación de paquetes.
* [Métricas](../../audiences/using/active-profiles.md) del cliente: Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación.
* [Herramientas](../../start/using/privacy-management.md) de privacidad: Este menú le permite crear solicitudes de acceso y eliminación de RGPD y rastrear su evolución.

## Usuarios y seguridad {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invite a los usuarios a acceder a la aplicación y administrar **grupos de seguridad**, que son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de la organización. De forma predeterminada, Adobe Campaign oferta un conjunto de **roles** que le permite definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios. Combinadas con **unidades organizativas**, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

El estándar de campaña también le permite supervisar la información relacionada con la seguridad. Puede recuperar información sobre las exportaciones de datos realizadas por los usuarios a través de la pantalla **[!UICONTROL Export audits]** y aprovechar la pantalla **[!UICONTROL Licenses]** para monitorear todas las licencias de Campaña instaladas dentro de su organización, así como información diferente como el número de compilación, la versión de lanzamiento y los términos de acuerdo.

Más información:

* [Administración de usuarios](../../administration/using/users-management.md)
* [Unidades organizativas](../../administration/using/organizational-units.md)
* [Lista de funciones](../../administration/using/list-of-roles.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
* [Auditoría de registros de exportación](../../administration/using/auditing-export-logs.md)
* [Licencias](../../administration/using/licenses.md)

## Configuración de canales {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos los canales de comunicación de Adobe Campaign deben estar correctamente configurados para poder enviar mensajes de forma eficaz.,El menú **[!UICONTROL Channel]** le permite administrar los parámetros técnicos vinculados a los diferentes canales.

Configure varios parámetros **email**: reglas de procesamiento para devoluciones, cuarentenas, propiedades de correo electrónico y parámetros de enrutamiento, reglas de tipo. Defina las configuraciones y propiedades de enrutamiento para el canal **SMS**, así como la codificación y los formatos SMS.

Configure **aplicaciones móviles** para poder enviar mensajes en la aplicación y notificaciones push mediante SDK de Adobe Experience Platform.

Más información:

* [Acerca de la configuración de canales](../../administration/using/about-channel-configuration.md)
* [Configuración de canales de correo electrónico](../../administration/using/configuring-email-channel.md)
* [Configuración de canales de SMS](../../administration/using/configuring-sms-channel.md)
* [Configuración de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)

## Ajustes de la aplicación {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene con diferentes elementos de la aplicación que pueden configurarse para satisfacer sus necesidades.

Configure **cuentas externas**, que se utilizan para conectar Adobe Campaign a servidores externos. Obtenga acceso a asignaciones de destino de Campaign Standard y supervise su plataforma mediante **flujos de trabajo técnicos**.

Defina una o varias **marcas** para su organización y configure el envío de **notificaciones en tiempo real** dentro de la aplicación en caso de actividades importantes del sistema.

Más información:

* [Acerca de la configuración de Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Cuentas externas](../../administration/using/external-accounts.md)
* [Asignaciones de objetivos en Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flujos de trabajo técnicos](../../administration/using/technical-workflows.md)
* [Marcas](../../administration/using/branding.md)
* [Envío de notificaciones internas](../../administration/using/sending-internal-notifications.md)

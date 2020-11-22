---
solution: Campaign Standard
product: campaign
title: Introducción a la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo empezar a utilizar la integración de Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 11%

---


# Introducción a la integración con Microsoft Dynamics 365

Active los datos de CRM en la comunicación entre canales: aprenda a pasar contactos de Microsoft Dynamics 365 a Adobe Campaign y a compartir datos de rendimiento de campañas (envía, abre, hace clic y rebotan) de Adobe Campaign a Microsoft Dynamics 365.

Las versiones admitidas se enumeran [en esta sección](#support-software-versions).

>[!CAUTION]
>
>Esta capacidad no está disponible de forma predeterminada como parte del producto. La implementación requiere la participación de Adobe Consulting. Póngase en contacto con el representante de su Adobe para obtener más información.

## Principios

La integración de Adobe Campaign y Microsoft Dynamics 365 permite la sincronización de todos los datos de contacto disponibles en el sistema CRM, lo que hace que todos los datos de contacto relevantes estén disponibles para actividades de campaña.

Por el contrario, a medida que los perfiles de Adobe Campaign interactúan con los mensajes, dichos datos (por ejemplo: envía, abre, hace clic y realiza devoluciones) automáticamente en Microsoft Dynamics 365 para mantener los registros de contacto completos con la actividad de marketing.

La integración también admite entidades personalizadas, lo que permite sincronizar las entidades [](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) personalizadas de Dynamics 365 con las entidades personalizadas correspondientes en la Campaña.

Esta integración está diseñada para admitir cuatro casos de uso principales:

1. Sincronización de contactos de Dynamics 365 con Campaña para que se puedan segmentar en campañas de marketing
1. Sincronización de entidades personalizadas de Dynamics 365 a Campaña para que se puedan utilizar en la segmentación y personalización
1. Envío de eventos de marketing por correo electrónico (envía, abre, hace clic y rebota) desde la Campaña a Dynamics 365 para mostrarlos en el repositorio de ventas en la interfaz de Dynamics 365
1. Sincronizar los estados de exclusión (por ejemplo, no enviar correo electrónico) entre Dynamics 365 y ACS para mantener las preferencias de privacidad del cliente.

## Ventajas principales

* Mensajería coherente entre ventas y marketing

La integración de Adobe Campaign y Microsoft Dynamics 365 proporciona a ambos sistemas acceso a la perspectiva del cliente y al historial de marketing de correo electrónico, lo que permite que todos los mensajes del cliente compartan la misma mensajería coherente.

* Vista holística de todos los datos de clientes potenciales y clientes

Al integrar Adobe Campaign con Dynamics 365, es posible compartir y acceder al historial de marketing de correo electrónico en cada contacto desde el sistema CRM.

* Activar datos de Dynamics 365 en cualquier canal

Con los datos de contacto sincronizados con Adobe Campaign, las comunicaciones se pueden enviar en cualquier canal en línea o sin conexión con Campaña, incluida la inserción móvil, en la aplicación, el correo electrónico o el correo directo. Independientemente del canal preferido de cada contacto, la Campaña te ha cubierto.

>[!CAUTION]
>
>Para la sincronización de contactos y entidades personalizadas, esta integración considera a Dynamics 365 como la fuente de la verdad.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365, no en Campaña.  Si los cambios se realizan en Campaña, se pueden sobrescribir durante la sincronización.

## Versiones de software de soporte {#support-software-versions}

Esta integración requiere las siguientes versiones de software:

* Solo Microsoft Dynamics 365 para ventas en línea, versión más reciente

* Adobe Campaign Standard, última versión

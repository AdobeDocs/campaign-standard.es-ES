---
title: Trabajo con Campaign Standard y Microsoft Dynamics 365
description: Obtenga información sobre cómo trabajar con Campaign Standard y Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74cc176a1b93a7983629ccccb1fea00628241952

---


# Trabajo con Campaign Standard y Microsoft Dynamics 365

Active los datos de CRM en la comunicación entre canales: aprenda a pasar contactos de Microsoft Dynamics 365 a Adobe Campaign y a compartir datos de rendimiento de campañas (envía, abre, hace clic y rebotan) de Adobe Campaign a Microsoft Dynamics 365.

>[!NOTE]
>
>La integración de Microsoft Dynamics 365/Adobe Campaign Standard solo admite la aplicación **de ventas de** Microsoft Dynamics 365.

## Beneficios y casos de uso

### Principios

La integración de Adobe Campaign y Microsoft Dynamics 365 permite la sincronización de todos los datos de contacto disponibles en el sistema CRM, lo que hace que todos los datos de contacto relevantes estén disponibles para actividades de campaña.

Por el contrario, a medida que los perfiles dentro del Adobe Campaign interactúan con los mensajes, dichos datos (por ejemplo: envía, abre, hace clic y realiza devoluciones) automáticamente en Microsoft Dynamics 365 para mantener los registros de contacto completos con la actividad de marketing.

La última versión de la integración también añade compatibilidad con las entidades personalizadas, lo que permite sincronizar las entidades personalizadas de Dynamics 365 con las entidades personalizadas correspondientes en la Campaña.

Esta integración está diseñada para admitir tres casos de uso principales:

1. Sincronización de contactos de Dynamics 365 con Campaña para que se puedan segmentar en campañas de marketing
1. Envío de eventos de marketing por correo electrónico (envía, abre, hace clic y rebota) desde la Campaña a Dynamics 365 para mostrarlos en el repositorio de ventas en la interfaz de Dynamics 365
1. Sincronización de entidades personalizadas de Dynamics 365 a Campaña para que se puedan utilizar en la segmentación y personalización

Vea el vídeo de la función de integración de Campaign Standard de Dynamics 365 [aquí](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html).

### Beneficios principales

* Mensajería coherente entre ventas y marketing

La integración de Adobe Campaign y Microsoft Dynamics 365 proporciona a ambos sistemas acceso a la perspectiva del cliente y al historial de marketing de correo electrónico, lo que permite que todos los mensajes dirigidos al cliente compartan la misma mensajería coherente.

* vista holística de todos los datos de clientes potenciales y clientes

Al integrar Adobe Campaign con Dynamics 365, es posible compartir y acceder al historial de marketing de correo electrónico en cada contacto desde el sistema CRM.

* Activar datos de Dynamics 365 en cualquier canal

Con los datos de contacto sincronizados con el Adobe Campaign, las comunicaciones se pueden enviar en cualquier canal en línea o sin conexión con Campaña, incluida la inserción móvil, en la aplicación, el correo electrónico o el correo directo. Independientemente del canal preferido de cada Contactos, la Campaña le ha cubierto.

>[!CAUTION]
>
>Para la sincronización de Contactos, esta integración considera a Dynamics 365 como la fuente de la verdad.  Cualquier cambio en los atributos de contacto sincronizados debe realizarse en Dynamics 365, no en Campaña.  Si los cambios se realizan en Campaña, se pueden sobrescribir durante la sincronización.


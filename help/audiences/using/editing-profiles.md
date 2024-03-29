---
title: Edición de perfiles
description: Obtenga información sobre cómo editar perfiles existentes y acceder a información de contacto, canales preferidos, registros de seguimiento, suscripciones, etc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# Edición de perfiles{#editing-profiles}

## Acceso a propiedades de perfil {#accessing-profile-properties}

Para editar un perfil existente y consultar los datos asociados a él o modificarlo, los pasos son los siguientes:

1. En la página de inicio de Adobe Campaign, haga clic en **[!UICONTROL Customer profiles]** o la **[!UICONTROL Profiles]** pestaña.
1. Seleccione un contacto.
1. Haga clic en **[!UICONTROL Edit profile properties]** para acceder a la información detallada del perfil.

   ![](assets/profile_creation2.png)

   La ventana de propiedades del perfil ofrece varias pestañas que proporcionan acceso a toda la información del perfil.

   También pueden aparecer otras pestañas en función de los recursos personalizados que se hayan creado o ampliado en Adobe Campaign. Para obtener más información sobre los recursos personalizados, consulte [Acerca de los recursos personalizados](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Solo puede modificar la información en la variable **[!UICONTROL General]** pestaña - excepto para **[!UICONTROL Traceability]** sección.

También es posible editar perfiles mediante la API de Adobe Campaign Standard. Para obtener más información, consulte la [documentación específica](../../api/using/updating-profiles.md).

Temas relacionados:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envío en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Datos generales de perfil {#general-profile-data}

El **[!UICONTROL General]** La pestaña agrupa la siguiente información sobre el perfil:

* Información de contacto, que contiene el nombre, apellidos, fecha de nacimiento, foto, idioma preferido del destinatario (por ejemplo, [correos electrónicos multilingües](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canales en los que se puede contactar con el perfil, que contiene la dirección de correo electrónico del destinatario, el número de teléfono móvil y la información de exclusión.
* Dirección postal (para [correo directo](../../channels/using/about-direct-mail.md)) y la zona horaria del contacto (hasta [programar mensajes en su zona horaria](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorización de acceso, que indica la unidad organizativa del destinatario (a [administración de permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Registros de envío y seguimiento {#sending-and-tracking-logs}

El **[!UICONTROL Sending logs]** y **[!UICONTROL Tracking logs]** las pestañas agrupan la lista de envíos que se han enviado al perfil y todos los datos de seguimiento relacionados.

Para obtener más información sobre el envío y los registros de seguimiento, consulte la [registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs) y el [seguimiento de mensajes](../../sending/using/tracking-messages.md) secciones.

## Suscripciones {#subscriptions}

Las suscripciones del contacto se enumeran en la pestaña correspondiente. Para obtener más información sobre la suscripción a un servicio, consulte [esta sección](../../audiences/using/about-subscriptions.md).

El **[!UICONTROL Mobile App Subscriptions]** consulte las notificaciones push. Para obtener más información, consulte la [Notificación push](../../channels/using/about-push-notifications.md) canal.

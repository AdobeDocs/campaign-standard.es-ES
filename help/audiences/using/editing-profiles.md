---
solution: Campaign Standard
product: campaign
title: Edición de perfiles
description: Obtenga información sobre cómo editar perfiles existentes y acceder a información de contacto, canales preferidos, registros de seguimiento, suscripciones, etc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 8%

---


# Edición de perfiles{#editing-profiles}

## Acceso a las propiedades de perfil {#accessing-profile-properties}

Para editar un perfil existente y consultar los datos asociados a él, o modificarlo, los pasos son los siguientes:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta **[!UICONTROL Customer profiles]** o en la pestaña **[!UICONTROL Profiles]**.
1. Seleccione un contacto.
1. Haga clic en el icono **[!UICONTROL Edit profile properties]** para acceder a la información detallada del perfil.

   ![](assets/profile_creation2.png)

   La ventana de propiedades del perfil ofrece varias pestañas que proporcionan acceso a toda la información del perfil.

   También pueden aparecer otras pestañas, según los recursos personalizados que se hayan creado o ampliado en Adobe Campaign. Para obtener más información sobre los recursos personalizados, consulte [Acerca de los recursos personalizados](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Solo puede modificar la información en la pestaña **[!UICONTROL General]**, excepto en la sección **[!UICONTROL Traceability]**.

La edición de perfiles también es posible mediante la API de Adobe Campaign Standard. Para obtener más información, consulte la [documentación específica](../../api/using/updating-profiles.md).

Tema relacionado:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Envío en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Datos generales de perfil {#general-profile-data}

La pestaña **[!UICONTROL General]** agrupa la siguiente información sobre el perfil:

* Información de contacto, que contiene el nombre, apellidos, fecha de nacimiento, foto, idioma preferido del destinatario (para [correos electrónicos multilingües](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canales en los que se puede contactar con el perfil, que contienen la dirección de correo electrónico del destinatario, el número de teléfono móvil y la información de exclusión.
* Dirección postal (para [correo postal](../../channels/using/about-direct-mail.md)) y zona horaria del contacto (para [programar mensajes en su zona horaria](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorización de acceso, que indica la unidad organizativa del destinatario (para [administrar permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Envío y seguimiento de registros {#sending-and-tracking-logs}

Las pestañas **[!UICONTROL Sending logs]** y **[!UICONTROL Tracking logs]** agrupan la lista de envíos que se enviaron al perfil y todos los datos de seguimiento relacionados.

Para obtener más información sobre el envío y los registros de seguimiento, consulte las secciones [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) y [tracking messages](../../sending/using/tracking-messages.md) .

## Suscripciones {#subscriptions}

Las suscripciones del contacto se enumeran en la pestaña correspondiente. Para obtener más información sobre la suscripción a un servicio, consulte [esta sección](../../audiences/using/about-subscriptions.md).

La pestaña **[!UICONTROL Mobile App Subscriptions]** hace referencia a las notificaciones push. Para obtener más información, consulte el canal [Push notification](../../channels/using/about-push-notifications.md) .

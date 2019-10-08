---
title: Edición de perfiles
seo-title: Edición de perfiles
description: Edición de perfiles
seo-description: Obtenga información sobre cómo editar los perfiles existentes y acceder a la información de contacto, los canales preferidos, los registros de seguimiento, las suscripciones, etc.
page-status-flag: nunca activado
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar-perfiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# Edición de perfiles{#editing-profiles}

## Acceso a las propiedades del perfil {#accessing-profile-properties}

Para editar un perfil existente y consultar los datos asociados a él, o modificarlo, siga estos pasos:

1. En la página de inicio de Adobe Campaign, haga clic en la **[!UICONTROL Customer profiles]** tarjeta o en la **[!UICONTROL Profiles]** ficha.
1. Seleccione un contacto.
1. Haga clic en el **[!UICONTROL Edit profile properties]** icono para acceder a la información detallada del perfil.

   ![](assets/profile_creation2.png)

   La ventana de propiedades del perfil ofrece varias fichas que permiten acceder a toda la información del perfil.

   También pueden aparecer otras fichas en función de los recursos personalizados que se hayan creado o ampliado en Adobe Campaign. Para obtener más información sobre los recursos personalizados, consulte [Acerca de los recursos](../../developing/using/data-model-concepts.md)personalizados.

   >[!NOTE]
   >
   >Sólo puede modificar la información de la **[!UICONTROL General]** ficha, excepto la **[!UICONTROL Traceability]** sección.

La edición de perfiles también es posible mediante la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

Tema relacionado:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envío en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Datos de perfil generales {#general-profile-data}

La **[!UICONTROL General]** ficha agrupa la siguiente información sobre el perfil:

* Información de contacto, que contiene el nombre, apellidos, fecha de nacimiento, foto, idioma preferido (para correos electrónicos [](../../channels/using/creating-a-multilingual-email.md)multilingües), etc.
* Canales en los que se puede establecer contacto con el perfil, que contiene la dirección de correo electrónico del destinatario, el número de teléfono móvil y la información de exclusión.
* Dirección postal (para correo [](../../channels/using/about-direct-mail.md)directo) y zona horaria del contacto (para [programar mensajes en su huso horario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorización de acceso, que indica la unidad organizativa del destinatario (para [administrar permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Envío y seguimiento de registros {#sending-and-tracking-logs}

Las fichas **[!UICONTROL Sending logs]** y **[!UICONTROL Tracking logs]** agrupan la lista de entregas que se enviaron al perfil y todos los datos de seguimiento relacionados.

Para obtener más información sobre el envío y el seguimiento de registros, consulte las secciones de registros [de](../../sending/using/monitoring-a-delivery.md#delivery-logs) entrega y mensajes [de](../../sending/using/tracking-messages.md) seguimiento.

## Suscripciones {#subscriptions}

Las suscripciones del contacto se muestran en la ficha correspondiente. Para obtener más información sobre la suscripción a un servicio, consulte [esta sección](../../audiences/using/about-subscriptions.md).

La **[!UICONTROL Mobile App Subscriptions]** ficha hace referencia a las notificaciones push. Para obtener más información, consulte el canal de notificaciones [](../../channels/using/about-push-notifications.md) Push.

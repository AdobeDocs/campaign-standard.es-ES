---
title: Edición de perfiles
seo-title: Edición de perfiles
description: Edición de perfiles
seo-description: Descubra cómo editar los perfiles existentes y la información de contacto de acceso, los canales preferidos, los registros de seguimiento, las suscripciones, etc.
page-status-flag: no activado nunca
uuid: 6 fcdb 719-6149-48 fc-b 400-64 c 24 a 51487 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: administración de perfiles
discoiquuid: 8 d 3 ba 7 bf -90 ae -4 c 6 d-aaeb-a 48572 a 69 f 2 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Editing profiles{#editing-profiles}

## Accessing profile properties {#accessing-profile-properties}

Para editar un perfil existente y consultar los datos asociados a él, o modificarlos, los pasos son los siguientes:

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. Seleccione un contacto.
1. Click the **[!UICONTROL Edit profile properties]** icon to access the profile's detailed information.

   ![](assets/profile_creation2.png)

   La ventana de propiedades del perfil ofrece varias fichas que proporcionan acceso a toda la información de perfil.

   Otras fichas también pueden aparecer según los recursos personalizados que se hayan creado o ampliado en Adobe Campaign. For more information about custom resources, see [About custom resources](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >You can only modify the information in the **[!UICONTROL General]** tab - except for the **[!UICONTROL Traceability]** section.

También es posible utilizar la edición de perfiles mediante la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

Tema relacionado:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envío en la zona horaria del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## General profile data {#general-profile-data}

The **[!UICONTROL General]** tab groups the following information about the profile:

* Contact information, which contains the recipient's first name, last name, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canales en los que se puede establecer contacto con el perfil, que contiene la dirección de correo electrónico del destinatario, el número de teléfono móvil y la información de exclusión.
* Postal address (for [direct mail](../../channels/using/about-direct-mail.md)), and the contact's time zone (to [schedule messages in its time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Access authorization, which indicates the recipient's organisational unit (to [manage permissions](../../administration/using/about-access-management.md)). See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

The **[!UICONTROL Sending logs]** and **[!UICONTROL Tracking logs]** tabs group the list of deliveries that were sent to the profile, and all related tracking data.

For more on sending and tracking logs, refer to the [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) and the [tracking messages](../../sending/using/tracking-messages.md) sections.

## Subscriptions {#subscriptions}

Las suscripciones de los contactos se enumeran en la ficha correspondiente. For more on subscribing to a service, refer to [this section](../../audiences/using/about-subscriptions.md).

The **[!UICONTROL Mobile App Subscriptions]** tab refer to the push notifications. For more information, refer to the [Push notification](../../channels/using/about-push-notifications.md) channel.

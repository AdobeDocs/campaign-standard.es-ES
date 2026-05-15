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
TQID: https://experienceleague.adobe.com/hTCybEq1Hfh1fxXd5JGjRWmGZXzXNebtf42NZnEMZ5c
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 7%

---

# Edición de perfiles{#editing-profiles}

## Acceso a propiedades de perfil {#accessing-profile-properties}

Para editar un perfil existente y consultar los datos asociados a él o modificarlo, los pasos son los siguientes:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta **[!UICONTROL Customer profiles]** o en la ficha **[!UICONTROL Profiles]**.
1. Seleccione un contacto.
1. Haga clic en el icono **[!UICONTROL Edit profile properties]** para acceder a la información detallada del perfil.

   ![](assets/profile_creation2.png)

   La ventana de propiedades del perfil ofrece varias pestañas que proporcionan acceso a toda la información del perfil.

   También pueden aparecer otras pestañas en función de los recursos personalizados que se hayan creado o ampliado en Adobe Campaign. Para obtener más información acerca de los recursos personalizados, vea [Acerca de los recursos personalizados](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Solo puede modificar la información en la ficha **[!UICONTROL General]**, excepto en la sección **[!UICONTROL Traceability]**.

También es posible editar perfiles mediante la API de Adobe Campaign Standard. Para obtener más información, consulte la [documentación específica](../../api/using/updating-profiles.md).

Temas relacionados:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envío en el huso horario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Datos generales de perfil {#general-profile-data}

La ficha **[!UICONTROL General]** agrupa la siguiente información sobre el perfil:

* Información de contacto, que contiene el nombre, apellidos, fecha de nacimiento, foto, idioma preferido (para [correos electrónicos multilingües](../../channels/using/creating-a-multilingual-email.md)), etc. del destinatario.
* Canales en los que se puede contactar con el perfil, que contiene la dirección de correo electrónico del destinatario, el número de teléfono móvil y la información de exclusión.
* Dirección postal (para [correo postal](../../channels/using/about-direct-mail.md)) y zona horaria del contacto (para [programar mensajes en su zona horaria](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorización de acceso, que indica la unidad organizativa del destinatario (para [administrar permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Registros de envío y seguimiento {#sending-and-tracking-logs}

Las fichas **[!UICONTROL Sending logs]** y **[!UICONTROL Tracking logs]** agrupan la lista de envíos que se enviaron al perfil y todos los datos de seguimiento relacionados.

Para obtener más información sobre el envío y los registros de seguimiento, consulte las secciones [registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs) y [mensajes de seguimiento](../../sending/using/tracking-messages.md).

## Suscripciones {#subscriptions}

Las suscripciones del contacto se enumeran en la pestaña correspondiente. Para obtener más información sobre la suscripción a un servicio, consulte [esta sección](../../audiences/using/about-subscriptions.md).

La pestaña **[!UICONTROL Mobile App Subscriptions]** hace referencia a las notificaciones push. Para obtener más información, consulte el canal [Notificación push](../../channels/using/about-push-notifications.md).

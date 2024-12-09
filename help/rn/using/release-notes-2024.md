---
title: Notas de la versión de 2024
description: Esta página enumera todas las versiones de 2024 de Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# Notas de la versión de 2024 {#release-notes-2024}

## Versión 24.1: versión de invierno de 2024 {#winter-24}

### Mejoras {#e-rn-improvements}

* **Notificaciones push de Android**: Adobe Campaign Standard 24.1 utiliza las API HTTP v1 para enviar mensajes de notificación push de Android a fin de garantizar la compatibilidad con los próximos cambios de FCM. Obtenga más información en [esta nota técnica](../../administration/using/push-technote.md).

* **Notificaciones push de iOS**: Adobe Campaign Standard 24.1 ahora admite certificados de autenticación p8 para notificaciones push de iOS. Su implementación debe adaptarse para activar estos cambios. Obtenga más información en [esta nota técnica](../../administration/using/push-technote.md).

* **Cancelación de suscripción a una lista en un clic**: a partir del 1 de junio de 2024, Google y Yahoo! exigirán a los remitentes que cumplan con la cancelación de la suscripción a una lista con un clic. Campaign ahora admite esta posibilidad de forma predeterminada. Obtenga más información en [esta sección](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infraestructura**: la base de datos Postgres se ha actualizado de la versión 11.22 a la versión 12.17.

* **Seguimiento de CTA**: cuando los usuarios abren y hacen clic en una URL personalizada, ahora se realiza un seguimiento de la URL personalizada resuelta en lugar de la URL personalizada codificada. Este cambio no está habilitado de forma predeterminada. Para habilitarlo en la instancia de Campaign, póngase en contacto con su representante de Adobe.

* **Lista desplegable de campos de personalización**: al crear plantillas de mensajes de correo electrónico transaccionales en Adobe Experience Manager, ahora puede seleccionar campos de personalización en una lista desplegable. Este cambio no está habilitado de forma predeterminada. Para habilitarlo en la instancia de Campaign, póngase en contacto con su representante de Adobe.

### Correcciones {#e-rn-fixes}

* Se ha corregido un problema que impedía que las direcciones de correo electrónico devueltas se eliminaran de la cuarentena pasados 30 días. (CAMP-52977)
* Se ha corregido un problema que detenía el flujo de trabajo de Alerta de envío con el siguiente error: `division by zero`. (CAMP-49786)


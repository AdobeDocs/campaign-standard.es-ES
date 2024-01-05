---
title: Próximos cambios del canal de notificaciones push
description: Próximos cambios del canal de notificaciones push
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 10%

---

# Próximos cambios del canal de notificaciones push {#push-upgrade}

Puede utilizar Campaign para enviar notificaciones push a dispositivos Android y iOS. Para ello, Campaign se basa en servicios de suscripción específicos. Algunos cambios importantes en el servicio Android Firebase Cloud Messaging (FCM) se lanzarán el 24.1 de invierno de 2024 y afectarán a la implementación de Adobe Campaign. Además, para las aplicaciones de iOS, el Adobe está cambiando la forma de permitir que los administradores configuren los certificados.

## ¿Qué ha cambiado? {#push-changes}

### Android {#push-android}

Como parte del esfuerzo continuo de Google por mejorar sus servicios, las API de FCM existentes dejarán de usarse el **20 de junio de 2024**. Obtenga más información acerca del protocolo HTTP de Firebase Cloud Messaging en [Documentación de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Actualmente, Adobe Campaign Standard utiliza las API heredadas de HTTP para enviar mensajes de notificación push de Android y realizará cambios en los próximos meses para actualizar a las API HTTP v1.

### iOS {#push-ios}

Adobe también actualizará Adobe Campaign Standard para el canal de notificaciones push de iOS y cambiará la forma en que permitimos a los administradores configurar certificados para sus aplicaciones de iOS. A partir de la versión de invierno de 24.2 2024, los administradores deberán cargar los certificados de iOS a través de la interfaz de usuario de Adobe Campaign Standard, en las propiedades de su aplicación móvil.

## ¿Se ha visto afectado? {#push-impact}

Como usuario Campaign Standard, si envía mensajes de notificaciones push a sus audiencias, se verá afectado.

## ¿Cómo realizar la migración? {#push-migration}

Estas actualizaciones requieren una actualización de la compilación de Campaign Standard a la versión de invierno de 24.1 de 2024, ya que afectan a la configuración del canal móvil y a la administración de permisos.

Próximamente se proporcionarán instrucciones detalladas para facilitar un proceso de transición sin contratiempos.

Nuestro Equipo de Atención al Cliente estará disponible para ayudarle durante esta transición. También podemos organizar seminarios web y sesiones de capacitación para cubrir los aspectos técnicos y las mejores prácticas para la transición.

Mientras tanto, se recomienda dedicar este tiempo a revisar la configuración y personalización actual de Adobe Campaign Standard para que pueda realizar los cambios que sean necesarios.

Si tiene alguna duda o pregunta inmediata, no dude en ponerse en contacto con nuestro equipo de asistencia.

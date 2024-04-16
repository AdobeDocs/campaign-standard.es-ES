---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: ce90272c423400163d5ff497c6995a1bf1927ee4
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---


# Última versión{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versión 24.1: versión de invierno de 2024 {#winter-24}

### Mejoras {#e-rn-improvements}

Adobe Campaign Standard 24.1 utiliza las API HTTP v1 para enviar mensajes de notificación push de Android a fin de garantizar la compatibilidad con los próximos cambios de FCM. Obtenga más información en [esta nota técnica](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 ahora admite certificados de autenticación p8 para notificaciones push de iOS. Su implementación debe adaptarse para activar estos cambios. Obtenga más información en [esta nota técnica](../../administration/using/push-technote.md).

A partir del 1 de junio de 2024, Google y Yahoo! exigirán a los remitentes que cumplan con la cancelación de la suscripción a una lista con un clic. Campaign ahora admite esta posibilidad de forma predeterminada. Obtenga más información en [esta sección](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

### Correcciones {#e-rn-fixes}

* Se ha corregido un problema que impedía que las direcciones de correo electrónico devueltas se eliminaran de la cuarentena pasados 30 días. (CAMP-52977)
* Se ha corregido un problema que detenía el flujo de trabajo de Alerta de envío con el siguiente error: `division by zero`. (CAMP-49786)


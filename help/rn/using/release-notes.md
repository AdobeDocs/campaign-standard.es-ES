---
title: Últimas notas de la versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 0beb4934d1412c3f64d28106f9243673907629f3
workflow-type: ht
source-wordcount: '497'
ht-degree: 100%

---


# Últimas notas de la versión {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

<!--
## Early release notes {#e-new-release}

This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).
-->

## Versión 24.2: versión de verano de 2024 {#summer-24}

**Fecha de lanzamiento**: agosto de 2024 (disponibilidad limitada) - [Más información](../../rn/using/release-planning.md).

### Mejora {#summer-24-rn-improvements}

**Migración a la credencial OAuth de servidor a servidor**

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. Adobe realizará la migración de JWT a OAuth para sus integraciones de salida, como la integración de Campaign-Analytics o la integración de Activadores de Experience Cloud.

Si ha implementado integraciones entrantes con Campaign y utiliza [las API de Campaign](../../api/using/get-started-apis.md), debe migrar su cuenta técnica según se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio (JWT) existentes dejarán de funcionar el **27 de enero de 2025**.

### Correcciones {#summer-24-rn-fixes}

* Se ha corregido un problema que hacía que el planificador del flujo de trabajo se iniciara antes de la hora programada. (CAMP-55412)
* Se ha corregido un problema que provocaba un error al duplicar campos personalizados en notificaciones push transaccionales. (CAMP-54459)
* Se han corregido problemas que afectaban a la posibilidad de usar el planificador de hora y fecha para la mensajería in-app. (CAMP-54495)
* Se ha corregido un problema que provocaba que el seguimiento no funcionara al utilizar la función de alias de seguimiento personalizado y que todo el vínculo fuera dinámico. (CAMP-56044)
* Se ha corregido un problema que provocaba que se mostrara un número limitado de plantillas al utilizar la búsqueda para encontrar plantillas específicas. (CAMP-55273)
* Se han añadido los siguientes idiomas a la lista desplegable de idiomas preferidos: en_kz (Inglés - Kazajistán) y en_ua (Inglés - Ucrania). (CAMP-55336)
* Se ha corregido un problema que hacía que los botones de ajuste de hora no funcionaran en la configuración del planificador. (CAMP-53602)
* Se han corregido varios problemas de la interfaz de usuario relacionados con la barra de ajuste de hora en la configuración del planificador. (CAMP-55291)

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


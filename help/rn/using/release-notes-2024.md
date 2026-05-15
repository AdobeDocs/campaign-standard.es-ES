---
title: Notas de la versión 2024
description: Esta página enumera todas las versiones de 2024 de Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
TQID: https://experienceleague.adobe.com/L1RnV5WNdVWVn8oRUtFp4BDW-GzuP6xWZXpFYgupbQs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 93%

---

# Notas de la versión 2024 {#release-notes-2024}


## Versión 24.2: versión de verano de 2024 (LA) {#summer-24}

### Mejora {#summer-24-rn-improvements}

**Migración a la credencial OAuth de servidor a servidor**

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. Adobe realizará la migración de JWT a OAuth para sus integraciones de salida, como la integración de Campaign-Analytics o la integración de Activadores de Experience Cloud.

Si ha implementado integraciones entrantes con Campaign y utiliza [las API de Campaign](../../api/using/get-started-apis.md), debe migrar su cuenta técnica como se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio (JWT) existentes dejarán de funcionar el **27 de enero de 2025**.

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

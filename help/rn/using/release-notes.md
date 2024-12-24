---
title: Últimas notas de la versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# Últimas notas de la versión {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Notas de la versión preliminar {#e-new-release}

En esta sección se enumeran las mejoras y correcciones incluidas en la próxima versión de Campaign Standard.

>[!CAUTION]
>
>Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

### Versión 25.1: versión de invierno de 2025 {#winter-25}

#### Correcciones de seguridad {#winter-25-security}

* Esta versión incorpora correcciones de seguridad.
* Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado a la versión 10.1.33.

#### Otras correcciones {#winter-25-fixes}

* Se ha corregido un problema de duplicado en las plantillas (CAMP-56340)
* Se ha corregido una regresión del seguimiento cuando se utilizaban direcciones URL dinámicas en plantillas de Adobe Experience Manager (CAMP-51932)
* Se ha corregido un problema de rendimiento en el proceso de facturación (CAMP-56796)
* Se ha corregido un problema de codificación de HTML con el carácter `>` en las páginas web de JSSP (CAMP-56497)
* Se ha corregido un problema en la creación de informes dinámicos al usar la opción **Mostrar en las filas seleccionadas** (CAMP-55895)


## Versión 24.2: versión de verano de 2024 (LA) {#summer-24}

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

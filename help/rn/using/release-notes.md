---
title: Últimas notas de la versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---


# Últimas notas de la versión {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## Versión 25.2: verano de 2025 {#summer-25}

### Correcciones de seguridad {#summer-25-security}

* Esta versión incorpora correcciones de seguridad.
* Esta versión incorpora la siguiente actualización de seguridad: PostgreSQL 14.18, migración de CentOS a Rocky para instancias de Azure.

### Otras correcciones {#summer-25-fixes}

* Se ha mejorado la administración del agotamiento de secuencia para mejorar la fiabilidad del sistema. (CAMP-57281)
* Actualizaciones generales de estabilización del producto. (CAMP-57339)
* Se ha mejorado el sistema de informes dinámico para mejorar la solidez y reducir las discrepancias de datos. (CAMP-58157)
* Se ha corregido un problema que provocaba que los menús desplegables no ajustaran el texto correctamente. (CAMP-57360)
* Se ha actualizado la funcionalidad de creación de informes para evitar que los usuarios consulten datos de más de dos años de antigüedad. (CAMP-59262)

## Versión 25.1.2 {#25.1.2}

### Correcciones de seguridad {#25.1.2-security}

* Esta versión incorpora correcciones de seguridad.
* Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado a la versión 10.1.36.

### Otras correcciones {#25.1.2-fixes}

* Se ha corregido un problema con el análisis de token que impedía que los usuarios iniciaran sesión a través de IMS. (CAMP-57337)
* Se ha mejorado el mecanismo de generación de ID de secuencia automática para aumentar la fiabilidad del sistema. (CAMP-57281)

## Versión 25.1: versión de invierno de 2025 {#winter-25}

### Correcciones de seguridad {#winter-25-security}

* Esta versión incorpora correcciones de seguridad.
* Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado a la versión 10.1.33.

### Otras correcciones {#winter-25-fixes}


* Se ha corregido la URL “Esquema de datos” en la pantalla de resumen de suscripción (CAMP-56168, CAMP-56296)
* Se ha corregido un problema para omitir las reglas de fatiga cuando se utiliza la opción **Mensaje para enviar de inmediato** (CAMP-56866, CAMP-57033)
* Se ha corregido un problema de duplicado en las plantillas (CAMP-56340)
* Se ha corregido una regresión del seguimiento cuando se utilizaban direcciones URL dinámicas en plantillas de Adobe Experience Manager (CAMP-51932)
* Se ha corregido un problema de rendimiento en el proceso de facturación (CAMP-56796)
* Se ha corregido un problema de codificación de HTML con el carácter `>` en las páginas web de JSSP (CAMP-56497)
* Se ha corregido un problema en la creación de informes dinámicos al usar la opción **Mostrar en las filas seleccionadas** (CAMP-55895)


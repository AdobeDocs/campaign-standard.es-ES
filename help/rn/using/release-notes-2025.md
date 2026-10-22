---
title: Notas de la versión 2025
description: Esta página enumera todas las versiones de 2025 de Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 9046db34-f610-4721-b6eb-92334149366d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e8d937ec-9046-41b5-834b-d22a624e0d37
    internal-label: Campaign overview
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 94%
---
# Notas de la versión 2025 {#release-notes-2025}

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

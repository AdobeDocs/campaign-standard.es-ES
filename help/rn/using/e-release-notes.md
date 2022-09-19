---
title: Notas de las versiones anteriores
description: Notas de las versiones anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 20a59e064afeb93a2a6260439b09790692971071
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---


# Notas de las versiones anteriores {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 22.3: otoño/invierno de 2022 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}


**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.
-->

### Actualización de seguridad{#e-rn-security}

Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado de la versión 7.0 a la 8.0.

### Correcciones{#e-rn-fixes}

* Se ha corregido un problema con los informes programados, que se activaban una hora antes del horario programado. (CAMP-51502)
* Se ha corregido un problema en los indicadores de Entrega del panel Entrega que no coincidían con los Registros de envío (nms:broadLogRcp). (CAMP-51127)
* Se ha corregido un problema que impedía la extensión de recursos personalizados con el conector ACS (oferta principal). (CAMP-51033)
* Se ha mejorado el proceso de publicación de las respuestas de solicitudes de privacidad para evitar demoras. (CAMP-50613)
---
title: Notas de la versión anteriores
description: Notas de la versión anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: e74ce4aea097e5078aabf83f424e855db72b04a1
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 21%

---


# Notas de la versión anteriores {#e-new-release}

En esta página se describen las mejoras y correcciones incluidas en la próxima versión del Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 22.3: septiembre de 2022 {#e-rn-2022}

**Mejoras**

**Accesibilidad**

Campaign Standard 2.3 incluye correcciones y mejoras de accesibilidad que facilitan a los usuarios navegar y sacar el máximo partido de Adobe Campaign.

Estas funciones se publican en Disponibilidad limitada y se implementan únicamente en un conjunto de clientes. Para habilitar estas mejoras en los entornos de Campaign, póngase en contacto con el representante de Adobe.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

**Actualización de seguridad**

Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado de la versión 7.0 a la versión 8.0.

**Correcciones**

* Se ha corregido un problema con los informes programados, que se activaban una hora antes de la hora programada. (CAMP-51502)
* Se ha corregido un problema en los indicadores de Entrega del panel Envío que no coincidían con Registros de envío (nms:broadLogRcp). (CAMP-51127)
* Se ha corregido un problema que impedía la extensión de recursos personalizados con el conector ACS (oferta principal). (CAMP-51033)
* Se ha mejorado el proceso de publicación de las respuestas de solicitudes de privacidad para evitar demoras. (CAMP-50613)
---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 20%

---


# Última versión{#latest-release}

![Panel de control de Campaign](assets/do-not-localize/cp-icon.png) **Nueva versión de Panel de control de Campaign**. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es){target=&quot;_blank&quot;}.


## Versión 22.3: otoño/invierno de 2022 {#sept-22}

### Mejora{#rn-improvements}

**Accesibilidad**

Campaign Standard 2.3 incluye correcciones y mejoras de accesibilidad que facilitan a los usuarios navegar y sacar el máximo partido de Adobe Campaign.

Estas funciones se publican en Disponibilidad limitada y se implementan únicamente en un conjunto de clientes. Para habilitar estas mejoras en los entornos de Campaign, póngase en contacto con el representante de Adobe.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Actualización de seguridad{#rn-security}

Esta versión incorpora la siguiente actualización de seguridad: Apache Tomcat se ha actualizado de la versión 7.0 a la versión 8.0.

### Correcciones{#e-rn-fixes}

* Se ha corregido un problema con los informes programados, que se activaban una hora antes de la hora programada. (CAMP-51502)
* Se ha corregido un problema en los indicadores de Entrega del panel Envío que no coincidían con Registros de envío (nms:broadLogRcp). (CAMP-51127)
* Se ha corregido un problema que impedía la extensión de recursos personalizados con el conector ACS (oferta principal). (CAMP-51033)
* Se ha mejorado el proceso de publicación de las respuestas de solicitudes de privacidad para evitar demoras. (CAMP-50613)


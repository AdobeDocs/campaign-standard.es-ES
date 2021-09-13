---
title: Introducción al modelo de datos de Campaign Standard
description: Enriquezca el modelo de datos de Campaign Standard con campos y recursos personalizados y amplíe las API de REST para exponer los campos extendidos.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 31%

---

# Introducción al modelo de datos de Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modelo de datos</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Recursos personalizados</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Trabajo con API</a></p></td></tr>
</table>

Amplíe el modelo de datos de Campaign Standard con sus propios campos y recursos y supervise todos los cambios del modelo de datos en una sola vista.

## Modelo de datos {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Los datos utilizados por Campaign se definen mediante diferentes recursos definidos en un **modelo de datos predefinido**. El modelo de datos muestra una estructura SQL predeterminada para un conjunto de recursos relacionados con el marketing: envío, audiencia, páginas de aterrizaje, perfil, etc. Cada recurso viene con filtros asociados, lo que le permite navegar por los recursos.

El menú **Diagnosis** permite enumerar los objetos técnicos generados por el Campaign Standard: esquemas de datos, páginas web, filtros, etc., que le permiten supervisar el modelo de datos y cualquier cambio que se realice en él.

Más información:

* [Conceptos del modelo de datos](../../developing/using/data-model-concepts.md)
* [Prácticas recomendadas del modelo de datos](../../developing/using/data-model-best-practices.md)
* [Descripción del modelo de datos](../../developing/using/datamodel-introduction.md)
* [Control de cambios en el modelo de datos](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

El Campaign Standard le permite **Enriquecer el modelo de datos predefinido** para crear sus propios recursos (por ejemplo, para agregar tablas de compra o producto), o ampliar los recursos existentes con nuevos campos. También puede configurar las pantallas de Campaign para optimizar la navegación a través de los nuevos recursos y campos que se han creado.

Además, puede **ampliar las API de REST del Campaign Standard** para que se muestren en los campos ampliados de las API para los perfiles de recursos personalizados. Esto le permite, por ejemplo, actualizar el perfil de un cliente con un código de promoción generado a partir de un sistema de facturación.

Más información:

* [Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Ampliación de la API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: Ampliación del recurso de perfil con un nuevo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabajo con API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con las API de Campaign Standard, cree integraciones para Adobe Campaign Standard y cree su propio ecosistema al interconectar Campaign con el panel de tecnologías que utiliza. [Introducción a las API de REST de Campaign Standard](../../api/using/get-started-apis.md)

## Recursos adicionales

* [Exportación e importación de recursos personalizados](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Exportación de datos de Campaign a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)

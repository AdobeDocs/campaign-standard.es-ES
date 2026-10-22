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
TQID: 'https://experienceleague.adobe.com/LHlfIZ24iApQfr6dL-x-nQViltSetibBgt1slLDsRi4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 24%
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

Los datos que usa Campaign se definen con diferentes recursos definidos en un **modelo de datos predefinido**. El modelo de datos muestra una estructura SQL predeterminada para un conjunto de recursos relacionados con el marketing: envío, audiencia, páginas de aterrizaje, perfil, etc. Cada recurso incluye filtros asociados, lo que le permite navegar por los recursos.

El menú **Diagnóstico** le permite enumerar los objetos técnicos generados por Campaign Standard: esquemas de datos, páginas web, filtros, etc., lo que le permite supervisar el modelo de datos y los cambios realizados en él.

Más información:

* [Conceptos del modelo de datos](../../developing/using/data-model-concepts.md)
* [Prácticas recomendadas del modelo de datos](../../developing/using/data-model-best-practices.md)
* [Descripción del modelo de datos](../../developing/using/datamodel-introduction.md)
* [Monitorización de cambios en el modelo de datos](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard le permite **Enriquecer el modelo de datos predefinido** para crear sus propios recursos (por ejemplo, para agregar tablas de compra o de productos) o para ampliar los recursos existentes con nuevos campos. También puede configurar las pantallas de Campaign para optimizar la navegación a través de los nuevos recursos y campos que se han creado.

Además, puede **ampliar las API de REST de Campaign Standard** para exponer en los campos ampliados de las API los perfiles de recursos personalizados. Esto le permite, por ejemplo, actualizar el perfil de un cliente con un código de promoción generado a partir de un sistema de facturación.

Más información:

* [Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Ampliación de la API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: Ampliación del recurso de perfil con un nuevo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabajo con API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con las API de Campaign Standard, cree integraciones para Adobe Campaign Standard y construya su propio ecosistema interconectando Campaign con el panel de tecnologías que utiliza. [Introducción a las API de REST de Campaign Standard](../../api/using/get-started-apis.md)

## Recursos adicionales

* [Exportación e importación de recursos personalizados](https://helpx.adobe.com/es/campaign/kb/acs-get-started-with-cusres.html)
* [Exportación de datos de Campaign a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)

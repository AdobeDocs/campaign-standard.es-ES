---
title: Introducción al modelo de datos de Campaign Standard
description: Enriquezca el modelo de datos de Campaign Standard con campos y recursos personalizados, y extienda las API de REST para exponer los campos extendidos.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ae70ca95cb282a694c41361d859b19385db5673
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 16%

---


# Introducción al modelo de datos de Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modelo de datos</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Recursos personalizados</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Trabajo con API</a></p></td></tr>
</table>

Amplíe el modelo de datos de Campaign Standard con sus propios campos y recursos, y supervise todos los cambios del modelo de datos en una sola vista.

## Modelo de datos {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Los datos utilizados por la Campaña se definen mediante diferentes recursos definidos en un modelo **de datos** predefinido. El modelo de datos muestra una estructura SQL lista para usar para un conjunto de recursos relacionados con el marketing: envío, audiencia, páginas de aterrizaje, perfil, etc. Cada recurso viene con filtros asociados, lo que le permite navegar por los recursos.

El menú **Diagnóstico** le permite realizar listas de los objetos técnicos generados por el Campaign Standard: esquemas de datos, páginas web, filtros, etc., que le permiten monitorear el modelo de datos y cualquier cambio realizado en él.

Más información:

* [Conceptos del modelo de datos](../../developing/using/data-model-concepts.md)
* [Prácticas recomendadas del modelo de datos](../../developing/using/data-model-best-practices.md)
* [Descripción del modelo de datos](../../developing/using/datamodel-introduction.md)
* [Control de cambios en el modelo de datos](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard permite **enriquecer el modelo** de datos predefinido para crear sus propios recursos (por ejemplo, para agregar tablas de compra o producto) o para ampliar los recursos existentes con nuevos campos. También puede configurar pantallas de Campaña para optimizar la navegación a través de los nuevos recursos y campos que se han creado.

Además, puede **ampliar las API** REST de Campaign Standard para que se muestren en los campos extendidos de las API para los Perfiles de recursos personalizados. Esto le permite, por ejemplo, actualizar el perfil de un cliente con un código promocional generado a partir de un sistema de facturación.

Más información:

* [Adición o ampliación de un recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Ampliación de la API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: Ampliación del recurso de perfil con un nuevo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabajo con API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con las API de Campaign Standard, cree integraciones para Adobe Campaign Standard y cree su propio ecosistema interconectando la Campaña con el panel de tecnologías que utilice. [Introducción a las API de Campaign Standard REST](../../api/using/get-started-apis.md)

## Recursos adicionales

* [Acerca de Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [Creación de recursos personalizados (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Exportación e importación de recursos personalizados](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)

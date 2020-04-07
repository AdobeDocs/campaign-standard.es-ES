---
title: Segmentación y direccionamiento
description: '"Obtenga información sobre perfiles, segmentación y creación de audiencias en Campaña: cree audiencias, importe contactos que compartan audiencias con las soluciones de Experience Cloud y evite la fatiga del marketing".'
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Segmentación y direccionamiento{#segmentation-and-targeting}

## Profiles {#profiles}

Use Adobe Campaign’s flexible data model to enrich your customer profile data and add new attributes or tables. A continuación, utilice estos perfiles de cliente para una segmentación, personalización y sistema de informes más precisos.

Los perfiles de Adobe Campaign representan todos los contactos almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil sea dirigido, calificado y rastreado individualmente. This means that a profile can be: a client, a prospect, an individual subscribed to a newsletter, a recipient, a user, or any other denomination depending on the organization.

La función perfiles del cliente integra todos los datos del cliente en un solo lugar:

![](assets/mkt_hist_view.png)

El Adobe Campaign propone diversos mecanismos para la adquisición de perfiles: recopilar datos en línea mediante [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md), mecanismos [de importación manuales o](../../automating/using/about-data-import-and-export.md)automatizados, entrada [](../../audiences/using/creating-profiles.md) directa en la interfaz de Adobe Campaign, creación masiva a través de API [de](../../api/using/about-campaign-standard-apis.md)Campaña.

**Temas relacionados:**

* Obtenga información sobre los distintos tipos de perfiles en la sección [Perfiles](../../audiences/using/about-profiles.md) .
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Obtenga información sobre cómo personalizar los datos, gestionar tareas de gestión de datos complejas, como cálculos, agregados, deduplicaciones y combinaciones, mediante las funciones de objetivo de [flujo de trabajo](../../automating/using/about-targeting-activities.md)

## Audiencias {#audiences}

Para permitirle entregar mensajes relevantes y eficaces y captar a sus clientes de manera eficaz, Adobe Campaign integra funcionalidades avanzadas de análisis y objetivo. Thanks to the workflows and the query editor, you can build audiences that will be targeted by your different campaigns, depending on the information that you have on them, their activities, their language, their preferences or their marketing history. This allows you to filter subscribed profiles for example, or create target audiences on an unlimited number of criteria.

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**Temas relacionados:**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Descubra cómo [compartir audiencias](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) con las soluciones de Experience Cloud

## Reglamento general de protección de datos {#general-data-protection-regulation}

El Reglamento General de Protección de Datos (GDPR) es la nueva normativa sobre privacidad de la Unión Europea que unifica y moderniza los requisitos de protección de datos. El RGPD se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residan en la UE. Además de las capacidades de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad en nuestra función de procesador de datos para incluir funciones adicionales, a fin de ayudarle a prepararse como controlador de datos para determinadas solicitudes de RGPD.

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

Las reglas de fatiga permiten a los especialistas en mercadotecnia establecer reglas comerciales globales de canal cruzado que excluyen automáticamente los perfiles sobre los que se solicitan campañas.

Para implementar reglas de fatiga, debe definir un número máximo de mensajes por perfil y seleccionar un período en el que se aplicará la regla. Durante la preparación del envío, los perfiles se excluyen del envío, si procede, en función del número de mensajes que ya se les hayan enviado.

**Temas relacionados:**

* Learn how to [design fatigue rules](../../sending/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../sending/using/about-typology-rules.md)
* Use [filter rules](../../sending/using/filtering-rules.md) to refine the audience of your messages

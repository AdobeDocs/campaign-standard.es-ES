---
title: Segmentación y segmentación
seo-title: Segmentación y segmentación
description: Segmentación y segmentación
seo-description: '" Obtenga información sobre perfiles, segmentación y creación de audiencias en Campaign: crear audiencias, importar contactos comparta audiencias con soluciones de Experience Cloud y evitar fatiga de marketing».'
page-status-flag: no activado nunca
uuid: 71 f 53808-0309-49 f 6-a 4 ee -3446 eac 9758 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d 8 c 8 a 318-9433-4 aec-b 378-fd 0 beb 50 e 9 fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

Use el modelo de datos flexible de Adobe Campaign para enriquecer los datos de perfil de clientes y agregar nuevos atributos o tablas. A continuación, use estos perfiles de cliente para una segmentación, personalización y creación de informes más precisas.

Los perfiles de Adobe Campaign representan todos los contactos almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil sea dirigido, calificado y rastreado individualmente. Esto significa que un perfil puede ser: un cliente, un posible cliente, una persona suscrita a una newsletter, un destinatario, un usuario o cualquier otra confesión según la organización.

La función de perfiles de cliente integra todos los datos de clientes en un solo lugar:

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**Temas relacionados:**

* Learn about different types of profiles in the [Profiles](../../audiences/using/about-profiles.md) section.
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

A fin de permitirle ofrecer mensajes relevantes y eficaces, y atraer a sus clientes de forma eficaz, Adobe Campaign integra funciones avanzadas de análisis y segmentación. Gracias a los flujos de trabajo y al editor de consultas, puede crear audiencias que serán objetivo por sus diferentes campañas, según la información que tenga sobre ellos, sus actividades, su idioma, sus preferencias o su historial de marketing. Esto le permite filtrar perfiles suscritos, por ejemplo, o crear audiencias de objetivo en un número ilimitado de criterios.

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**Temas relacionados:**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

El RGPD es la nueva ley de privacidad de la Unión Europea que armoniza y moderniza los requisitos de protección de datos. El RGPD se aplica a los clientes de Adobe Campaign que contienen datos para los sujetos de datos que residen en la UE. Además de las capacidades de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), estamos tomando esta oportunidad en nuestro rol de Procesador de datos para incluir capacidades adicionales, para facilitar su preparación como controlador de datos para ciertas solicitudes del RGPD.

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

Las reglas de fatiga permiten a los especialistas en mercadotecnia establecer reglas comerciales globales de múltiples canales que excluirán automáticamente los perfiles sobresolicitados de las campañas.

Para implementar reglas de fatiga, debe definir un número máximo de mensajes por perfil y seleccionar un período en el que se aplicará la regla. Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de mensajes que se hayan enviado.

**Temas relacionados:**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* Use [filter rules](../../administration/using/filtering-rules.md) to refine the audience of your messages

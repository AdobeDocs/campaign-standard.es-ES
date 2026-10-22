---
title: Enriquecimiento de la base de datos
description: Obtenga información sobre los distintos métodos para enriquecer la base de datos.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
TQID: 'https://experienceleague.adobe.com/LROFX17EE6zvJRbH4P--NjtiJLwanqeudAKzwnQj0BI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%
---
# Enriquecimiento de la base de datos{#enriching-the-database}

Campaign Standard ofrece varias herramientas para ayudarle a ampliar su base de datos de marketing. Esta sección detalla los diferentes métodos que puede utilizar para insertar datos en Campaign, con referencias a la documentación dedicada.

## Importación de datos mediante flujos de trabajo {#importing-data-through-workflows}

Los flujos de trabajo le permiten recopilar datos e importarlos en la base de datos de Campaign mediante el uso de [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) actividades.

La información genérica y las prácticas recomendadas al importar datos mediante flujos de trabajo se presentan en [esta sección](../../automating/using/about-data-import-and-export.md).

Además, puede configurar plantillas para importar datos. El uso de plantillas de importación es una práctica recomendada si necesita importar archivos con la misma estructura de forma regular.

Puede configurar dos tipos de plantillas:

* **Plantillas de flujo de trabajo**: se trata de flujos de trabajo preconfigurados que puede configurar una vez según sus necesidades y reutilizar cada vez que desee importar datos y actualizar la base de datos.

  Un ejemplo de plantilla de flujo de trabajo para importar datos se detalla en [esta sección](../../automating/using/creating-import-workflow-templates.md).

* **Importar plantillas de datos**: al igual que las plantillas de flujo de trabajo, se trata de plantillas basadas en flujos de trabajo que están configurados para cargar archivos y actualizar la base de datos. Una vez configuradas, están disponibles para los usuarios con una vista simplificada en el menú **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**.

  Para obtener más información sobre la importación de plantillas de datos, consulte la [documentación dedicada](../../automating/using/importing-data-with-import-templates.md).

## Recopilación de datos de páginas de aterrizaje {#collecting-data-from-landing-pages}

Las páginas de aterrizaje son formularios web que se pueden utilizar para recopilar datos y crear o actualizar la información existente en la base de datos.

El principio es el siguiente:

* Cree y diseñe su página de aterrizaje añadiendo campos de entrada para recopilar datos (nombre, apellidos, correo electrónico, etc.).
* Asigne cada campo de entrada con el campo correspondiente de la base de datos.
* Hacer que la página de aterrizaje esté disponible en línea a través de un sitio web o mediante un vínculo directo a un mensaje.

Para obtener más información sobre las páginas de aterrizaje, consulte la [documentación dedicada](../../channels/using/getting-started-with-landing-pages.md).

## Sincronización de perfiles de Microsoft Dynamics 365

La integración de Campaign Standard con Microsoft Dynamics 365 le permite pasar datos de contacto de Microsoft Dynamics 365 a la base de datos de Campaign.
Estos contactos se pueden ver en la lista Perfiles y se pueden segmentar en campañas de marketing.

Para obtener más información sobre esta integración, consulte la [documentación dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Tenga en cuenta que el conector Campaign Standard-Microsoft Dynamics 365 está actualmente en disponibilidad limitada y que está sujeto a varias limitaciones que se detallan en la documentación.

## Importación de datos mediante llamadas API

Las API de Campaign Standard le permiten realizar operaciones para actualizar la base de datos, como la creación, actualización o eliminación de perfiles o servicios.

Para obtener más información sobre cómo usar las API, consulte la [documentación dedicada](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Antes de realizar la creación o actualización masiva de perfiles mediante llamadas a la API, compruebe las limitaciones de escala correspondientes a su acuerdo de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/es/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

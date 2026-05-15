---
title: Introducción a orígenes y destinos
description: Obtenga más información sobre orígenes y destinos de Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
TQID: https://experienceleague.adobe.com/r1rASYXuo-xeKH80eZVYG-jUhxy93GuTa8CIDyouSNY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 314
ht-degree: 64%

---

# Introducción a orígenes y destinos {#rtcdp}

## Acerca de los orígenes y destinos

Con Adobe Experience Platform, puede compartir datos entre Campaign Standard y la plataforma de datos del cliente en tiempo real de Adobe (RTCDP). Esto le permite dirigirse a los públicos de Adobe Experience Platform en sus flujos de trabajo de Campaign y, a continuación, enviar los datos de la plataforma de datos del cliente en tiempo real de Adobe relacionados con estos públicos, como envíos, aperturas y clics.

* Con **Destinos**, ingrese audiencias de Adobe Experience Platform en Campaign Standard. Esto le permite activar los datos conocidos y desconocidos para sus campañas de marketing.
* Con **Sources**, exporte los datos de Campaign Standard (por ejemplo, envíos, aperturas, clics) a Adobe Experience Platform. Esto le permite centralizar los datos que recopila de orígenes diferentes en un solo lugar y utilizar las perspectivas obtenidas de él para hacer más.


>[!IMPORTANT]
>
>Tenga en cuenta los límites del almacenamiento de SFTP, el almacenamiento de la base de datos y el perfil activo según el contrato de Adobe Campaign al usar esta funcionalidad.

Para obtener una descripción más detallada de la plataforma de datos del cliente en tiempo real de Adobe, los destinos y los orígenes, consulte estas páginas:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es)
* [Documentación sobre los destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=es)
* [Documentación sobre los orígenes](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es)

## Conexión de Campaign Standard con Adobe Experience Platform

Para poder compartir datos entre Adobe Experience Platform y Campaign Standard, primero debe conectar Adobe Campaign como **destino** y conectar su ubicación de AWS S3 o Azure Blob Storage como **Source** en Adobe Experience Platform.

Una vez configurados los conectores, puede configurar una importación de datos o exportación a Campaign Standard mediante flujos de trabajo.

![](assets/rtcdp-schema.png)

Para obtener más información sobre cómo configurar estos procesos de importación y exportación, consulte estas secciones:

* [Ingesta de públicos de Adobe Experience Platform en Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportación de datos de Campaign a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)

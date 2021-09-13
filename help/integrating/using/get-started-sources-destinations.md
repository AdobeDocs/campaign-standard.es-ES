---
title: Introducción a orígenes y destinos
description: Obtenga más información sobre orígenes y destinos de Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 64%

---

# Introducción a orígenes y destinos {#rtcdp}

## Acerca de los orígenes y destinos

Con Adobe Experience Platform, puede compartir datos entre el Campaign Standard y la plataforma de datos del cliente en tiempo real de Adobe (RTCDP). Esto le permite dirigirse a las audiencias de Adobe Experience Platform en sus flujos de trabajo de Campaign y, a continuación, enviar los datos de la plataforma de datos del cliente en tiempo real de Adobe relacionados con estas audiencias, como envíos, aperturas y clics.

* Con **Destinations**, incorpore audiencias de Adobe Experience Platform en Campaign Standard. Esto le permite activar los datos conocidos y desconocidos para sus campañas de marketing.
* Con **Sources**, exporte los datos del Campaign Standard (por ejemplo, envíos, aperturas, clics) a Adobe Experience Platform. Esto le permite centralizar los datos que recopila de orígenes diferentes en un solo lugar y utilizar las perspectivas obtenidas de él para hacer más.


>[!IMPORTANT]
>
>Tenga en cuenta los límites del almacenamiento de SFTP, el almacenamiento de la base de datos y el perfil activo según el contrato de Adobe Campaign al usar esta funcionalidad.

Para obtener una descripción más detallada de la plataforma de datos del cliente en tiempo real de Adobe, los destinos y los orígenes, consulte estas páginas:

* [Plataforma de datos del cliente en tiempo real de Adobe](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es)
* [Documentación de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=es)
* [Documentación de orígenes](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es)

## Conectar Campaign Standard con Adobe Experience Platform

Para poder compartir datos entre Adobe Experience Platform y Campaign Standard, primero debe conectar Adobe Campaign como **Destination** y conectar su ubicación de almacenamiento del blob de AWS S3 o Azure como **Source** en Adobe experience Platform.

Una vez configurados los conectores, puede configurar una importación de datos o exportación a Campaign Standard mediante flujos de trabajo.

![](assets/rtcdp-schema.png)

Para obtener más información sobre cómo configurar estos procesos de importación y exportación, consulte estas secciones:

* [Ingesta de audiencias de Adobe Experience Platform en Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportación de datos de Campaign a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)

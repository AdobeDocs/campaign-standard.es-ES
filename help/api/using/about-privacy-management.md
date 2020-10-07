---
title: Acerca de la administración de la privacidad
description: Más información sobre la administración de la privacidad con las API
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# Acerca de la administración de la privacidad {#about-privacy-management}

Las API de Campaign Standard proporcionan funciones que permiten el proceso automático de solicitudes relacionadas con las normativas de privacidad, como el RGPD y la CCPA.

Las acciones que puede realizar son las siguientes:

* Crear una nueva solicitud de privacidad,
* Monitorear una solicitud de privacidad,
* Recuperar un archivo de datos de privacidad,
* Administre el estado de exclusión de CCPA de un perfil.

El extremo de la API de privacidad es **/privacy/privacyTool**. La descripción del recurso PrivacyTool y los filtros asociados están disponibles en los metadatos del recurso. Consulte Mecanismo [de metadatos](../../api/using/metadata-mechanism.md).

La exclusión de CCPA se administra mediante el atributo de perfil **ccpaOptOut** .

Para obtener más información sobre Adobe Campaign Standard y el cumplimiento de la privacidad, consulte la documentación [](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html)dedicada.

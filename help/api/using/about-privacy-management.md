---
title: Acerca de la administración de privacidad
description: Obtenga más información acerca de la administración de la privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Acerca de la administración de privacidad {#about-privacy-management}

Las API de Campaign Standard proporcionan funciones que permiten el procesamiento automático de solicitudes relacionadas con regulaciones de privacidad como RGPD y CCPA.

Las acciones que puede realizar son las siguientes:

* Crear una nueva solicitud de privacidad,
* Monitorización de una solicitud de privacidad,
* Recuperación de un archivo de datos de privacidad,
* Administrar el estado de exclusión de CCPA de un perfil.

El punto final de la API de privacidad es **/privacy/privacyTool**. La descripción del recurso PrivacyTool y los filtros asociados están disponibles en los metadatos del recurso. Consulte [Mecanismo de metadatos](../../api/using/metadata-mechanism.md).

La exclusión de CCPA se administra mediante la variable **ccpaOptOut** atributo de perfil.

Para obtener más información sobre Adobe Campaign Standard y el cumplimiento de la privacidad, consulte la [documentación dedicada](../../start/using/privacy-requests.md).

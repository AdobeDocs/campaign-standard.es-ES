---
title: Acerca de la administración de la privacidad
description: Obtenga más información sobre la administración de la privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Acerca de la administración de la privacidad {#about-privacy-management}

Las API de Campaign Standard proporcionan funciones que permiten el procesamiento automático de solicitudes relacionadas con regulaciones de privacidad como el RGPD y la CCPA.

Las acciones que puede realizar son las siguientes:

* Cree una nueva solicitud de privacidad,
* Monitorizar una solicitud de privacidad,
* Recupere un archivo de datos de privacidad,
* Administre el estado de exclusión de la CCPA de un perfil.

El extremo de la API de privacidad es **/privacy/privacyTool**. La descripción del recurso PrivacyTool y los filtros asociados están disponibles en los metadatos del recurso. Consulte [Mecanismo de metadatos](../../api/using/metadata-mechanism.md).

La exclusión de CCPA se administra mediante el atributo de perfil **cpaOptOut**.

Para obtener más información sobre Adobe Campaign Standard y el cumplimiento de la privacidad, consulte la [documentación dedicada](../../start/using/privacy-requests.md).

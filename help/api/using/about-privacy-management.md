---
title: Acerca de la administración de la privacidad
description: Obtenga más información sobre la administración de la privacidad con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

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

Para obtener más información sobre Adobe Campaign Standard y el cumplimiento de la privacidad, consulte la [documentación dedicada](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html).

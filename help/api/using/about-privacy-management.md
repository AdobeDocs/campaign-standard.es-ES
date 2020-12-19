---
solution: Campaign Standard
product: campaign
title: Acerca de la administración de la privacidad
description: Más información sobre la administración de la privacidad con las API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

El extremo de la API de privacidad es **/privacy/privacyTool**. La descripción del recurso PrivacyTool y los filtros asociados están disponibles en los metadatos del recurso. Consulte [Mecanismo de metadatos](../../api/using/metadata-mechanism.md).

La exclusión de CCPA se administra mediante el atributo de perfil **cpaOptOut**.

Para obtener más información sobre el cumplimiento de normas de privacidad y Adobe Campaign Standard, consulte la [documentación dedicada](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html).

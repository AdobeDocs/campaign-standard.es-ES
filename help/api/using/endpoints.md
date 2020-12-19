---
solution: Campaign Standard
product: campaign
title: Puntos de conexión
description: Obtenga más información sobre los extremos de las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# Puntos de conexión {#endpoints}

Los extremos disponibles para la API de Adobe Campaign REST:

* **/profileAndServices**: interactuar con los campos predeterminados. No se puede acceder a los campos extendidos con este extremo.
* **/profileAndServicesExt**: interactuar con campos personalizados agregados durante la extensión de recursos personalizados de Perfil o Servicios. Para obtener más información sobre los recursos personalizados, consulte [esta sección](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interactuar con la API de mensajes transaccionales (el nombre del extremo de la API de mensajes transaccionales depende de la configuración de la instancia). Para obtener más información, consulte [esta sección](../../api/using/managing-transactional-messages.md).
* **/workflow/execute**: interactuar con flujos de trabajo. Para obtener más información, consulte [esta sección](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interactuar con la API de privacidad para permitir el proceso automático de solicitudes de privacidad. Para obtener más información, consulte [esta sección](../../api/using/creating-a-privacy-request.md).
* **/history**: recuperar el historial de marketing de los perfiles. Para obtener más información sobre los perfiles de cliente integrados en la Campaña, consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

De forma predeterminada, los recursos principales disponibles para las API **profileAndServices** y **profileAndServicesExt** son:

* **/perfil**: interactuar con perfiles de la base de datos de Campañas. Para agregar perfiles a un servicio, utilice el extremo **/service**. Para obtener más información sobre perfiles en Campaña, consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: administrar servicios de suscripción. Para obtener más información sobre los servicios en Campaña, consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos los demás recursos que se han ampliado o creado solo están disponibles mediante la API **ProfileAndServicesExt**. Deben estar vinculados al recurso **Perfil** para ser accesibles.

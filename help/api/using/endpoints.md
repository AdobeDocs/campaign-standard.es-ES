---
title: Puntos de conexión
description: Obtenga más información acerca de los extremos de las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 11%

---

# Puntos de conexión {#endpoints}

Los extremos disponibles para la API de REST de Adobe Campaign:

* **/profileAndServices**: interactúe con los campos predeterminados. No se puede acceder a los campos extendidos con este extremo.
* **/profileAndServicesExt**: interactúe con los campos personalizados agregados durante la extensión de recursos personalizados de perfil o servicios. Para obtener más información sobre los recursos personalizados, consulte [esta sección](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interactúe con la API de mensajes transaccionales (el nombre del extremo de la API de mensajes transaccionales depende de la configuración de su instancia). Para obtener más información, consulte [esta sección](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interactuar con flujos de trabajo. Para obtener más información, consulte [esta sección](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interactúe con la API de privacidad para permitir el procesamiento automático de solicitudes de privacidad. Para obtener más información, consulte [esta sección](../../api/using/creating-a-privacy-request.md).
* **/history**: recupere el historial de marketing de los perfiles. Para obtener más información sobre perfiles de clientes integrados en Campaign, consulte la [Documentación de Campaign](https://helpx.adobe.com/es/campaign/standard/audiences/using/integrated-customer-profile.html).

De manera predeterminada, los recursos principales disponibles para las API **profileAndServices** y **profileAndServicesExt** son:

* **/profile**: interactúe con los perfiles de la base de datos de Campaign. Para agregar perfiles a un servicio, use el extremo **/service**. Para obtener más información sobre los perfiles de Campaign, consulte la [Documentación de Campaign](https://helpx.adobe.com/es/campaign/standard/audiences/using/about-profiles.html).
* **/servicio**: administrar servicios de suscripción. Para obtener más información sobre los servicios de Campaign, consulte la [Documentación de Campaign](https://helpx.adobe.com/es/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos los demás recursos que se han ampliado o creado están disponibles únicamente a través de la API **ProfileAndServicesExt**. Deben estar vinculados al recurso **Profile** para que sea accesible.

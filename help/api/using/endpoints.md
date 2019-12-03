---
title: Puntos de conexión
description: Obtenga más información sobre los extremos de las API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# Puntos de conexión {#endpoints}

Los extremos disponibles para la API REST de Adobe Campaign:

* **/profileAndServices**: interactuar con los campos predeterminados. No se puede acceder a los campos extendidos con este extremo.
* **/profileAndServicesExt**: interactuar con campos personalizados agregados durante la extensión de recursos personalizados de Perfil o Servicios. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionAPI&gt;**: interactuar con la API de mensajes transaccionales (el nombre del extremo de la API de mensajes transaccionales depende de la configuración de la instancia). Para obtener más información, consulte [esta sección](../../api/using/managing-transactional-messages.md).
* **/workflow/execute**: interactuar con flujos de trabajo. Para obtener más información, consulte [esta sección](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interactuar con la API de privacidad para permitir el proceso automático de solicitudes de privacidad. Para obtener más información, consulte [esta sección](../../api/using/creating-a-privacy-request.md).
* **/history**: recuperar el historial de marketing de los perfiles. Para obtener más información sobre los perfiles de cliente integrados en Campaign, consulte la documentación [de](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)Campaign.

De forma predeterminada, los recursos principales disponibles para las API **profileAndServices** y **profileAndServicesExt** son:

* **/profile**: interactuar con perfiles de la base de datos de Campaign. Para agregar perfiles a un servicio, utilice el extremo **/servicio** . Para obtener más información sobre los perfiles de Campaign, consulte la documentación [de](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)Campaign.
* **/service**: administrar servicios de suscripción. Para obtener más información sobre los servicios de Campaign, consulte la documentación [de](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)Campaign.

>[!NOTE]
>
>Todos los demás recursos que se han ampliado o creado solo están disponibles a través de la **API ProfileAndServicesExt** . Deben estar vinculados al recurso **Perfil** para poder ser accesibles.

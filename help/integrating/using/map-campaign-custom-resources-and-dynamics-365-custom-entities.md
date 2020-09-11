---
title: Asignar recursos personalizados de Campaña y entidades personalizadas de Dynamics 365
description: Obtenga información sobre cómo asignar recursos y entidades en el contexto de la integración entre Adobe Campaign Standard y Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e11de4d4482400e62be2db076c88da5ae30d60cc
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---


# Asignar recursos de Campaña y entidades de Dynamics 365

Obtenga información sobre cómo asignar recursos personalizados y entidades personalizadas en el contexto de la integración entre Adobe Campaign Standard y Microsoft Dynamics 365.

>[!CAUTION]
>
>Esta capacidad no está disponible de forma predeterminada como parte del producto. La implementación requiere la participación de Adobe Consulting. Póngase en contacto con el representante de su Adobe para obtener más información.

## Requisitos previos

La integración [de](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365-Adobe Campaign Standard admite entidades personalizadas, lo que permite sincronizar las entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaña.

Los nuevos datos de los recursos personalizados se pueden utilizar para varios fines, como la segmentación y la personalización.

La integración admite tablas vinculadas y no vinculadas. La vinculación se admite hasta tres niveles (por ejemplo, nivel1->nivel2->nivel3).

>[!CAUTION]
>
>Si algún registro de recursos personalizados de Campaña contiene información personal, se aplican recomendaciones específicas. Obtenga más información [en esta sección](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Avisos

Al configurar los flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de recursos personalizados de Campaña son operaciones sensibles que deben realizar únicamente los usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe habilitarse en Dynamics 365 para las entidades personalizadas sincronizadas.
* Si un registro principal y un registro secundario vinculado se crean casi al mismo tiempo en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en la Campaña antes de su registro principal.

* Si el principal y el secundario están vinculados en la Campaña mediante la opción de vínculo **sencillo de cardinalidad** 1, el registro secundario permanecerá oculto e inaccesible (mediante la interfaz de usuario o la API) hasta que el registro principal llegue a la Campaña.

* (Suponiendo **1 vínculo** sencillo de cardinalidad en Campaña) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en Campaña antes de que el registro principal aparezca en la Campaña (no es probable, pero sí una posibilidad remota), esa actualización o eliminación no se procesará en la Campaña y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión tendrá que encargarse por separado en la parte de la Campaña, ya que en Dynamics 365 ya no hay ningún registro que eliminar o actualizar.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay forma de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 vínculo** sencillo de cardinalidad para acceder a esos registros.

En esta sección [](../../developing/using/key-steps-to-add-a-resource.md)encontrará una descripción general más completa de los recursos personalizados de Campaña.

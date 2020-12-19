---
solution: Campaign Standard
product: campaign
title: Asignación de recursos personalizados de Campaign y entidades personalizadas de Dynamics 365
description: Obtenga información sobre cómo asignar recursos y entidades en el contexto de la integración entre Adobe Campaign Standard y Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 10%

---


# Asignar recursos de Campaña y entidades de Dynamics 365

Obtenga información sobre cómo asignar recursos personalizados y entidades personalizadas en el contexto de la integración entre Adobe Campaign Standard y Microsoft Dynamics 365.

>[!CAUTION]
>
>Esta capacidad no está disponible de forma predeterminada como parte del producto. La implementación requiere la participación de Adobe Consulting. Póngase en contacto con el representante de su Adobe para obtener más información.

## Requisitos previos

La [integración de Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) admite entidades personalizadas, lo que permite sincronizar las entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaña.

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

* Si el principal y el secundario están vinculados en el lado de la Campaña mediante la opción **1 vínculo simple de cardinalidad**, el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a la Campaña.

* (Suponiendo **1 vínculo simple de cardinalidad** en la Campaña) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en la Campaña antes de que el registro principal se muestre en la Campaña (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en la Campaña y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión tendrá que encargarse por separado en la parte de la Campaña, ya que en Dynamics 365 ya no hay ningún registro que eliminar o actualizar.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay manera de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 vínculo simple de cardinalidad** para acceder a esos registros.

En esta sección [encontrará una descripción general más completa de los recursos personalizados de Campaña.](../../developing/using/key-steps-to-add-a-resource.md)

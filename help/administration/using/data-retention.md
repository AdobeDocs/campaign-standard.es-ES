---
title: Retención de datos
description: Obtenga información sobre los valores de retención predeterminados para las tablas estándar
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Retención de datos{#data-retention}

>[!NOTE]
>
>Los informes de datos solo están disponibles durante los últimos tres años. Para obtener más información sobre los períodos de retención de datos, póngase en contacto con los consultores de Adobe o con los administradores técnicos.

Las tablas de registro estándar de Campaign tienen períodos de retención preestablecidos que limitan la duración del almacenamiento de datos para evitar sobrecargar el sistema.

Los administradores técnicos de Adobe configuran los ajustes de retención de datos durante la implementación y los valores pueden variar en función de los requisitos de los clientes.

Póngase en contacto con los consultores o administradores técnicos de Adobe para obtener más información acerca de los períodos de retención que se aplican a su entorno o para establecer períodos de retención personalizados.

Tenga en cuenta que, con la funcionalidad estándar de flujo de trabajo, es posible configurar períodos de retención para cualquier tabla personalizada.

A continuación se muestran los períodos de retención predeterminados para las tablas estándar. Siempre que sea posible y según el uso de los datos, Adobe le recomienda pasar a los períodos de retención recomendados para mejorar el rendimiento de la instancia de Campaign.

* **Seguimiento consolidado**: 6 meses (recomendado: 1 mes)
* **Registros de envío**: 6 meses (recomendado: 1 mes)
* **Registros de seguimiento**: 6 meses (recomendado: 1 mes)
* **Eventos**: 1 mes
* **Estadísticas del procesamiento de eventos**: 6 meses (recomendado: 1 mes)
* **Eventos archivados**: 6 meses (recomendado: 1 mes)
* **Entidades temporales**: 7 días
* **Eventos de mapa ignorados**: 1 mes
* **Alertas de envío**: 1 mes
* **Auditoría de exportación**: 6 meses (recomendado: 1 mes)
* **Envíos**: 2 años

## Período de retención para envíos {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

A partir del 1 de junio de 2025, solo permanecerán disponibles en el sistema las entregas de los últimos dos años. Encontrará más detalles a continuación:

* Cualquier envío de más de dos años se eliminará de forma permanente y ya no será accesible.
* Esta limpieza incluye solo las entregas enviadas y fallidas; las entregas recurrentes, las entregas en borrador y las plantillas no se verán afectadas.
* Una vez que se elimine una entrega, cualquier información de envío o seguimiento vinculada también se eliminará de forma permanente.
* Las plantillas de marketing o de envío transaccional no se eliminarán.
* En el caso de las entregas recurrentes, no se eliminan las entregas secundarias con un periodo de acumulación establecido como mes o año.

Si desea acelerar procesos como el flujo de trabajo **[!UICONTROL Copy headers from delivery templates]**, se puede reducir el período de retención de envíos. Para ello, póngase en contacto con su representante de Adobe.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->



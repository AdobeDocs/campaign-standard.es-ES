---
title: Retención de datos
description: Obtenga información sobre los valores de retención predeterminados para las tablas estándar
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 99c092bc40c9176a25a6ec2a164ee1d3f85d5cbe
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---

# Retención de datos{#data-retention}

>[!NOTE]
>
>Los informes de datos solo están disponibles durante los últimos tres años. Para obtener más información sobre los períodos de retención de datos, póngase en contacto con los consultores de Adobe o con los administradores técnicos.

Las tablas de registro estándar de Campaign tienen períodos de retención preestablecidos que limitan la duración del almacenamiento de datos para evitar sobrecargar el sistema.

Los administradores técnicos de Adobe configuran los ajustes de retención de datos durante la implementación y los valores pueden variar en función de los requisitos de los clientes.

Póngase en contacto con los consultores de Adobe o con los administradores técnicos para obtener más información acerca de los períodos de retención que se aplican a su entorno o para establecer períodos de retención personalizados.

Tenga en cuenta que, con la funcionalidad estándar de flujo de trabajo, es posible configurar períodos de retención para cualquier tabla personalizada.

A continuación se muestran los períodos de retención predeterminados para las tablas estándar. Siempre que sea posible y según el uso de los datos, el Adobe le sugiere pasar a los períodos de retención recomendados para mejorar el rendimiento de la instancia de Campaign.

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

## Período de retención para envíos {#deliveries}

De forma predeterminada, el período de retención de envíos es ilimitado.

Sin embargo, si hay un gran volumen de envíos en su instancia, puede actualizar la opción **NmsCleanup_DeliveryPurgeDelay** disponible en el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]**.

Cada vez que se ejecute el flujo de trabajo **[!UICONTROL Database cleanup]**, se eliminarán los envíos que cumplan las condiciones establecidas para esta opción.

Esta acción puede ayudar a acelerar procesos como el flujo de trabajo **[!UICONTROL Copy headers from delivery templates]**.

>[!NOTE]
>
>Obtenga más información sobre los flujos de trabajo técnicos en [esta sección](technical-workflows.md).


El valor predeterminado de la opción **NmsCleanup_DeliveryPurgeDelay** es `-1`. En este caso, no se elimina ninguna entrega.

Por ejemplo, si lo establece en `180`, los envíos que no sean de plantilla y que no se hayan actualizado en los últimos 180 días se eliminarán cuando se ejecute el flujo de trabajo **[!UICONTROL Database cleanup]**.

>[!NOTE]
>
>* Las plantillas de marketing o de envío transaccional no se eliminarán.
>
>* En el caso de las entregas recurrentes, no se eliminan las entregas secundarias con un periodo de acumulación establecido como mes o año.

Al actualizar la opción **NmsCleanup_DeliveryPurgeDelay**, se recomienda continuar gradualmente con varias iteraciones. Por ejemplo, puede empezar estableciendo el valor en 300 días, luego en 180 días, luego en 120 días, etc., asegurándose de que las iteraciones se produzcan al menos con una diferencia de 2 días. De lo contrario, el flujo de trabajo **[!UICONTROL Database cleanup]** puede tardar mucho más debido al gran número de envíos que se van a eliminar.


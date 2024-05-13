---
title: Retención de datos
description: Obtenga información sobre los valores de retención predeterminados para las tablas estándar
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# Retención de datos{#data-retention}

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
* **Exportar auditoría**: 6 meses (recomendado: 1 mes)

## Período de retención para envíos {#deliveries}

De forma predeterminada, el período de retención de envíos es ilimitado.

Sin embargo, si hay un gran volumen de envíos en su instancia, puede actualizar el **NmsCleanup_DeliveryPurgeDelay** opción disponible en el **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menú.

Cada vez que **[!UICONTROL Database cleanup]** Cuando se ejecute el flujo de trabajo, se eliminarán los envíos que cumplan las condiciones establecidas para esta opción.

Esta acción puede ayudar a acelerar procesos como el **[!UICONTROL Copy headers from delivery templates]** flujo de trabajo.

>[!NOTE]
>
>Obtenga más información sobre flujos de trabajo técnicos en [esta sección](technical-workflows.md).


El valor predeterminado para **NmsCleanup_DeliveryPurgeDelay** La opción es `-1`. En este caso, no se elimina ninguna entrega.

Por ejemplo, si lo establece en `180`, cualquier envío que no sea de plantilla y que no se haya actualizado en los últimos 180 días se eliminará cuando el **[!UICONTROL Database cleanup]** flujo de trabajo de se ejecuta.

>[!NOTE]
>
>* Las plantillas de marketing o de envío transaccional no se eliminarán.
>
>* En el caso de las entregas recurrentes, no se eliminan las entregas secundarias con un periodo de acumulación establecido como mes o año.

Al actualizar el **NmsCleanup_DeliveryPurgeDelay** , se recomienda continuar gradualmente con varias iteraciones. Por ejemplo, puede empezar estableciendo el valor en 300 días, luego en 180 días, luego en 120 días, etc., asegurándose de que las iteraciones se produzcan al menos con una diferencia de 2 días. De lo contrario, la variable **[!UICONTROL Database cleanup]** el flujo de trabajo puede tardar mucho más debido al gran número de envíos que se pueden eliminar.


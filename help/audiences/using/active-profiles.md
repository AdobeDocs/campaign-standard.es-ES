---
title: Perfiles activos
description: Puede acceder a un informe dedicado sobre las métricas del cliente y visualizar los perfiles activos en la base de datos de Campañas.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---


# Perfiles activos{#active-profiles}

Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación. Solo los administradores pueden acceder a este informe en **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Si está alojado en AWS y utiliza Campaign Standard de la compilación 10368, también puede supervisar el número de perfiles activos utilizados en las instancias directamente desde el Panel de control de Campaign. Para obtener más información, consulte la [documentación del Panel de control de Campaign](https://docs.adobe.com/content/help/es-ES/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Note that Active profiles metric is available and relevant for **Marketing instances** only. No es aplicable ni está disponible para Instancias de ejecución, es decir, instancias de MID (mid-sourcing) y RT (Message Center / mensajería en tiempo real).


No se tienen en cuenta los perfiles excluidos durante la preparación del envío (reglas de tipología, cuarentenas, grupos de control). Un perfil identificado por varios envíos solo se contará una vez. En la parte inferior del informe encontrará la lista de perfiles activos para cada dimensión de segmentación.

El flujo de trabajo **[!UICONTROL Billing]** técnico genera este informe todos los meses. Contiene el número de perfiles activos que fueron objetivo durante el último período móvil de 12 meses.

Tenga en cuenta que los perfiles que se excluyeron durante la preparación del envío (reglas de tipología, cuarentenas) no se tienen en cuenta. Además, un perfil que ha sido blanco de varios envíos solo se contará una vez.

![](assets/audience_active_profiles2.png)

En la parte inferior del informe, encontrará la lista de perfiles activos procesados por el flujo de trabajo de facturación:

* La **[!UICONTROL NmsRecipient]** fuente incluye a todos los clientes con los que se contactó mediante información del perfil de su Campaign Standard.

* Por otro lado, los clientes que fueron dirigidos a un objetivo usando sólo una porción específica de información (dirección de correo electrónico, número de teléfono), sin relación con su perfil de Campaña, estarán bajo la **[!UICONTROL anonymous]** fuente.

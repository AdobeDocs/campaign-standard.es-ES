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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Perfiles activos{#active-profiles}

Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación. Solo los administradores pueden acceder a este informe en **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

El flujo de trabajo **[!UICONTROL Billing]** técnico genera cada mes un informe que contiene el número de perfiles activos objetivo durante el último período móvil de 12 meses.

Los perfiles que se excluyen durante la preparación de la entrega (reglas de tipología, cuarentena) no se tienen en cuenta. Un perfil identificado por varios envíos solo se contará una vez. En la parte inferior del informe encontrará la lista de perfiles activos para cada dimensión de segmentación.

![](assets/audience_active_profiles2.png)

Si está alojado en AWS y utiliza Campaign Standard de la compilación 10368, también puede supervisar el número de perfiles activos utilizados en las instancias directamente desde el Panel de control. For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).

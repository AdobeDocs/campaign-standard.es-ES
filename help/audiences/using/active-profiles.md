---
solution: Campaign Standard
product: campaign
title: Perfiles activos
description: Puede acceder a un informe dedicado sobre las métricas de los clientes y visualizar los perfiles activos en la base de datos de Campaign.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 12%

---


# Perfiles activos{#active-profiles}

Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación. Solo los administradores pueden acceder a este informe en **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Si utiliza Campaign Standard de la compilación 10368, también puede supervisar el número de perfiles activos utilizados en las instancias directamente desde el Panel de control de Campaign. Para obtener más información, consulte la [documentación del Panel de control de Campaign](https://docs.adobe.com/content/help/es-ES/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Tenga en cuenta que la métrica de perfiles activos está disponible y es relevante solo para **instancias de marketing**. No es aplicable ni está disponible para instancias de ejecución, es decir, instancias de MID (intermediario) y RT (centro de mensajes/mensajería en tiempo real).

No se tienen en cuenta los perfiles que se excluyeron durante la preparación de la entrega (reglas de tipología, cuarentena o grupos de control). Un perfil identificado por varios envíos solo se contará una vez. En la parte inferior del informe, encontrará la lista de perfiles activos para cada dimensión de segmentación.

Este informe se genera cada mes mediante el flujo de trabajo técnico **[!UICONTROL Billing]** . Contiene el número de perfiles activos que fueron seleccionados durante el último periodo móvil de 12 meses.

Tenga en cuenta que los perfiles que se excluyeron durante la preparación de la entrega (reglas de tipología, cuarentena) no se tienen en cuenta. Además, un perfil identificado por varios envíos solo se cuenta una vez.

![](assets/audience_active_profiles2.png)

En la parte inferior del informe, encontrará la lista de perfiles activos procesados por el flujo de trabajo de facturación:

* La fuente **[!UICONTROL NmsRecipient]** incluye a todos los clientes a los que se contactó mediante información de su perfil de Campaign Standard.

* Por otro lado, los clientes a los que se ha dirigido la campaña utilizando solo un fragmento de información específico (dirección de correo electrónico, número de teléfono), sin relación con su perfil de Campaign, caerán en la **[!UICONTROL anonymous]** fuente.

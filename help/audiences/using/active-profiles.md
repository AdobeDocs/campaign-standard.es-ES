---
title: Perfiles activos de Campaign
description: Obtenga información sobre cómo acceder a las métricas del cliente y a los perfiles activos
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 12%

---

# Perfiles activos{#active-profiles}

Puede acceder a los detalles de perfiles activos desde la **[!UICONTROL Customer metrics]** informe. Este informe solo está disponible para los administradores funcionales de Campaign. Para acceder a este informe, haga clic en el icono Adobe Campaign en la parte superior izquierda del [interfaz de usuario](../../start/using/interface-description.md#advanced-menu)y busque **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Este informe se genera cada mes mediante la variable **[!UICONTROL Billing]** flujo de trabajo técnico y muestra el número de **perfiles activos**. Obtenga más información sobre los flujos de trabajo técnicos en [esta página](../../administration/using/technical-workflows.md).

Un &quot;perfil&quot; es un registro de información que representa a un cliente final, a un cliente potencial o a un posible cliente. Se consideran los perfiles **active** si ha sido un objetivo de una entrega de Campaign en los últimos 12 meses a través de cualquier canal.

Según el contrato, cada una de las instancias de Campaign se aprovisiona con un número específico de perfiles activos. Consulte el contrato de licencia para obtener referencia sobre el número de perfiles activos adquiridos.

![](assets/audience_active_profiles_list.png)



* Los perfiles que se excluyeron durante la preparación de la entrega (por reglas de tipología o mecanismo de cuarentena, por ejemplo) no se tienen en cuenta.

* Los destinatarios de Mensajes transaccionales se cuentan para Perfiles activos.

* Un perfil identificado por varios envíos solo se contará una vez.

* Este informe es solo informativo, no tiene un impacto directo en la facturación.

En la parte inferior de la página, las dimensiones de segmentación se enumeran con la cantidad de perfiles para cada una. Los destinatarios de los mensajes transaccionales están asociados al **Anonymous** dimensión.

>[!NOTE]
>
>Como usuario administrador, también puede supervisar el número de perfiles activos utilizados en las instancias directamente desde el Panel de control de Campaign. Para obtener más información, consulte la [Documentación del Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es).

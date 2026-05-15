---
title: Perfiles activos de Campaign
description: Obtenga información sobre cómo acceder a métricas de clientes y perfiles activos
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
TQID: https://experienceleague.adobe.com/XKRIP6jfP3ROPWTN4moJKsBLQcRqmR3gSWZ-hi5P8I4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 13%

---

# Perfiles activos{#active-profiles}

Puede acceder a los detalles de los perfiles activos desde el informe **[!UICONTROL Customer metrics]**. Este informe solo está disponible para los administradores funcionales de Campaign. Para obtener acceso a este informe, haga clic en el icono Adobe Campaign en la parte superior izquierda de la [interfaz de usuario](../../start/using/interface-description.md#advanced-menu) y desplácese hasta **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Este informe se genera cada mes mediante el flujo de trabajo técnico de **[!UICONTROL Billing]** y muestra la cantidad de **perfiles activos**. Obtenga más información acerca de los flujos de trabajo técnicos en [esta página](../../administration/using/technical-workflows.md).

Un &quot;perfil&quot; es un registro de información que representa a un cliente final, a un cliente potencial o a un posible cliente. Los perfiles se consideran **activos** si se han identificado con un envío de Campaign en los últimos 12 meses a través de cualquier canal.

Según el contrato, cada una de las instancias de Campaign se aprovisiona con una cantidad específica de perfiles activos. Consulte el acuerdo de licencia para obtener una referencia sobre la cantidad de perfiles activos adquiridos.

![](assets/audience_active_profiles_list.png)



* Los perfiles que se excluyeron durante la preparación del envío (por ejemplo, mediante reglas de tipología o mecanismo de cuarentena) no se tienen en cuenta.

* Los destinatarios de los mensajes transaccionales se cuentan hacia los perfiles activos.

* Un perfil identificado por varios envíos solo se contará una vez.

* Este informe es solo informativo, no tiene un impacto directo en la facturación.

En la parte inferior de la página, las dimensiones de segmentación se enumeran con el número de perfiles para cada una. Los destinatarios de los mensajes transaccionales están asociados a la dimensión **Anónimo**.

>[!NOTE]
>
>Como usuario administrador, también puede monitorizar el número de perfiles activos utilizados en las instancias directamente desde la Panel de control de Campaign. Para obtener más información, consulte la [documentación del Panel de control](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es).
>

---
solution: Campaign Standard
product: campaign
title: Perfiles activos de Campaign
description: Obtenga información sobre cómo acceder a las métricas del cliente y a los perfiles activos
feature: Perfiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 14%

---

# Perfiles activos{#active-profiles}

Los administradores funcionales de Campaign pueden acceder al informe **[!UICONTROL Customer metrics]** desde **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Este informe se genera cada mes mediante el flujo de trabajo técnico **[!UICONTROL Billing]** y muestra el número de **perfiles activos**.

Un &quot;perfil&quot; es un registro de información que representa a un cliente final, a un cliente potencial o a un posible cliente. Los perfiles se consideran **activos** si han sido objetivos de un envío de Campaign en los últimos 12 meses a través de cualquier canal.

Según el contrato, cada una de las instancias de Campaign se aprovisiona con un número específico de perfiles activos. Consulte el contrato de licencia para obtener referencia sobre el número de perfiles activos adquiridos.

![](assets/audience_active_profiles_list.png)



* Los perfiles que se excluyeron durante la preparación de la entrega (por reglas de tipología o mecanismo de cuarentena, por ejemplo) no se tienen en cuenta.

* Los destinatarios de Mensajes transaccionales se cuentan para Perfiles activos.

* Un perfil identificado por varios envíos solo se contará una vez.

* Este informe es solo informativo, no tiene un impacto directo en la facturación.

En la parte inferior de la página, las dimensiones de segmentación se enumeran con la cantidad de perfiles para cada una. Los destinatarios de los mensajes transaccionales están asociados a la dimensión **Anonymous**.

>[!NOTE]
>
>Como usuario administrador, también puede supervisar el número de perfiles activos utilizados en las instancias directamente desde el Panel de control de Campaign. Para obtener más información, consulte la [Documentación del Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es).


---
solution: Campaign Standard
product: campaign
title: Acerca de la inclusión y la exclusión en Campaign
description: La exclusión da como resultado que un perfil ya no sea objetivo de ningún envío ni de envíos de un canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Acerca de la inclusión y la exclusión en Campaign{#about-opt-in-and-opt-out-in-campaign}

La exclusión da como resultado que un perfil ya no sea objetivo de ningún envío ni de envíos de un canal específico.

Para dar a los perfiles la capacidad de adhesión o exclusión, debe crear una página de aterrizaje dedicada. Para obtener más información sobre esto, consulte [Configuración de páginas de aterrizaje de inclusión y exclusión](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Un operador también puede adhesión o excluir perfiles manualmente. Para obtener más información sobre esto, consulte [Administración de la inclusión y la exclusión desde un perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante la análisis del envío para acelerar los envíos (la tasa de error tiene un efecto significativo en la velocidad del envío).

>[!NOTE]
>
>La exclusión se aplica a **Perfiles**, a diferencia de la cuarentena que está vinculada a una **dirección de correo electrónico** o **número de teléfono**. Exclusión un perfil excluirá de los envíos todas las direcciones vinculadas a él. Si un usuario tiene dos perfiles en la base de datos, seguirá siendo objetivo de envíos, ya que sólo uno de sus perfiles es la exclusión. Para asegurarse de que todas sus direcciones están excluidas, agréguelas a las direcciones de cuarentenas. Para obtener más información, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obtener más información sobre suscripciones de servicios, consulte [esta página](../../audiences/using/about-subscriptions.md).

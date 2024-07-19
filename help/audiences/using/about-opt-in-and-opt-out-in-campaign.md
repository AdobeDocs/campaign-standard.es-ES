---
title: Acerca de la inclusión y la exclusión en Campaign
description: La exclusión hace que un perfil ya no se tenga en cuenta para ninguna entrega ni para las entregas de un canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# Acerca de la inclusión y la exclusión en Campaign{#about-opt-in-and-opt-out-in-campaign}

La exclusión hace que un perfil ya no se tenga en cuenta para ninguna entrega ni para las entregas de un canal específico.

Para permitir que los perfiles puedan incluirse o excluirse, debe crear una página de aterrizaje dedicada. Para obtener más información, consulte [Configuración de páginas de aterrizaje de inclusión y exclusión](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Un operador también puede activar o desactivar los perfiles manualmente. Para obtener más información, consulte [Administración de la inclusión y la exclusión de un perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante el análisis de la entrega para acelerar los envíos (la tasa de error tiene un efecto significativo en la velocidad de entrega).

>[!NOTE]
>
>La exclusión se aplica a **Perfiles**, a diferencia de la cuarentena vinculada a una **dirección de correo electrónico** o a **número de teléfono**. Por lo tanto, al excluir un perfil, se excluyen de las entregas todas las direcciones vinculadas a él. Sin embargo, si un usuario tiene dos perfiles en la base de datos, los envíos seguirán teniendo como objetivo a este usuario, ya que solo se excluye uno de sus perfiles. Para asegurarse de que se excluyen todas sus direcciones, agréguelas a las direcciones en cuarentena. Para obtener más información, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obtener más información sobre suscripciones a servicios, consulte [esta página](../../audiences/using/about-subscriptions.md).

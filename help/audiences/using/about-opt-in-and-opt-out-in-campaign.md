---
title: Acerca de la inclusión y la exclusión en Campaign
description: La exclusión hace que un perfil ya no se tenga en cuenta para los envíos ni para los envíos de un canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Acerca de la inclusión y la exclusión en Campaign{#about-opt-in-and-opt-out-in-campaign}

La exclusión hace que un perfil ya no se tenga en cuenta para los envíos ni para los envíos de un canal específico.

Para que los perfiles puedan entrar o salir, debe crear una página de aterrizaje dedicada. Para obtener más información, consulte [Configuración de páginas de aterrizaje de inclusión y exclusión](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Un operador también puede activar o desactivar manualmente los perfiles. Para obtener más información, consulte [Administración de la inclusión y la exclusión desde un perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante el análisis de envío para acelerar los envíos (la tasa de error afecta significativamente a la velocidad de envío).

>[!NOTE]
>
>La exclusión se aplica a **Profiles**, a diferencia de la cuarentena que está vinculada a una **dirección de correo electrónico** o a4/>número de teléfono **.** Por lo tanto, la exclusión de un perfil excluye de las entregas todas las direcciones vinculadas a él. Sin embargo, si un usuario tiene dos perfiles en la base de datos, seguirá siendo objetivo de los envíos, ya que solo se ha excluido uno de sus perfiles. Para asegurarse de que todas sus direcciones están excluidas, agréguelas a las direcciones en cuarentena. Para obtener más información, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obtener más información sobre las suscripciones a servicios, consulte [esta página](../../audiences/using/about-subscriptions.md).

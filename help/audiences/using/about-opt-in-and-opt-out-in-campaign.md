---
title: Acerca de la inclusión y la exclusión en Campaign
description: La exclusión da como resultado que un perfil ya no sea objetivo de ningún envío ni de envíos de un canal específico.
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Acerca de la inclusión y la exclusión en Campaign{#about-opt-in-and-opt-out-in-campaign}

La exclusión da como resultado que un perfil ya no sea objetivo de ningún envío ni de envíos de un canal específico.

Para dar a los perfiles la capacidad de adhesión o exclusión, debe crear una página de aterrizaje dedicada. Para obtener más información sobre esto, consulte [Configuración de páginas de aterrizaje](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)de inclusión y exclusión.

Un operador también puede adhesión o excluir Perfiles manualmente. Para obtener más información sobre este tema, consulte [Administración de la opción de inclusión y exclusión de un perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante la análisis del envío para acelerar los envíos (la tasa de error tiene un efecto significativo en la velocidad del envío).

>[!NOTE]
>
>La exclusión se aplica a **Perfiles**, en oposición a la cuarentena que está vinculada a una dirección **de** correo electrónico o a un número **de** teléfono. Exclusión un perfil excluirá de los envíos todas las direcciones vinculadas a él. Si un usuario tiene dos perfiles en la base de datos, seguirá siendo objetivo de envíos, ya que sólo uno de sus perfiles es la exclusión. Para asegurarse de que todas sus direcciones están excluidas, agréguelas a las direcciones de cuarentenas. Para obtener más información, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).

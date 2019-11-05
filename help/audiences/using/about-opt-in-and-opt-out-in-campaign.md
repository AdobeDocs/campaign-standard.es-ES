---
title: Acerca de la inclusión y la exclusión en Campaign
description: La exclusión (o lista negra) hace que un perfil ya no esté segmentado por ninguna entrega o por entregas desde un canal específico.
page-status-flag: nunca activado
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: Understanding-opt-in-and-opt-out-process
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de la inclusión y la exclusión en Campaign{#about-opt-in-and-opt-out-in-campaign}

La exclusión (o lista negra) hace que un perfil ya no esté segmentado por ninguna entrega o por entregas desde un canal específico.

Para ofrecer a los perfiles la capacidad de activar o desactivar, debe crear una página de aterrizaje dedicada. Para obtener más información sobre esto, consulte [Configuración de páginas](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)de aterrizaje de inclusión y exclusión.

Un operador también puede seleccionar perfiles de entrada o salida manualmente. Para obtener más información sobre este tema, consulte [Administración de la opción de inclusión y exclusión de un perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante el análisis de entrega para acelerar los envíos (la tasa de error tiene un efecto significativo en la velocidad de entrega).

>[!NOTE]
>
>La exclusión se aplica a **perfiles**, en lugar de a cuarentena que está vinculada a una dirección **de** correo electrónico o a un número **de** teléfono. Por lo tanto, la exclusión de un perfil excluirá de las entregas todas las direcciones vinculadas a él. Si un usuario tiene dos perfiles en la base de datos, seguirá siendo el objetivo de entregas, ya que solo uno de sus perfiles es la exclusión. Para asegurarse de que todas sus direcciones están excluidas, agréguelas a las direcciones de cuarentena. Para obtener más información, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).

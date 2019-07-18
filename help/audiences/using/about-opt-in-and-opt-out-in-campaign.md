---
title: Acerca de la inclusión y la exclusión en Campaign
seo-title: Acerca de la inclusión y la exclusión en Campaign
description: Acerca de la inclusión y la exclusión en Campaign
seo-description: La opción de exclusión (o lista negra) resulta en que un perfil ya no se dirija a ninguna entrega o por entregas desde un canal específico.
page-status-flag: no activado nunca
uuid: 501 d 9485-976 b -4 de 7-b 242-6886 f 2814 c 6 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: comprender y excluir procesos
discoiquuid: 2 f 26 ec 22-0809-4541-b 2 a 1-e 84 ff 868 ba 6 e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

La opción de exclusión (o lista negra) resulta en que un perfil ya no se dirija a ninguna entrega o por entregas desde un canal específico.

Para dar a los perfiles la capacidad de activar o desactivar, debe crear una página de aterrizaje dedicada. For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Un operador también puede activar o alejar los perfiles manualmente. For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Los perfiles de exclusión se excluyen automáticamente durante el análisis de entrega para acelerar los envíos (el índice de errores tiene un efecto significativo en la velocidad de entrega).

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. Si se elige excluir un perfil, se excluirá de las entregas todas las direcciones vinculadas a ella. Si un usuario tiene dos perfiles en la base de datos, seguirá siendo dirigido por entregas porque sólo uno de sus perfiles es desactivado. Para asegurarse de que todas las adresses están excluidas, agréguelas a las direcciones de cuarentena. For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).

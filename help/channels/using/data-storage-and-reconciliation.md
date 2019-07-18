---
title: Almacenamiento y almacenamiento de datos
seo-title: Almacenamiento y almacenamiento de datos
description: Almacenamiento y almacenamiento de datos
seo-description: Adobe Campaign permite definir cómo se administran los datos introducidos en la página de aterrizaje una vez enviados por un usuario.
page-status-flag: no activado nunca
uuid: 5 b 222 ea 2-6628-457 f-a 618-bfc 0 e 5 eb 93 dd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: landing-pages
discoiquuid: 899 c 7152-f 415-4 df 9-b 4 b 4-5 ff 3470 a 4 e 32
context-tags: Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Data storage and reconciliation{#data-storage-and-reconciliation}

Los parámetros de reconciliación de datos permiten definir cómo se administran los datos introducidos en la página de aterrizaje después de que los haya enviado un usuario.

Para ello:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. Esto le permite actualizar o crear un perfil según los parámetros de estrategia de actualización definidos.
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.


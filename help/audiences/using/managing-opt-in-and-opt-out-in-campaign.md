---
title: Administración de opciones de inclusión y exclusión en Campaign
seo-title: Administración de opciones de inclusión y exclusión en Campaign
description: Administración de opciones de inclusión y exclusión en Campaign
seo-description: Comprender cómo se administran las opciones de inclusión y exclusión en Adobe Campaign.
page-status-flag: no activado nunca
uuid: aa 1801 ec -562 b -420 e -8 d 79-c 07 d 066 b 7 b 1 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: comprender y excluir procesos
discoiquuid: 6 b 5680 f 2-bba 9-453 e-a 0 d 5-8 ca 69 dd 02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Managing opt-in and opt-out in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Managing opt-in and opt-out from a profile {#managing-opt-in-and-opt-out-from-a-profile}

Users can be opted in or out by an operator directly from the profile **[!UICONTROL General]** tab.

In the **[!UICONTROL No longer contact (blacklist)]** section, the selected checkboxes correspond to the channels from which the user chose to opt out. Seleccione los canales según las necesidades del usuario.

![](assets/optin_landingpage_3.png)

## Setting up opt-in and opt-out landing pages {#setting-up-opt-in-and-opt-out-landing-pages}

To give users the ability to opt in or opt out, you have to create and publish a **[!UICONTROL Profile acquisition]** landing page. Luego podrán seleccionar los canales según sus necesidades. Para ello, siga los pasos a continuación.

You can also set up a **[!UICONTROL BlackList]** landing page that will enable users to opt out from all deliveries. For more on this, refer to [Setting up a landing page to opt out from all deliveries](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Las páginas de aterrizaje también se pueden utilizar para habilitar la suscripción de servicios. For more on this, refer to [this page](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. Create a **[!UICONTROL Profile acquisition]** landing page (see [this section](../../channels/using/about-landing-pages.md)).
1. Agregue una casilla en el contenido de la página de aterrizaje para cada canal deseado y, a continuación, vincule el campo al campo correspondiente de la base de datos de campaña.

   ![](assets/optin_landingpage_1.png)

1. Guarde la página de aterrizaje y publíquela.
1. In the landing page, the checkboxes are already selected according to the profile **[!UICONTROL General]** tab. El usuario puede seleccionar o anular la selección de los canales según sus necesidades y enviar el formulario.

   ![](assets/optin_landingpage_2.png)

1. Once the form submitted, the profile **[!UICONTROL General]** tab is updated according to the user's selection.

   ![](assets/optin_landingpage_3.png)

### Setting up a landing page to opt out from all deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

To give users the ability to opt out from all deliveries, you have to create and publish a **[!UICONTROL BlackList]** landing page. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Once a user clicks on the landing page link, the **[!UICONTROL No longer contact (by any channel)]** option in the profile is automatically selected.

![](assets/blacklisting_allchannels.png)


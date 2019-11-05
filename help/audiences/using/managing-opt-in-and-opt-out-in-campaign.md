---
title: Administración de la inclusión y la exclusión en Campaign
description: Comprenda cómo se administran las opciones de inclusión y exclusión en Adobe Campaign.
page-status-flag: nunca activado
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: Understanding-opt-in-and-opt-out-process
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Administración de la inclusión y la exclusión en Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Administración de la inclusión y la exclusión de un perfil {#managing-opt-in-and-opt-out-from-a-profile}

Los usuarios pueden ser seleccionados por un operador directamente desde la ficha de perfil **[!UICONTROL General]** .

En la **[!UICONTROL No longer contact (blacklist)]** sección, las casillas de verificación seleccionadas corresponden a los canales de los que el usuario eligió desactivar la opción. Seleccione los canales según las necesidades del usuario.

![](assets/optin_landingpage_3.png)

## Configuración de páginas de aterrizaje de inclusión y exclusión {#setting-up-opt-in-and-opt-out-landing-pages}

Para que los usuarios puedan optar por la activación o la desactivación, debe crear y publicar una página **[!UICONTROL Profile acquisition]** de aterrizaje. Luego podrán seleccionar los canales según sus necesidades. Para realizar esto, siga los pasos a continuación.

También puede configurar una **[!UICONTROL BlackList]** página de aterrizaje que permita a los usuarios desactivar todas las entregas. Para obtener más información sobre esto, consulte [Configuración de una página de aterrizaje para desactivar todas las entregas](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Las páginas de aterrizaje también se pueden utilizar para habilitar la suscripción a servicios. Para obtener más información, consulte [esta página](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. Cree una **[!UICONTROL Profile acquisition]** página de aterrizaje (consulte [esta sección](../../channels/using/about-landing-pages.md)).
1. Agregue una casilla de verificación en el contenido de la página de aterrizaje para cada canal deseado y, a continuación, vincúlelo al campo correspondiente de la base de datos de Campaign.

   ![](assets/optin_landingpage_1.png)

1. Guarde la página de aterrizaje y publíquela.
1. En la página de aterrizaje, las casillas de verificación ya están seleccionadas según la ficha de perfil **[!UICONTROL General]** . El usuario puede seleccionar o anular la selección de los canales según sus necesidades y enviar el formulario.

   ![](assets/optin_landingpage_2.png)

1. Una vez enviado el formulario, la ficha de perfil **[!UICONTROL General]** se actualiza según la selección del usuario.

   ![](assets/optin_landingpage_3.png)

### Configuración de una página de aterrizaje para desactivar todas las entregas {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para que los usuarios puedan desactivar todas las entregas, debe crear y publicar una página **[!UICONTROL BlackList]** de aterrizaje. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Una vez que un usuario hace clic en el vínculo de la página de aterrizaje, la **[!UICONTROL No longer contact (by any channel)]** opción del perfil se selecciona automáticamente.

![](assets/blacklisting_allchannels.png)


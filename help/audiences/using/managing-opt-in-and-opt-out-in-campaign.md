---
solution: Campaign Standard
product: campaign
title: Administración de la inclusión y la exclusión en Campaign
description: Comprenda cómo se administran las opciones de inclusión y exclusión en Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Administración de la inclusión y la exclusión en Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Administración de la inclusión y la exclusión desde un perfil {#managing-opt-in-and-opt-out-from-a-profile}

Un operador puede adhesión o excluir usuarios directamente desde la ficha perfil **[!UICONTROL General]**.

En la sección **[!UICONTROL No longer contact (on denylist)]**, las casillas de verificación seleccionadas corresponden a los canales desde los que el usuario eligió exclusión. Seleccione los canales según las necesidades del usuario.

![](assets/optin_landingpage_3.png)

## Configuración de las páginas de aterrizaje de inclusión y exclusión {#setting-up-opt-in-and-opt-out-landing-pages}

Para que los usuarios puedan adhesión o exclusión, debe crear y publicar una página de aterrizaje **[!UICONTROL Profile acquisition]**. Entonces podrán seleccionar los canales según sus necesidades. Para realizar esto, siga los pasos a continuación.

También puede configurar una página de aterrizaje **[!UICONTROL Denylist]** que permita a los usuarios exclusión desde todos los envíos. Para obtener más información sobre esto, consulte [Configuración de una página de aterrizaje para exclusión de todos los envíos](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>También se pueden utilizar páginas de aterrizaje para habilitar la suscripción de servicios. Para obtener más información, consulte [esta página](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Cree una página de aterrizaje **[!UICONTROL Profile acquisition]** (consulte [esta sección](../../channels/using/getting-started-with-landing-pages.md)).
1. Añada una casilla de verificación en el contenido de la página de aterrizaje para cada canal deseado y, a continuación, vincúlelo al campo correspondiente de la base de datos de Campañas.

   ![](assets/optin_landingpage_1.png)

1. Guarde la página de aterrizaje y publíquela.
1. En la página de aterrizaje, las casillas de verificación ya están seleccionadas según la ficha perfil **[!UICONTROL General]**. El usuario puede seleccionar o anular la selección de los canales según sus necesidades y enviar el formulario.

   ![](assets/optin_landingpage_2.png)

1. Una vez enviado el formulario, la ficha perfil **[!UICONTROL General]** se actualiza según la selección del usuario.

   ![](assets/optin_landingpage_3.png)

### Configuración de una página de aterrizaje para exclusión de todos los envíos {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para que los usuarios puedan exclusión desde todos los envíos, debe crear y publicar una página de aterrizaje **[!UICONTROL Denylist]**. Para obtener más información sobre la creación de páginas de aterrizaje, consulte [esta página](../../channels/using/getting-started-with-landing-pages.md).

Una vez que un usuario hace clic en el vínculo de página de aterrizaje, la opción **[!UICONTROL No longer contact (by any channel)]** del perfil se selecciona automáticamente.

![](assets/blocklisting_allchannels.png)


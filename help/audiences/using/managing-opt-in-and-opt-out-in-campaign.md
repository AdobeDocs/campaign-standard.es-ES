---
title: Administración de la inclusión y la exclusión en Campaign
description: Comprenda cómo se administran la inclusión y la exclusión en Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# Administración de la inclusión y la exclusión en Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Administración de la inclusión y la exclusión desde un perfil {#managing-opt-in-and-opt-out-from-a-profile}

Un operador puede activar o desactivar los usuarios directamente desde la pestaña perfil **[!UICONTROL General]**.

En la sección **[!UICONTROL No longer contact (on denylist)]** , las casillas de verificación seleccionadas corresponden a los canales desde los que el usuario optó por la exclusión. Seleccione los canales según las necesidades del usuario.

![](assets/optin_landingpage_3.png)

## Configuración de páginas de aterrizaje de inclusión y exclusión {#setting-up-opt-in-and-opt-out-landing-pages}

Para que los usuarios puedan entrar o salir, debe crear y publicar una página de aterrizaje **[!UICONTROL Profile acquisition]**. Luego podrán seleccionar los canales según sus necesidades. Para realizar esto, siga los pasos a continuación.

También puede configurar una página de aterrizaje **[!UICONTROL Denylist]** que permita a los usuarios desactivar todas las entregas. Para obtener más información, consulte [Configuración de una página de aterrizaje para la exclusión de todos los envíos](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Las páginas de aterrizaje también se pueden utilizar para habilitar la suscripción de servicios. Para obtener más información, consulte [esta página](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Cree una **[!UICONTROL Profile acquisition]** página de aterrizaje (consulte [esta sección](../../channels/using/getting-started-with-landing-pages.md)).
1. Agregue una casilla en el contenido de la página de aterrizaje para cada canal deseado y luego vincúlelo al campo correspondiente de la base de datos de Campaign.

   ![](assets/optin_landingpage_1.png)

1. Guarde la página de aterrizaje y publíquela.
1. En la página de aterrizaje, las casillas de verificación ya están seleccionadas según la pestaña del perfil **[!UICONTROL General]**. El usuario puede seleccionar o desseleccionar los canales según sus necesidades y enviar el formulario.

   ![](assets/optin_landingpage_2.png)

1. Una vez enviado el formulario, la pestaña del perfil **[!UICONTROL General]** se actualiza según la selección del usuario.

   ![](assets/optin_landingpage_3.png)

### Configuración de una página de aterrizaje para la exclusión de todas las entregas {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para que los usuarios puedan desactivar todas las entregas, debe crear y publicar una página de aterrizaje **[!UICONTROL Denylist]**. Para obtener más información sobre la creación de páginas de aterrizaje, consulte [esta página](../../channels/using/getting-started-with-landing-pages.md).

Una vez que un usuario hace clic en el vínculo de la página de aterrizaje, la opción **[!UICONTROL No longer contact (by any channel)]** del perfil se selecciona automáticamente.

![](assets/blocklisting_allchannels.png)

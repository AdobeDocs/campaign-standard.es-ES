---
title: Acerca de las páginas de aterrizaje
seo-title: Acerca de las páginas de aterrizaje
description: Acerca de las páginas de aterrizaje
seo-description: Páginas de aterrizaje de Discover Campaign y su ciclo de vida.
page-status-flag: nunca activado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,asistente;landingPage,información general;landingPage,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Acerca de las páginas de aterrizaje{#about-landing-pages}

Campaign viene con páginas de aterrizaje que son formularios web que se pueden utilizar para capturar información sobre las audiencias, ofrecer suscripciones a un servicio, mostrar datos y ampliar la base de datos. Las páginas de aterrizaje también se pueden utilizar para adquirir o actualizar perfiles existentes.

>[!CAUTION]
>
>Las páginas de aterrizaje solo se pueden utilizar para actualizar perfiles.

Campaign viene con un conjunto de plantillas de página de aterrizaje integradas:

* **[!UICONTROL Acquisition]**:: esta es la plantilla predeterminada para las páginas de aterrizaje, que permite capturar y actualizar datos en la base de datos de Campaign.
* **[!UICONTROL Subscription]**:: esta plantilla debe utilizarse para ofrecer suscripciones a un servicio.
* **[!UICONTROL Unsubscription]**:: esta plantilla se puede vincular desde un correo electrónico enviado a los suscriptores de un servicio para permitirles cancelar la suscripción a este servicio.
* **[!UICONTROL Blacklist]**:: esta plantilla debe utilizarse cuando Campaign ya no desee establecer contacto con un perfil. Para obtener más información sobre la lista negra, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Estas plantillas se proponen de forma predeterminada al crear una nueva página de aterrizaje.

![](assets/lp_creation_1.png)

Adobe recomienda crear sus propias plantillas duplicando una plantilla integrada. Algunos parámetros solo se pueden configurar en plantillas de página de aterrizaje y no se pueden modificar directamente en las páginas de aterrizaje.

>[!NOTE]
>
>Para acceder a las plantillas de página de aterrizaje, haga clic en el logotipo de Adobe Campaign en la esquina superior izquierda y seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**.

El ciclo de vida completo de una página de aterrizaje es el siguiente:

1. Creación: diseñe y establezca el contenido de la página de aterrizaje.
1. Prueba: simular la ejecución de la página de aterrizaje en un perfil de prueba.
1. Publicación: publique la página de aterrizaje para insertarla en directo.
1. Caducidad o depublicación: cancele la publicación manualmente o espere a que la página de aterrizaje caduque y ya no estará disponible.

![](assets/lp_livecycle.png)

Una vez creada y publicada, puede hacer que la página de aterrizaje sea accesible a través de un sitio web o [insertando un vínculo directo a la página de aterrizaje en un correo electrónico](../../designing/using/links.md#inserting-a-link).

**Temas relacionados:**

* [Creación de un vídeo de página](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) de aterrizaje
* [Utilice una página de aterrizaje para suscribirse a un servicio](../../audiences/using/creating-a-service.md)
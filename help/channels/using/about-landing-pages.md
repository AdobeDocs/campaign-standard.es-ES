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
source-git-commit: 0068746b0b90b85edfb2c93eb08a82e1adc2fca8

---


# Acerca de las páginas de aterrizaje{#about-landing-pages}

Campaign viene con páginas de aterrizaje que son formularios web que se pueden utilizar para capturar información sobre las audiencias, ofrecer suscripciones a un servicio, mostrar datos y ampliar la base de datos. Las páginas de aterrizaje también se pueden utilizar para adquirir o actualizar perfiles existentes.

Para obtener más información sobre los pasos necesarios para configurar una página de aterrizaje, consulte [esta sección](../../channels/using/main-steps-to-set-up-a-landing-page.md)

**Temas relacionados:**

* [Creación de un vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) de tutorial de página de aterrizaje
* [Uso de una página de aterrizaje para suscribir un servicio](../../audiences/using/creating-a-service.md)

## Ciclo de vida de las páginas de aterrizaje {#landing-pages-life-cycle}

El ciclo de vida completo de una página de aterrizaje es el siguiente:

1. Creación: diseñe y establezca el contenido de la página de aterrizaje.
1. Prueba: simular la ejecución de la página de aterrizaje en un perfil de prueba.
1. Publicación: publique la página de aterrizaje para insertarla en directo.
1. Caducidad o depublicación: cancele la publicación manualmente o espere a que la página de aterrizaje caduque y ya no estará disponible.

![](assets/lp_livecycle.png)

Una vez creada y publicada, puede hacer que la página de aterrizaje sea accesible a través de un sitio web o [insertando un vínculo directo a la página de aterrizaje en un correo electrónico](../../designing/using/links.md#inserting-a-link).

## Limitaciones de la página de aterrizaje{#landing-page-limitations}

La sección siguiente enumera las limitaciones que debe tener en cuenta antes de comenzar a configurar las páginas de aterrizaje.

**Escritura y actualización de datos**

* Las páginas de aterrizaje están limitadas a **[!UICONTROL Profile]** y solo a **[!UICONTROL Subscription]** recursos. El registro se puede guardar y actualizar desde **[!UICONTROL Profile]** y una suscripción o cancelación de suscripción a un **[!UICONTROL Service]**.
Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura](../../developing/using/configuring-the-resource-s-data-structure.md)de datos del recurso.

>[!CAUTION]
>
>Una página de aterrizaje no puede mostrar ni actualizar datos de ningún otro recurso que no sea **[!UICONTROL Profile]** y **[!UICONTROL Subscription]**.

**Precarga**

* La página de aterrizaje no puede mostrar una lista de registros automáticamente, no puede enumerar los servicios a los que los perfiles ya están suscritos. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* Sólo se puede acceder a la página de aterrizaje con un formulario prerellenado (los datos se cargan previamente con la página) desde un correo electrónico de Adobe Campaign. No es posible acceder a este formulario desde una página web.

**Reconciliación**

* El comportamiento de reconciliación es el siguiente: tan pronto como se encuentra una coincidencia, el proceso de reconciliación se detiene. Esto significa que la reconciliación sólo se puede realizar en un registro de perfil y no en varios registros cuando hay duplicados.

Por ejemplo, si desea enviar la siguiente página de inicio de adquisición a sus perfiles para actualizar la base de datos de Campaign con los números móviles de sus perfiles.

![](assets/landing_page_limitation_1.png)

Si uno de los perfiles rellena la página de aterrizaje con información nueva pero ya tiene un perfil duplicado, el perfil coincidente con la fecha de creación más temprana se actualizará, ya que los perfiles se priorizan según la fecha de creación.

Aquí solo se actualizó el primer perfil porque era la entrada más antigua.

![](assets/landing_page_limitation_2.png)

**Prueba de las páginas de aterrizaje**

* Las páginas de aterrizaje solo funcionan en perfiles y no en perfiles de prueba, lo que significa que las páginas de aterrizaje no se pueden probar como parte de una prueba de correo electrónico.

---
title: Limitaciones de la página de aterrizaje
seo-title: Limitaciones de la página de aterrizaje
description: Limitaciones de la página de aterrizaje
seo-description: Páginas de aterrizaje de la campaña de Discover y su ciclo de vida.
page-status-flag: no activado nunca
uuid: b 316 bf 47-7 d 98-46 fa-ab 4 f -67 ff 50 de 8095
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: landing-pages
discoiquuid: ca 8 d 1698-6 e 8 a -4 f 5 a-b 017-74 a 152 e 14286
context-tags: Landingpage, wizard; Landingpage, overview; Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5dbb89eca363f252d0c69126878d4f79320e0f19

---


# Landing page limitations{#landing-page-limitations}

**Escritura y actualización de datos**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**Precarga**

* La página de aterrizaje no puede mostrar una lista de registros automáticamente, no puede enumerar los servicios a los que ya se han suscrito los perfiles. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* Solo se puede acceder a la página de aterrizaje con un formulario cumplimentado previamente (los datos se cargan previamente con la página) desde un correo electrónico de Adobe Campaign. No es posible acceder a este formulario desde una página de sitio Web.

**Reconciliación**

* El comportamiento de reconciliación es el siguiente: en cuanto se encuentra una coincidencia, el proceso de reconciliación se detiene. Esto significa que la reconciliación solo se puede realizar en un registro de perfil y no en varios registros cuando hay duplicados.

Por ejemplo, desea enviar la siguiente página de aterrizaje de adquisición a los perfiles para actualizar la base de datos de campaña con los números móviles de los perfiles.

![](assets/landing_page_limitation_1.png)

Si uno de los perfiles completa la página de aterrizaje con información nueva pero ya tiene un perfil duplicado, se actualizará el perfil coincidente con la fecha de creación más temprana, ya que los perfiles se priorizan según la fecha de creación únicamente.

Aquí solo se actualizó el primer perfil porque fue la entrada más antigua.

![](assets/landing_page_limitation_2.png)

**Prueba de página de aterrizaje**

* Las páginas de aterrizaje solo funcionan en perfiles y no en perfiles de prueba, lo que significa que las páginas de aterrizaje no se pueden probar como parte de una prueba por correo electrónico.

---
title: Uso compartido de una página de aterrizaje
seo-title: Uso compartido de una página de aterrizaje
description: Uso compartido de una página de aterrizaje
seo-description: Descubra cómo probar y publicar una página de aterrizaje en Adobe Campaign.
page-status-flag: no activado nunca
uuid: fb 7 b 087 a -3292-496 c-bc 41-2 e 3012 bacf 59
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: landing-pages
discoiquuid: f 7 d 4 bb 71-f 957-4 f 86-97 c 7-8 ac 0 a 0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

Antes de publicar una página de aterrizaje, debe realizar pruebas: valide la ejecución, configure el acceso y configure el final de su página de aterrizaje. Estos pasos son requisitos previos y deben ejecutarse con precaución.

## Testing the landing page {#testing-the-landing-page-}

Como la página de aterrizaje afectará a la plataforma y a los datos, debe probar cuidadosamente su ejecución. Para ello:

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. En la pantalla de prueba, seleccione un perfil de prueba y un servicio de prueba si la página de aterrizaje va a gestionar suscripciones.

   ![](assets/lp_test_2.png)

1. Introduzca los datos en los campos y seleccione las opciones.
1. Envíe la página de aterrizaje y compruebe las actualizaciones en la base de datos.

   >[!CAUTION]
   >
   >Cuando se envía el formulario, se actualiza el servicio y el perfil utilizados.

1. Repita este proceso con varios perfiles y datos.

   También puede generar la miniatura de la página de aterrizaje desde esta pantalla.

## Setting up validity parameters {#setting-up-validity-parameters}

Antes de publicar, por razones de seguridad y rendimiento de plataforma, le recomendamos encarecidamente que establezca una fecha de caducidad en las propiedades de página de aterrizaje. En la fecha seleccionada, la página de aterrizaje se cancelará automáticamente. Para ello:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. Set up expiration date and time in the **[!UICONTROL Publication]** section: the landing page will automatically be unpublished on the specified date and therefore no longer be available.

   Puede seleccionar la zona horaria que se debe tener en cuenta para esta fecha y hora.

1. Definir una dirección URL de redirección para redirigir a los visitantes al intentar acceder a una página de aterrizaje no activa.

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>También puede definir una fecha y una hora de implementación: la página de aterrizaje se publicará automáticamente en la fecha especificada.

## Publishing a landing page {#publishing-a-landing-page}

Cuando publica una página de aterrizaje, ésta se activa y los visitantes pueden acceder a ella.

You can unpublish or update and republish your landing page at any time, via the **[!UICONTROL Publish]** button. Sin embargo, si falla la publicación y todavía no ha cancelado la publicación de la página de aterrizaje, la primera versión permanecerá en línea.

---
title: Uso compartido de una página de aterrizaje
description: Obtenga información sobre cómo probar y publicar una página de aterrizaje en Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa92475c1f8b37f995ebdc74c4a1f43692a53c21

---


# Prueba y publicación de una página de aterrizaje{#testing-publishing--landing-page}

## Acerca de la publicación de la página de aterrizaje {#about-landing-page-publication}

Antes de publicar una página de aterrizaje, debe realizar pruebas: valide la ejecución, configure el acceso y configure el final de la vida útil de la página de aterrizaje. Estos pasos son requisitos previos y deben ejecutarse con precaución.

## Prueba de la página de aterrizaje {#testing-the-landing-page-}

Dado que la página de aterrizaje afectará a la plataforma y a los datos, debe probar cuidadosamente su ejecución. Para ello:

1. Haga clic en el **[!UICONTROL Test]**botón de la barra de acciones de la página de aterrizaje.
1. En la pantalla de prueba, seleccione un perfil de prueba y un servicio de prueba para administrar las suscripciones en la página de aterrizaje.

   ![](assets/lp_test_2.png)

1. Introduzca datos en los campos y seleccione opciones.
1. Envíe la página de aterrizaje y compruebe las actualizaciones en la base de datos.

   >[!IMPORTANT]
   >
   >Cuando se envía el formulario, se actualizan el servicio y el perfil utilizados.

1. Repita esto con varios perfiles y datos.

   También puede generar la miniatura de la página de aterrizaje desde esta pantalla.

>[!NOTE]
>
>Si la dirección URL del servidor de aplicaciones no es segura (es decir, si no comienza con https://), la vista previa de la página de aterrizaje no se puede mostrar desde la interfaz de usuario de Campaign. Este servidor se define al [configurar marcas](../../administration/using/branding.md#configuring-and-using-brands).

## Configuración de parámetros de validez {#setting-up-validity-parameters}

Antes de publicar, por motivos de seguridad y de rendimiento de la plataforma, le recomendamos encarecidamente que establezca una fecha de caducidad en las propiedades de la página de aterrizaje. En la fecha seleccionada, la página de aterrizaje se cancelará automáticamente la publicación. Para ello:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el ![](assets/edit_darkgrey-24px.png) botón del tablero de la página de aterrizaje.

   ![](assets/lp_edit_properties_button.png)

1. Configure la fecha y hora de caducidad en la **[!UICONTROL Publication]**sección: la página de aterrizaje se cancelará automáticamente en la fecha especificada y, por lo tanto, ya no estará disponible.

   Puede seleccionar el huso horario que se tendrá en cuenta para esta fecha y hora.

1. Defina una dirección URL de redirección para redireccionar a los visitantes al intentar acceder a una página de aterrizaje no activa.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>También puede definir una fecha y hora de implementación: la página de aterrizaje se publicará automáticamente en la fecha especificada.

## Publicación de una página de aterrizaje {#publishing-a-landing-page}

Al publicar una página de aterrizaje, esta se activa y los visitantes pueden acceder a ella.

Puede cancelar la publicación o actualizar y volver a publicar la página de aterrizaje en cualquier momento, mediante el **[!UICONTROL Publish]**botón. Sin embargo, si la republicación falla y aún no ha cancelado la publicación de la página de aterrizaje, la primera versión permanecerá en línea.

---
solution: Campaign Standard
product: campaign
title: Uso compartido de una página de aterrizaje
description: Aprenda a probar y publicar una página de aterrizaje en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Páginas de destino
role: User
level: Intermediate
exl-id: af849377-686f-45b3-bf6e-5069a8966987
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 100%

---

# Prueba y publicación de una página de destino{#testing-publishing--landing-page}

## Acerca de la publicación de páginas de aterrizaje {#about-landing-page-publication}

Antes de publicar una página de aterrizaje, debe hacer pruebas: valide la ejecución, configure el acceso y configure la caducidad de la página de aterrizaje. Estos pasos son requisitos previos y deben ejecutarse con precaución.

## Prueba de la página de aterrizaje {#testing-the-landing-page-}

Dado que la página de aterrizaje afectará a la plataforma y a los datos, debe probar su ejecución detenidamente. Para ello:

1. Haga clic en el botón **[!UICONTROL Test]** en la barra de acciones de la página de aterrizaje.
1. En la pantalla de prueba, seleccione un perfil de prueba y un servicio de prueba si la página de aterrizaje es para administrar suscripciones.

   ![](assets/lp_test_2.png)

1. Introduzca datos en los campos y seleccione las opciones relevantes.
1. Envíe la página de aterrizaje y compruebe las actualizaciones en la base de datos.

   >[!IMPORTANT]
   >
   >Cuando se envía el formulario, se actualizan el servicio y el perfil utilizados.

1. Repita esto con varios perfiles y datos.

También puede generar la miniatura de la página de aterrizaje desde esta pantalla.

>[!NOTE]
>
>Para ver la página de aterrizaje en la interfaz de usuario de la Campaign, la URL del servidor de aplicaciones debe ser segura. En ese caso, utilice https:// en lugar de http:// para configurar esta URL al [configurar su marca](../../administration/using/branding.md#configuring-and-using-brands).

## Configuración de parámetros de validez {#setting-up-validity-parameters}

Antes de publicar, por motivos de seguridad y de rendimiento de la plataforma, le recomendamos encarecidamente que defina una fecha de vencimiento en las propiedades de la página de aterrizaje. En la fecha seleccionada, la página de aterrizaje se cancelará de forma automática. Para ello:

1. Edite las propiedades de la página de aterrizaje a través del botón ![](assets/edit_darkgrey-24px.png) del panel de la página de aterrizaje.

   ![](assets/lp_edit_properties_button.png)

1. Configure la fecha y hora de caducidad en la sección **[!UICONTROL Publication]**: la página de aterrizaje se cancelará automáticamente en la fecha especificada y, por tanto, ya no estará disponible.

   Puede seleccionar el huso horario que se tendrá en cuenta para esta fecha y hora.

1. Defina una URL de redirección para redireccionar los visitantes al intentar acceder a una página de aterrizaje no activa.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>También puede definir una fecha y hora de implementación: la página de aterrizaje se publicará automáticamente en la fecha especificada.

## Publicación de una página de aterrizaje {#publishing-a-landing-page}

Al publicar una página de aterrizaje, esta se activa y sus visitantes pueden acceder a ella.

Puede cancelar la publicación o las actualizaciones, y volver a publicar la página de aterrizaje en cualquier momento haciendo clic en el botón **[!UICONTROL Publish]**. Sin embargo, si la republicación falla y aún no ha cancelado la publicación de la página de aterrizaje, la primera versión permanecerá en línea.

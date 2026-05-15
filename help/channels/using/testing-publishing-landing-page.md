---
title: Uso compartido de una página de destino
description: Aprenda a probar y publicar una página de destino en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Landing Pages
role: User
level: Intermediate
exl-id: af849377-686f-45b3-bf6e-5069a8966987
TQID: https://experienceleague.adobe.com/8RZopDxY3R2f-67RtWyh7xRwD6-c2BhR-tEmEeLGO3Y
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 95%

---

# Prueba y publicación de una página de destino{#testing-publishing--landing-page}

## Acerca de la publicación de página de aterrizaje {#about-landing-page-publication}

Antes de publicar una página de destino, debe hacer pruebas: valide la ejecución, configure el acceso y configure la caducidad de la página de destino. Estos pasos son requisitos previos y deben ejecutarse con precaución.

## Prueba de la página de aterrizaje {#testing-the-landing-page-}

Dado que la página de destino afectará a la plataforma y a los datos, debe probar su ejecución detenidamente. Para ello:

1. Haga clic en el botón **[!UICONTROL Test]** en la barra de acciones de la página de destino.
1. En la pantalla de prueba, seleccione un perfil de prueba y un servicio de prueba si la página de destino es para administrar suscripciones.

   ![](assets/lp_test_2.png)

1. Introduzca datos en los campos y seleccione las opciones relevantes.
1. Envíe la página de destino y compruebe las actualizaciones en la base de datos.

   >[!IMPORTANT]
   >
   >Cuando se envía el formulario, se actualizan el servicio y el perfil utilizados.

1. Repita esto con varios perfiles y datos.

También puede generar la miniatura de la página de aterrizaje desde esta pantalla.

>[!NOTE]
>
>Para ver la página de destino en la interfaz de usuario de la Campaign, la URL del servidor de aplicaciones debe ser segura. En ese caso, utilice https:// en lugar de http:// para configurar esta URL al [configurar su marca](../../administration/using/branding.md#configuring-and-using-brands).

## Configuración de parámetros de validez {#setting-up-validity-parameters}

Antes de publicar, por motivos de seguridad y de rendimiento de la plataforma, le recomendamos encarecidamente que defina una fecha de caducidad en las propiedades de la página de destino. En la fecha seleccionada, la página de destino se cancelará de forma automática. Para ello:

1. Edite las propiedades de la página de destino a través del botón ![](assets/edit_darkgrey-24px.png) del panel de control de la página de destino.

   ![](assets/lp_edit_properties_button.png)

1. Configure la fecha y hora de caducidad en la sección **[!UICONTROL Publication]**: la página de destino se cancelará automáticamente en la fecha especificada y, por tanto, ya no estará disponible.

   Puede seleccionar el huso horario que se tendrá en cuenta para esta fecha y hora.

1. Defina una URL de redirección para redireccionar los visitantes al intentar acceder a una página de destino no activa.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>También puede definir una fecha y hora de implementación: la página de destino se publicará automáticamente en la fecha especificada.

## Publicación de una página de aterrizaje {#publishing-a-landing-page}

Al publicar una página de destino, esta se activa y sus visitantes pueden acceder a ella.

Puede cancelar la publicación o las actualizaciones, y volver a publicar la página de destino en cualquier momento haciendo clic en el botón **[!UICONTROL Publish]**. Sin embargo, si la republicación falla y aún no ha cancelado la publicación de la página de destino, la primera versión permanecerá en línea.

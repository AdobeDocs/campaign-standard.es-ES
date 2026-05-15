---
title: Configuración de una página de destino
description: Aprenda a configurar las propiedades de una página de destino.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 0b9795e9-83e6-4399-a3b1-fc69081f6a82
TQID: https://experienceleague.adobe.com/WGJMzhZXIgXMEioDtea5foDs7hRh70WOLG3XV41irvw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 656
ht-degree: 93%

---

# Configuración de una página de destino {#configuring-landing-page}

## Confirmar un envío de página de aterrizaje {#confirm-a-landing-page-submission}

Cuando un visitante envía una página de destino, puede configurar las acciones activadas. Para ello:

1. Edite las propiedades de página de destino a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del panel de control de página de destino y muestre los parámetros de **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. En la sección **[!UICONTROL Specific actions]**, seleccione **[!UICONTROL Start sending message]** para determinar el envío de un mensaje automático, por ejemplo, para confirmar la suscripción a un servicio. Debe seleccionar una plantilla de envíos de correo electrónico.

   Tenga en cuenta que si un mensaje de confirmación ya está configurado en el nivel de servicio, no debe seleccionar uno en esta pantalla para evitar enviar varios mensajes de confirmación. Consulte [Configuración de un servicio](../../audiences/using/creating-a-service.md).

1. Cree **[!UICONTROL Additional data]** para permitir almacenar datos adicionales cuando se envía la página de destino. Estos datos no son visibles para las personas que visitan la página. Solo se tienen en cuenta los valores constantes.

   ![](assets/lp_parameters_6.png)

## Vinculación de una página de aterrizaje a un servicio {#linking-a-landing-page-to-a-service}

Puede vincular un formulario a un servicio para que los perfiles puedan suscribirse a un servicio específico al validar las páginas de destino.

Los parámetros para vincular una página de destino permiten especificar el tipo de acción realizada y si la página de destino está vinculada específicamente a un único servicio o si es genérica.

Para seleccionar el servicio que desea vincular, siga estos pasos:

1. Edite las propiedades de página de destino a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del panel de control de página de destino y muestre los parámetros de **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. Elija **[!UICONTROL Subscription]** en la lista desplegable **[!UICONTROL Specific actions]**.

   ![](assets/lp_parameters_5.png)

1. Seleccione **[!UICONTROL Specific service]** para vincular la página de destino a un solo servicio. No seleccione esta opción si desea utilizar varios servicios con la página de destino.

   Utilice la opción **[!UICONTROL Specified service in the URL]** para permitir que la página de destino se utilice en varios servicios. Por lo tanto, debe hacer referencia a la página de destino al configurar el servicio.

## Configuración de permisos y datos de precarga {#setting-permissions-and-pre-loading-data}

El acceso a una página de destino se puede restringir a visitantes identificados, que proceden de un vínculo de un mensaje enviado por Campaign, por ejemplo, o a una unidad organizativa específica.
En el caso de visitantes identificados, puede cargar previamente sus datos en la página de destino. Para ello:

1. Edite las propiedades de página de destino a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del panel de control de página de destino y muestre los parámetros de **[!UICONTROL Access & loading]**.

   ![](assets/lp_edit_properties_button.png)

1. Seleccione **[!UICONTROL Preload visitor data]**.

   Si un visitante a la página corresponde a un perfil de la base de datos, sus datos se muestran en los campos del formulario asignados a los datos de la base de datos y se tienen en cuenta los elementos de personalización de la página de destino.

   ![](assets/lp_parameters_3_temp.png)

También puede autorizar a cualquier visitante para que acceda a la página de aterrizaje mediante la opción **[!UICONTROL Authorize unidentified visitors]**.

<!--Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.-->

Las páginas de destino también pueden vincularse a una unidad organizativa. Esto define el acceso de los usuarios a las diferentes páginas de destino. Para asignar una unidad organizativa:

1. Acceda a las propiedades de la página de destino mediante el icono **[!UICONTROL Edit properties]**.

   ![](assets/lp_parameters_google3.png)

1. Despliegue **[!UICONTROL Access authorization]**.

1. Haga clic en el menú desplegable y seleccione la unidad organizativa. Para obtener más información sobre cómo crear una unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. Los campos **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Access authorization]** y **[!UICONTROL Last modified]** se completan automáticamente.

1. Haga clic en **[!UICONTROL Confirm]**, luego en **[!UICONTROL Save]**.

Ahora, solo se puede administrar y acceder a la página de destino si se es un usuario dentro de la unidad organizativa elegida.

![](assets/lp_org_unit_3.png)

## Configuración de Google reCAPTCHA {#setting-google-recaptcha}

Puede configurar Google reCAPTCHA V3 con la página de destino para protegerlo del spam y los abusos causados por los bots. Para poder usarlo con la página de destino, primero debe crear una cuenta externa. Para obtener más información sobre cómo configurarla, consulte esta [sección](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Una vez configurada la cuenta externa de Google reCAPTCHA V3, puede añadirla a la página de destino:

1. Antes de publicar la página de destino, acceda a las propiedades de la página mediante el icono ![](assets/edit_darkgrey-24px.png) en el panel de control de página de destino.

   ![](assets/lp_parameters_google3.png)

1. Despliegue el menú **[!UICONTROL Access & loading]**.
1. Marque la opción **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]**.
1. Seleccione la cuenta externa reCAPTCHA de Google creada anteriormente.

   ![](assets/lp_parameters_google_temp.png)

1. Haga clic **[!UICONTROL Confirm]**.

La página de destino ahora está configurada con Google reCAPTCHA, que se puede ver en la parte inferior de la página.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA devuelve una puntuación basada en las interacciones de los usuarios con la página. Para comprobar su puntuación, conéctese a Admin Console de Google.

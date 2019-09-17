---
title: Diseño de una página de aterrizaje
seo-title: Diseño de una página de aterrizaje
description: Diseño de una página de aterrizaje
seo-description: Siga estos pasos para diseñar el contenido de una página de aterrizaje y vincularlo a un servicio.
page-status-flag: nunca activado
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: landing-pages
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# Diseño de una página de aterrizaje{#designing-a-landing-page}

## Acerca del diseño de contenido {#about-content-design}

Las páginas de aterrizaje se crean como cualquier actividad [de mercadotecnia](../../start/using/marketing-activities.md#about-marketing-activities).

Al diseñar una página de aterrizaje, debe definir el contenido de:

* la propia página,
* la página de confirmación,
* la página de error.

Utilice el conmutador situado debajo de la barra de acciones para mostrar y configurar cada una de estas páginas.

El contenido de estas páginas se ha diseñado mediante el editor de contenido de Campaign. Consulte Contenido [de](../../channels/using/about-landing-page-content-design.md)diseño.

## Asignación de campos de formulario {#mapping-form-fields}

Los campos de entrada se utilizan para almacenar o actualizar datos en la base de datos de Campaign. Para ello, debe vincular los campos de la base de datos con la zona de entrada, el botón de radio o los bloques de tipo de casilla de verificación. Para ello:

1. Seleccione un bloque en la página de aterrizaje.
1. Complete la **[!UICONTROL Form data]** parte de la paleta.

   ![](assets/editing_lp_content_4.png)

1. Elija un campo de base de datos para establecer un vínculo con el campo de formulario en la zona de **[!UICONTROL Field]** selección.

   Cuando se selecciona la **[!UICONTROL Mandatory]** opción, la página solo se puede enviar si el usuario ha completado este campo. Si no se completa un campo obligatorio, aparecerá un mensaje de error cuando el usuario valide la página.

   >[!NOTE]
   >
   >Las páginas de aterrizaje solo se pueden asignar con **perfiles**.

1. Defina el tipo de campo eligiendo, por ejemplo **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]** en el área de **[!UICONTROL HTML type of the field]** selección.

>[!NOTE]
>
>Los campos predeterminados de las páginas de aterrizaje integradas están preconfigurados. Puede modificarlas según sea necesario.

## Envío del formulario {#submitting-the-form}

Puede seleccionar la acción que realizar cuando el visitante haga clic en el botón de envío. Para ello:

1. Seleccione el botón de envío de la página de aterrizaje.
1. Seleccione la acción en la lista desplegable del panel izquierdo. Las acciones posibles son: **[!UICONTROL Refresh]** (para actualizar la página) y **[!UICONTROL Next page]** (para mostrar la página de confirmación).

   ![](assets/editing_lp_content_5.png)

Además, puede cambiar la etiqueta del botón o configurar un vínculo específico. Para ello:

1. Seleccione el botón de envío.
1. Haga clic en el ![](assets/lp_link_properties.png) botón del panel izquierdo.
1. Introduzca la etiqueta del botón, seleccione el tipo de vínculo, sus propiedades y el destino.

   ![](assets/lp_link_custom.png)

## Vinculación de un formulario a un servicio {#linking-a-form-to-a-service}

Puede vincular un formulario a un servicio para que los perfiles se puedan suscribir a un servicio específico al validar las páginas de aterrizaje.

Los parámetros para vincular una página de aterrizaje permiten especificar el tipo de acción realizado y si la página de aterrizaje está vinculada específicamente a un único servicio o si es genérica.

Para seleccionar el servicio que desea vincular, debe:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del tablero de la página de aterrizaje y muestre los **[!UICONTROL Job]** parámetros.

   ![](assets/lp_edit_properties_button.png)

1. Elija **[!UICONTROL Subscription]** en la lista **[!UICONTROL Specific actions]** desplegable.

   ![](assets/lp_parameters_5.png)

1. Seleccione **[!UICONTROL Specific service]** para vincular la página de aterrizaje a un solo servicio. No seleccione esta opción si desea utilizar varios servicios con la página de aterrizaje.

   Utilice la **[!UICONTROL Specified service in the URL]** opción para permitir que la página de aterrizaje se utilice en varios servicios. Por lo tanto, debe hacer referencia a la página de aterrizaje al configurar el servicio.

### Confirmar un envío de página de aterrizaje {#confirm-a-landing-page-submission}

Cuando un visitante envía una página de aterrizaje, puede configurar las acciones activadas. Para ello:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del tablero de la página de aterrizaje y muestre los **[!UICONTROL Job]** parámetros.

   ![](assets/lp_edit_properties_button.png)

1. En la **[!UICONTROL Specific actions]** sección , seleccione **[!UICONTROL Start sending message]** para determinar el envío de un mensaje automático, por ejemplo para confirmar la suscripción a un servicio. A continuación, debe seleccionar una plantilla de envío de correo electrónico.

   Tenga en cuenta que si un mensaje de confirmación ya está configurado en el nivel de servicio, no debe seleccionar uno en esta pantalla para evitar enviar varios mensajes de confirmación. Consulte [Configurar un servicio](../../audiences/using/creating-a-service.md).

1. Crear **[!UICONTROL Additional data]** para habilitar el almacenamiento de datos adicionales cuando se envía la página de aterrizaje. Estos datos no son visibles para las personas que visitan la página. Solo se tienen en cuenta los valores constantes.

   ![](assets/lp_parameters_6.png)

## Configuración de permisos y precarga de datos {#setting-permissions-and-pre-loading-data}

El acceso a una página de aterrizaje puede restringirse a los visitantes identificados, que provienen de un vínculo en un mensaje enviado por Campaign, por ejemplo. En este caso, puede cargar previamente sus datos en la página de aterrizaje. Para ello:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del tablero de la página de aterrizaje y muestre los **[!UICONTROL Access & loading]** parámetros.

   ![](assets/lp_edit_properties_button.png)

1. Seleccione **[!UICONTROL Preload visitor data]**.

   Si un visitante de la página corresponde a un perfil de la base de datos, sus datos se muestran en los campos del formulario asignados a los datos de la base de datos y se tienen en cuenta los elementos de personalización de la página de aterrizaje.

   ![](assets/lp_parameters_3.png)

También puede:

* Utilice los parámetros de URL para identificar a los visitantes mediante la **[!UICONTROL Authorize visitor identification via URL parameters]** opción: a continuación, debe elegir la clave de carga y asignar los parámetros del filtro con los parámetros de la URL correspondiente.
* Autorice a cualquier visitante a acceder a la página de aterrizaje mediante la **[!UICONTROL Authorize unidentified visitors]** opción .

## Configuración de Google reCAPTCHA {#setting-google-recaptcha}

Puede configurar Google reCAPTCHA V3 con su página de aterrizaje para protegerla del spam y los abusos causados por los bots. Para poder utilizarlo con la página de aterrizaje, primero debe crear una cuenta externa. Para obtener más información sobre cómo configurarla, consulte esta [sección](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Una vez configurada la cuenta externa de Google reCAPTCHA V3, puede agregarla a la página de aterrizaje:

1. Antes de publicar la página de aterrizaje, acceda a las propiedades de página a las que se accede mediante el icono del tablero de la página de aterrizaje. ![](assets/edit_darkgrey-24px.png)

   ![](assets/lp_parameters_google3.png)

1. Despliegue el **[!UICONTROL Access & loading]** menú.
1. Marque la **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** opción.
1. Seleccione la cuenta externa de Google reCAPTCHA creada anteriormente.

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

La página de aterrizaje ahora está configurada con Google reCAPTCHA, que se puede ver en la parte inferior de la página.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA devolverá una puntuación basada en las interacciones de los usuarios con su página. Para comprobar su puntuación, conéctese a su consola [de administración de](https://g.co/recaptcha/admin)Google.

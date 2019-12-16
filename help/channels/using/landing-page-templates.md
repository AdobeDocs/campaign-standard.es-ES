---
title: Plantillas de página de aterrizaje
description: Obtenga más información sobre las plantillas de página de aterrizaje.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Acerca de las plantillas de página de aterrizaje {#landing-page-templates}

Campaign viene con un conjunto de plantillas de página de aterrizaje integradas:

* **[!UICONTROL Acquisition]**:: esta es la plantilla predeterminada para las páginas de aterrizaje, que permite capturar y actualizar datos en la base de datos de Campaign.
* **[!UICONTROL Subscription]**:: esta plantilla debe utilizarse para ofrecer suscripciones a un servicio.
* **[!UICONTROL Unsubscription]**:: esta plantilla se puede vincular desde un correo electrónico enviado a los suscriptores de un servicio para permitirles cancelar la suscripción a este servicio.
* **[!UICONTROL Blacklist]**:: esta plantilla debe utilizarse cuando Campaign ya no desee establecer contacto con un perfil. Para obtener más información sobre la lista negra, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Estas plantillas se proponen de forma predeterminada al crear una nueva página de aterrizaje.

![](assets/lp_creation_1.png)

Para acceder a las plantillas de página de aterrizaje, haga clic en el logotipo de Adobe Campaign en la esquina superior izquierda y seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe recomienda crear sus propias plantillas duplicando una plantilla integrada. Algunos parámetros solo se pueden configurar en plantillas de página de aterrizaje y no se pueden modificar directamente en las páginas de aterrizaje.

When building a template, we recommend adding a **'type'** attribute to tags. El editor procesará esta información y ayudará al usuario a vincular un campo de base de datos al campo de formulario al configurar la aplicación Web.

Ejemplo de código HTML en la plantilla:

```
<input id="email" type="email" name="email"/>
```

La lista oficial de atributos 'type' está disponible en la siguiente dirección: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)
---
title: Plantillas de Página de aterrizaje
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Acerca de las plantillas de página de aterrizaje {#landing-page-templates}

La Campaña incluye un conjunto de plantillas de página de aterrizaje integradas:

* **[!UICONTROL Acquisition]**:: esta es la plantilla predeterminada para páginas de aterrizaje, que permite capturar y actualizar datos en la base de datos de Campañas.
* **[!UICONTROL Subscription]**:: esta plantilla debe utilizarse para oferta de suscripciones a un servicio.
* **[!UICONTROL Unsubscription]**:: esta plantilla se puede vincular desde un correo electrónico enviado a los suscriptores de un servicio para permitirles cancelar la suscripción a este servicio.
* **[!UICONTROL Blacklist]**:: esta plantilla debe utilizarse cuando una Campaña ya no desee ponerse en contacto con un perfil. Para obtener más información sobre la lista negra, consulte [Acerca de la inclusión y la exclusión en la Campaña](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Estas plantillas se proponen de forma predeterminada al crear una nueva página de aterrizaje.

![](assets/lp_creation_1.png)

Para acceder a las plantillas de página de aterrizaje, haga clic en el logotipo de Adobe Campaign en la esquina superior izquierda y seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe recomienda crear sus propias plantillas duplicando una plantilla integrada. Algunos parámetros solo se pueden definir en plantillas de página de aterrizaje y no se pueden modificar directamente en páginas de aterrizaje.

Al crear una plantilla, se recomienda añadir un atributo **“type”** a las etiquetas El editor procesará esta información y ayudará al usuario a vincular un campo de base de datos al campo de formulario al configurar la aplicación Web.

Ejemplo de código HTML en la plantilla:

```
<input id="email" type="email" name="email"/>
```

La lista oficial de los atributos &#39;type&#39; está disponible en la siguiente dirección: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)
---
title: Plantillas de página de destino
description: Más información sobre las plantillas de página de destino.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
TQID: https://experienceleague.adobe.com/vJyIRO33IjK6o3--ekx-Iw9K-GcIZMViLz9wEr-kxY0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 93%

---

# Acerca de las plantillas de página de destino {#landing-page-templates}

Campaign incluye un conjunto de plantillas de página de destino integradas:

* **[!UICONTROL Acquisition]**: esta es la plantilla predeterminada para páginas de destino, que permite capturar y actualizar datos en la base de datos de Campaign.
* **[!UICONTROL Subscription]**: esta plantilla debe utilizarse para ofrecer suscripciones a un servicio.
* **[!UICONTROL Unsubscription]**: esta plantilla se puede vincular desde un correo electrónico enviado a los suscriptores de un servicio para permitirles cancelar su suscripción.
* **[!UICONTROL Denylist]**: esta plantilla debe utilizarse cuando un perfil ya no quiere que Campaign le siga contactando. Para obtener más información acerca de la administración de listas de bloqueados de la, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Estas plantillas se proponen de forma predeterminada al crear una nueva página de destino.

![](assets/lp_creation_1.png)

Para acceder a las plantillas de página de destino, haga clic en el logotipo de Adobe Campaign en la esquina superior izquierda y seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe recomienda crear sus propias plantillas duplicando una plantilla integrada. Algunos parámetros solo se pueden definir en plantillas de página de destino y no se pueden modificar directamente en páginas de destino.

Al crear una plantilla, se recomienda añadir un atributo **“type”** a las etiquetas El editor procesa esta información, que ayuda al usuario a vincular un campo de la base de datos al campo del formulario al configurar la aplicación web.

Ejemplo de código HTML en la plantilla:

```
<input id="email" type="email" name="email"/>
```

La lista oficial de los atributos “type” está disponible en la siguiente dirección: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)

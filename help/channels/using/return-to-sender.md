---
title: Regresar al remitente
seo-title: Regresar al remitente
description: Regresar al remitente
seo-description: Obtenga información sobre cómo recibir una dirección incorrecta y excluirla de futuras comunicaciones.
page-status-flag: no activado nunca
uuid: 11981 c 2 f -0 b 7 f -4166-9 daa-ec 6 a 6 b 4 d 5367
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: correo directo
discoiquuid: 5 f 20 ff 3 f -8242-4735-8 c 60-c 57610 edff 52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

Se admiten intercambios de archivos planos con proveedores de correo directo que incorporan información de retorno a remitente. Esto permite excluir las direcciones postales correspondientes de futuras comunicaciones. Esto también le permite recibir notificaciones de una dirección incorrecta e interactuar con el cliente a través de otros canales o pedirle que actualice su dirección postal.

Por ejemplo, un contacto se ha trasladado a un nuevo lugar y no le proporcionó su nueva dirección postal. El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, la cual automáticamente muestra las direcciones erróneas.

Para que esta funcionalidad funcione, la plantilla de envío predeterminada de correo directo incluye, en el contenido, el ID de registro de entrega. De este modo, Adobe Campaign podrá sincronizar los datos de entrega y perfil con la información que devuelve el proveedor.

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique esta plantilla para crear los suyos propios. For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

Cuando se realiza la importación, Adobe Campaign realiza automáticamente las siguientes acciones:

* Las direcciones incorrectas están bloqueadas en el nivel de perfil
* Se actualizan los indicadores principales de entrega (KPI)
* Se actualizan los registros de entrega


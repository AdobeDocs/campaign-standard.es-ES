---
title: Devolución al remitente
description: Obtenga información sobre cómo recibir notificaciones de una dirección incorrecta y excluirla de futuras comunicaciones.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
TQID: https://experienceleague.adobe.com/g-0yLI3-qYRfbF-gXuO8AtyCI3Qr5F7an5hqVzaQCE8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 2%

---

# Devolución al remitente{#return-to-sender}

Se admiten los intercambios de archivos planos con proveedores de correo directo que incorporan información de devolución al remitente. Esto permite excluir las direcciones postales correspondientes de futuras comunicaciones. Esto también le permite recibir una notificación de una dirección incorrecta y contactar con el cliente a través de otros canales o animarle a actualizar su dirección postal.

Por ejemplo, un contacto se ha trasladado a un nuevo lugar y no le ha proporcionado su nueva dirección postal. El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, que las incluye en la lista de bloqueados automáticamente de forma automática.

Para que esta funcionalidad funcione, la plantilla de envíos predeterminada de correo postal incluye, en el contenido, el ID de registro de envíos. Por lo tanto, Adobe Campaign puede sincronizar los datos de perfil y envío con la información devuelta por el proveedor.

![](assets/direct_mail_return_sender_1.png)

Hay disponible una plantilla de importación en **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique esta plantilla para crear la suya propia. Para obtener más información sobre cómo usar plantillas de importación, consulte [Usar plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Cuando la importación haya finalizado, Adobe Campaign realizará automáticamente las siguientes acciones:

* Las direcciones incorrectas se añaden a la lista de bloqueados de datos en el nivel de perfil de
* Se actualizan los indicadores principales de entrega (KPI)
* Se actualizan los registros de envío

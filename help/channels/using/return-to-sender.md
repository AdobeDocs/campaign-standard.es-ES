---
title: Devolver al remitente
description: Obtenga información sobre cómo recibir notificaciones de una dirección incorrecta y excluirla de futuras comunicaciones.
page-status-flag: nunca activado
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Devolver al remitente{#return-to-sender}

Se admiten los intercambios de archivos planos con proveedores de correo directo que incorporan la información de devolución al remitente. Esto permite excluir las direcciones postales correspondientes de futuras comunicaciones. Esto también le permite ser notificado de una dirección incorrecta y ponerse en contacto con el cliente a través de otros canales o alentarlo a actualizar su dirección postal.

Por ejemplo, un contacto se ha trasladado a un nuevo lugar y no le ha proporcionado su nueva dirección postal. El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, que automáticamente pone en negro las direcciones erróneas.

Para que esta funcionalidad funcione, la plantilla de entrega predeterminada de correo directo incluye, en el contenido, el ID de registro de entrega. Por lo tanto, Adobe Campaign podrá sincronizar los datos de perfil y entrega con la información devuelta por el proveedor.

![](assets/direct_mail_return_sender_1.png)

En la sección **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]** correspondiente se encuentra disponible una plantilla de importación. Duplique esta plantilla para crear la suya propia. Para obtener más información sobre el uso de plantillas de importación, consulte [Uso de plantillas](../../automating/using/defining-import-templates.md)de importación.

![](assets/direct_mail_return_sender_2.png)

Cuando la importación ha finalizado, Adobe Campaign realiza automáticamente las siguientes acciones:

* Las direcciones incorrectas se bloquean en el nivel de perfil
* Se actualizan los indicadores principales de entrega (KPI)
* Se actualizan los registros de entrega


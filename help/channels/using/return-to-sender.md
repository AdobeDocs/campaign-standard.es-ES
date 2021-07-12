---
solution: Campaign Standard
product: campaign
title: Devolución al remitente
description: Obtenga información sobre cómo recibir notificaciones de una dirección incorrecta y excluirla de futuras comunicaciones.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Correo directo
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---

# Devolución al remitente{#return-to-sender}

Se admiten los intercambios de archivos planos con proveedores de correo postal que incorporan la información de retorno al remitente. Esto permite excluir las direcciones postales correspondientes de futuras comunicaciones. Esto también le permite recibir notificaciones de una dirección incorrecta y comunicarse con el cliente a través de otros canales o animarlo a actualizar su dirección postal.

Por ejemplo, un contacto se ha trasladado a un nuevo lugar y no le ha proporcionado su nueva dirección postal. El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, que lista de bloqueados automáticamente las direcciones erróneas.

Para que esta funcionalidad funcione, la plantilla de entrega predeterminada de correo postal incluye, en el contenido, el ID de registro de entrega. Por lo tanto, Adobe Campaign podrá sincronizar los datos de perfil y envío con la información devuelta por el proveedor.

![](assets/direct_mail_return_sender_1.png)

Hay disponible una plantilla de importación en **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique esta plantilla para crear la suya propia. Para obtener más información sobre el uso de plantillas de importación, consulte [Uso de plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Cuando la importación ha finalizado, Adobe Campaign realiza automáticamente las siguientes acciones:

* Se añaden direcciones incorrectas a lista de bloqueados a nivel de perfil
* Se actualizan los indicadores principales de envío (KPI)
* Se actualizan los registros de envío
